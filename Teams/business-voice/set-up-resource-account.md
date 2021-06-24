---
title: Configurar una cuenta de Microsoft 365 Business Voice de recursos
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- Teams_Business_Voice
search.appverid: MET150
description: Obtenga información sobre cómo configurar una cuenta de Microsoft 365 Business Voice para su uso con operadores automáticos.
appliesto:
- Microsoft Teams
ms.openlocfilehash: df5001b6f757b407e96a473d302c79d837af957c
ms.sourcegitcommit: 38fa37d83704200911866cf017566fcb128ea2fe
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/24/2021
ms.locfileid: "53105172"
---
# <a name="step-4-set-up-a-business-voice-resource-account"></a><span data-ttu-id="e074c-103">Paso 4: Configurar una cuenta de recursos de Business Voice</span><span class="sxs-lookup"><span data-stu-id="e074c-103">Step 4: Set up a Business Voice resource account</span></span>

<span data-ttu-id="e074c-104">Las cuentas de recursos no se asignan a ningún usuario específico.</span><span class="sxs-lookup"><span data-stu-id="e074c-104">Resource accounts aren't assigned to any specific user.</span></span> <span data-ttu-id="e074c-105">En su lugar, las cuentas de recursos, que usan una licencia de usuario virtual gratuita, se usan en dispositivos y servicios en Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e074c-105">Instead, resource accounts, which use a free virtual user license, are used by devices and services in Microsoft 365.</span></span> <span data-ttu-id="e074c-106">En Microsoft Teams, a las cuentas de recursos se les asignan números de teléfono y, a continuación, se asocian con operadores automáticos y colas de llamadas.</span><span class="sxs-lookup"><span data-stu-id="e074c-106">In Microsoft Teams, resource accounts are assigned phone numbers and are then associated with auto attendants and call queues.</span></span>

<span data-ttu-id="e074c-107">Al asociar cuentas de recursos a operadores automáticos y colas de llamadas, puede agregarles uno o varios números de teléfono gratuitos o de pago.</span><span class="sxs-lookup"><span data-stu-id="e074c-107">By associating resource accounts to auto attendants and call queues, you can add one or more toll or toll-free phone numbers to them.</span></span> <span data-ttu-id="e074c-108">Por ejemplo, podría asociar una cuenta de recurso con un número de pago a un operador automático para los autores de llamadas locales.</span><span class="sxs-lookup"><span data-stu-id="e074c-108">For example, you could associate one resource account with a toll number to an auto attendant for local callers.</span></span> <span data-ttu-id="e074c-109">Para llamadas de larga distancia, puede asociar otra cuenta de recursos con un número gratuito al mismo operador automático.</span><span class="sxs-lookup"><span data-stu-id="e074c-109">For long distance calls, you could associate another resource account with a toll-free number to the same auto attendant.</span></span>

<span data-ttu-id="e074c-110">En las secciones de este artículo se muestra cómo configurar una cuenta de recursos y, a continuación, asignarle un número de teléfono.</span><span class="sxs-lookup"><span data-stu-id="e074c-110">The sections in this article show you how to set up a resource account and then assign a phone number to it.</span></span> <span data-ttu-id="e074c-111">Más adelante, asociará la cuenta de recursos con un operador automático.</span><span class="sxs-lookup"><span data-stu-id="e074c-111">Later on, you'll associate the resource account with an auto attendant.</span></span>

<span data-ttu-id="e074c-112">En el siguiente vídeo se muestra cómo completar estos pasos en el centro Teams administración.</span><span class="sxs-lookup"><span data-stu-id="e074c-112">The following video shows you how to complete these steps in the Teams admin center.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4OFYG]

## <a name="obtain-virtual-user-licenses"></a><span data-ttu-id="e074c-113">Obtener licencias de usuario virtual</span><span class="sxs-lookup"><span data-stu-id="e074c-113">Obtain virtual user licenses</span></span>

<span data-ttu-id="e074c-114">Las cuentas de recursos requieren una licencia para trabajar con operadores automáticos y colas de llamadas.</span><span class="sxs-lookup"><span data-stu-id="e074c-114">Resource accounts require a license in order to work with auto attendants and call queues.</span></span> <span data-ttu-id="e074c-115">Puede usar una licencia *Microsoft 365 Sistema telefónico : usuario* virtual.</span><span class="sxs-lookup"><span data-stu-id="e074c-115">You can use a free *Microsoft 365 Phone System - Virtual User* license.</span></span>

> [!NOTE]
> <span data-ttu-id="e074c-116">Solo debe realizar los pasos siguientes si se ha registrado para un período de prueba de Business Voice.</span><span class="sxs-lookup"><span data-stu-id="e074c-116">You should only need to perform the following steps if you've signed up for a Business Voice trial period.</span></span> <span data-ttu-id="e074c-117">Si compró licencias de Business Voice, las licencias virtuales ya deberían aplicarse a su cuenta.</span><span class="sxs-lookup"><span data-stu-id="e074c-117">If you purchased Business Voice licenses, virtual licenses should already be applied to your account.</span></span> 
>
> <span data-ttu-id="e074c-118">Para ver si ya tiene licencias virtuales, inicie sesión Microsoft 365 una cuenta con permisos de administrador global.</span><span class="sxs-lookup"><span data-stu-id="e074c-118">To see if you already have virtual licenses, log into Microsoft 365 using an account with Global admin permissions.</span></span> <span data-ttu-id="e074c-119">A continuación, vaya a Facturación > [Sus productos.](https://admin.microsoft.com/Adminportal/Home#/subscriptions)</span><span class="sxs-lookup"><span data-stu-id="e074c-119">Then go to Billing > [Your products](https://admin.microsoft.com/Adminportal/Home#/subscriptions).</span></span> <span data-ttu-id="e074c-120">Si tiene licencias virtuales, aparecerán como **Microsoft 365 Sistema telefónico : Usuario virtual.**</span><span class="sxs-lookup"><span data-stu-id="e074c-120">If you have virtual licenses, they'll appear as **Microsoft 365 Phone System - Virtual User**.</span></span>

1. <span data-ttu-id="e074c-121">Abra el Centro de administración de Microsoft 365 e inicie sesión con un usuario que sea administrador global (normalmente es la cuenta que usó para registrarse para Microsoft 365).</span><span class="sxs-lookup"><span data-stu-id="e074c-121">Open the Microsoft 365 admin center and log in with a user that is a Global admin (this is usually the account you used to sign up for Microsoft 365).</span></span>
2. <span data-ttu-id="e074c-122">En el panel de navegación izquierdo, vaya <a href="https://admin.microsoft.com/Adminportal/Home#/catalog" target="_blank">  >  a</a>Complementos de servicios de compra de facturación Ver todos los productos de  >    >  **complementos.**</span><span class="sxs-lookup"><span data-stu-id="e074c-122">In the left navigation pane, go to <a href="https://admin.microsoft.com/Adminportal/Home#/catalog" target="_blank">**Billing** > **Purchase services**</a> > **Add-ons** > **See all Add-ons products**.</span></span>
3. <span data-ttu-id="e074c-123">Desplácese hasta el final para buscar la **Microsoft 365 Sistema telefónico de usuario** virtual.</span><span class="sxs-lookup"><span data-stu-id="e074c-123">Scroll to the end to find the **Microsoft 365 Phone System – Virtual User** license.</span></span> <span data-ttu-id="e074c-124">Seleccione **Detalles** y, a continuación, **Comprar**.</span><span class="sxs-lookup"><span data-stu-id="e074c-124">Select **Details**, then **Buy**.</span></span>
4. <span data-ttu-id="e074c-125">En la página de compra de licencia, seleccione el número de licencias de usuario virtual que desee.</span><span class="sxs-lookup"><span data-stu-id="e074c-125">On the license purchase page, select the number of virtual user licenses you want.</span></span> <span data-ttu-id="e074c-126">Necesita una licencia virtual para cada operador automático y la cola de llamadas que tiene previsto configurar.</span><span class="sxs-lookup"><span data-stu-id="e074c-126">You need one virtual license for each auto attendant and call queue you plan to set up.</span></span> <span data-ttu-id="e074c-127">Se recomienda seleccionar al menos cinco licencias para que pueda configurar fácilmente más operadores automáticos y colas de llamadas en el futuro sin tener que comprar más licencias inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="e074c-127">We recommend selecting at least five licenses so you can easily set up more auto attendants and call queues in the future without having to purchase more licenses right away.</span></span>
5. <span data-ttu-id="e074c-128">Desactive **Asignar automáticamente a todos los usuarios sin licencias.**</span><span class="sxs-lookup"><span data-stu-id="e074c-128">Uncheck **Automatically assign to all of your users with no licenses**.</span></span>
6. <span data-ttu-id="e074c-129">Seleccione **Des check-out now**.</span><span class="sxs-lookup"><span data-stu-id="e074c-129">Select **Check out now**.</span></span>
7. <span data-ttu-id="e074c-130">Confirme el pedido, seleccione **Siguiente** y, a continuación, **Realizar pedido.**</span><span class="sxs-lookup"><span data-stu-id="e074c-130">Confirm your order, select **Next**, and then **Place order**.</span></span>

> [!NOTE]
> <span data-ttu-id="e074c-131">Tenga en cuenta que aún debe  **comprar** la licencia aunque tenga un costo de cero.</span><span class="sxs-lookup"><span data-stu-id="e074c-131">Keep in mind you must still  **Buy** the license even though it has a cost of zero.</span></span>

## <a name="create-a-resource-account"></a><span data-ttu-id="e074c-132">Crear una cuenta de recursos</span><span class="sxs-lookup"><span data-stu-id="e074c-132">Create a resource account</span></span>

<span data-ttu-id="e074c-133">Después de recibir la licencia *Microsoft 365 Sistema telefónico usuario virtual,* puede crear su cuenta de recursos.</span><span class="sxs-lookup"><span data-stu-id="e074c-133">After you've received your *Microsoft 365 Phone System - Virtual User* license, you can create your resource account.</span></span>

![Captura de pantalla de la interfaz de usuario agregar cuenta de recursos](../media/resource-account-add.png)

1. <span data-ttu-id="e074c-135">Abra el Microsoft Teams de administración e inicie sesión con un usuario que sea administrador global (normalmente es la cuenta que usó para registrarse para Microsoft 365).</span><span class="sxs-lookup"><span data-stu-id="e074c-135">Open the Microsoft Teams admin center and log in with a user that is a Global admin (this is usually the account you used to sign up for Microsoft 365).</span></span>
2. <span data-ttu-id="e074c-136">En el panel de navegación izquierdo, vaya a Configuración de toda la organización <a href="https://admin.teams.microsoft.com/company-wide-settings/resource-accounts" target="_blank">   >  **Cuentas de recursos.**</a></span><span class="sxs-lookup"><span data-stu-id="e074c-136">In the left navigation pane, go to <a href="https://admin.teams.microsoft.com/company-wide-settings/resource-accounts" target="_blank">**Org-wide settings** > **Resource accounts**</a>.</span></span>
3. <span data-ttu-id="e074c-137">Seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="e074c-137">Select **Add**.</span></span>
4. <span data-ttu-id="e074c-138">En el **panel Agregar cuenta de recursos,** rellene Nombre para **mostrar** y, a continuación, Nombre **de usuario.**</span><span class="sxs-lookup"><span data-stu-id="e074c-138">In the **Add resource account** pane, fill out **Display name**, and then **Username**.</span></span> <span data-ttu-id="e074c-139">Elija un nombre para mostrar descriptivo, como "Operador automático de línea principal" para describir el propósito de la cuenta de recursos.</span><span class="sxs-lookup"><span data-stu-id="e074c-139">Choose a descriptive display name such as "Main line auto attendant" to describe the purpose of the resource account.</span></span>
5. <span data-ttu-id="e074c-140">En **Tipo de cuenta de recursos,** seleccione Operador **automático.**</span><span class="sxs-lookup"><span data-stu-id="e074c-140">In **Resource account type**, select **Auto attendant**.</span></span>
6. <span data-ttu-id="e074c-141">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="e074c-141">Select **Save**.</span></span>

![Captura de pantalla de una lista de cuentas de recursos](../media/resource-accounts-auto-attendant-only-page.png)

## <a name="assign-a-license"></a><span data-ttu-id="e074c-143">Asignar una licencia</span><span class="sxs-lookup"><span data-stu-id="e074c-143">Assign a license</span></span>

<span data-ttu-id="e074c-144">Después de crear la cuenta de recursos, debe asignar una *Microsoft 365 Sistema telefónico:* licencia de usuario virtual *o Sistema telefónico* usuario.</span><span class="sxs-lookup"><span data-stu-id="e074c-144">After you've created your resource account, you need to assign a *Microsoft 365 Phone System - Virtual User* license or *Phone System* license.</span></span>

![Captura de pantalla de la interfaz de usuario asignar licencias en el Centro de administración de Microsoft 365](../media/resource-account-assign-virtual-user-license.png)

1. <span data-ttu-id="e074c-146">Abra el Centro de administración de Microsoft 365 e inicie sesión con un usuario que sea administrador global (normalmente es la cuenta que usó para registrarse para Microsoft 365).</span><span class="sxs-lookup"><span data-stu-id="e074c-146">Open the Microsoft 365 admin center and log in with a user that is a Global admin (this is usually the account you used to sign up for Microsoft 365).</span></span>
1. <span data-ttu-id="e074c-147">En el panel de navegación izquierdo, vaya a <a href="https://admin.microsoft.com/Adminportal/Home#/users" target="_blank"> **Usuarios**  >  **usuarios activos.**</a></span><span class="sxs-lookup"><span data-stu-id="e074c-147">In the left navigation pane, go to <a href="https://admin.microsoft.com/Adminportal/Home#/users" target="_blank">**Users** > **Active users**</a>.</span></span>
1. <span data-ttu-id="e074c-148">Seleccione su cuenta de recursos.</span><span class="sxs-lookup"><span data-stu-id="e074c-148">Select your resource account.</span></span>
1. <span data-ttu-id="e074c-149">En la **pestaña Licencias y aplicaciones,** en **Licencias,** **seleccione Microsoft 365 Sistema telefónico - Usuario virtual.**</span><span class="sxs-lookup"><span data-stu-id="e074c-149">On the **Licenses and Apps** tab, under **Licenses**, select **Microsoft 365 Phone System - Virtual User**.</span></span>
1. <span data-ttu-id="e074c-150">Seleccione **Guardar cambios y,** a continuación, **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="e074c-150">Select **Save changes** and then **Close**.</span></span>

## <a name="assign-a-service-number"></a><span data-ttu-id="e074c-151">Asignar un número de servicio</span><span class="sxs-lookup"><span data-stu-id="e074c-151">Assign a service number</span></span>

![Captura de pantalla de la interfaz de usuario asignar número de servicio](../media/resource-account-assign-phone-number.png)

1. <span data-ttu-id="e074c-153">Abra el Microsoft Teams de administración e inicie sesión con un usuario que sea administrador global (normalmente es la cuenta que usó para registrarse para Microsoft 365).</span><span class="sxs-lookup"><span data-stu-id="e074c-153">Open the Microsoft Teams admin center and log in with a user that is a Global admin (this is usually the account you used to sign up for Microsoft 365).</span></span>
1. <span data-ttu-id="e074c-154">En el panel de navegación izquierdo, vaya a Configuración de toda la organización <a href="https://admin.teams.microsoft.com/company-wide-settings/resource-accounts" target="_blank">   >  **Cuentas de recursos.**</a></span><span class="sxs-lookup"><span data-stu-id="e074c-154">In the left navigation pane, go to <a href="https://admin.teams.microsoft.com/company-wide-settings/resource-accounts" target="_blank">**Org-wide settings** > **Resource accounts**</a>.</span></span>
1. <span data-ttu-id="e074c-155">Seleccione la cuenta de recursos que acaba de crear y, a continuación, haga clic **en Asignar o desasignación.**</span><span class="sxs-lookup"><span data-stu-id="e074c-155">Select the resource account you just created, and then click **Assign/unassign**.</span></span>
1. <span data-ttu-id="e074c-156">En la **lista Teléfono de tipo de número,** elija En **línea.**</span><span class="sxs-lookup"><span data-stu-id="e074c-156">In the **Phone number type** dropdown, choose **Online**.</span></span>
1. <span data-ttu-id="e074c-157">En el **cuadro Número de teléfono** asignado, busque el número que desea usar y haga clic en **Agregar.**</span><span class="sxs-lookup"><span data-stu-id="e074c-157">In the **Assigned phone number** box, search for the number you want to use and click **Add**.</span></span> <span data-ttu-id="e074c-158">Asegúrese de incluir el código de país (por ejemplo, **+1** 250 555 0012)</span><span class="sxs-lookup"><span data-stu-id="e074c-158">Be sure to include the country code (for example, **+1** 250 555 0012)</span></span>
1. <span data-ttu-id="e074c-159">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="e074c-159">Click **Save**.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="e074c-160">Paso siguiente: Asignar números de teléfono a los usuarios</span><span class="sxs-lookup"><span data-stu-id="e074c-160">Next step: Assign phone numbers to your users</span></span>](set-up-assign-numbers.md)
