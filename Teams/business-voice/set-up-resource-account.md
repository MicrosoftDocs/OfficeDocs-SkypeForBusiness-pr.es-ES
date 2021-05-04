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
ms.openlocfilehash: 76e91a650e9e72c21a39d292e32fe5ff8ecbf80b
ms.sourcegitcommit: 49cdcf344c63c805bcb6365804c6f5d1393e926a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2021
ms.locfileid: "52130441"
---
# <a name="step-4-set-up-a-business-voice-resource-account"></a><span data-ttu-id="d2603-103">Paso 4: Configurar una cuenta de recursos de Business Voice</span><span class="sxs-lookup"><span data-stu-id="d2603-103">Step 4: Set up a Business Voice resource account</span></span>

<span data-ttu-id="d2603-104">En Microsoft Teams, se requiere una cuenta de recursos para cada operador automático o cola de llamadas.</span><span class="sxs-lookup"><span data-stu-id="d2603-104">In Microsoft Teams, a resource account is required for each auto attendant or call queue.</span></span> <span data-ttu-id="d2603-105">Las cuentas de recursos también pueden tener asignados números de teléfono de servicio.</span><span class="sxs-lookup"><span data-stu-id="d2603-105">Resource accounts may also be assigned service telephone numbers.</span></span> <span data-ttu-id="d2603-106">Así se asignan números de teléfono a operadores automáticos y colas de llamadas, lo que permite que los autores de llamadas de fuera de Teams lleguen al operador automático o a la cola de llamadas.</span><span class="sxs-lookup"><span data-stu-id="d2603-106">This is how you assign phone numbers to auto attendants and call queues allowing callers from outside Teams to reach the auto attendant or call queue.</span></span>

## <a name="obtain-virtual-user-licenses"></a><span data-ttu-id="d2603-107">Obtener licencias de usuario virtual</span><span class="sxs-lookup"><span data-stu-id="d2603-107">Obtain virtual user licenses</span></span>

<span data-ttu-id="d2603-108">Las cuentas de recursos requieren una licencia para trabajar con operadores automáticos y colas de llamadas.</span><span class="sxs-lookup"><span data-stu-id="d2603-108">Resource accounts require a license in order to work with auto attendants and call queues.</span></span> <span data-ttu-id="d2603-109">Puede usar una licencia *Microsoft 365 Sistema telefónico : usuario* virtual.</span><span class="sxs-lookup"><span data-stu-id="d2603-109">You can use a free *Microsoft 365 Phone System - Virtual User* license.</span></span>

1. <span data-ttu-id="d2603-110">Inicie sesión en el Centro de administración de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d2603-110">Sign in to the Microsoft 365 admin center.</span></span>
2. <span data-ttu-id="d2603-111">Ir a **Complementos de servicios** de compra de  >    >  **facturación** Ver todos los productos de  >  **complementos**</span><span class="sxs-lookup"><span data-stu-id="d2603-111">Go to **Billing** > **Purchase services** > **Add-ons** > **See all Add-ons products**</span></span>
3. <span data-ttu-id="d2603-112">Desplácese hasta el final para buscar la **Microsoft 365 Sistema telefónico de usuario** virtual.</span><span class="sxs-lookup"><span data-stu-id="d2603-112">Scroll to the end to find the **Microsoft 365 Phone System – Virtual User** license.</span></span> <span data-ttu-id="d2603-113">Seleccione **Detalles** y, a continuación, **Comprar**.</span><span class="sxs-lookup"><span data-stu-id="d2603-113">Select **Details**, then **Buy**.</span></span>
4. <span data-ttu-id="d2603-114">En la página de compra de licencia, seleccione el número de licencias de usuario virtual que desee.</span><span class="sxs-lookup"><span data-stu-id="d2603-114">On the license purchase page, select the number of virtual user licenses you want.</span></span> <span data-ttu-id="d2603-115">Necesita una licencia virtual para cada operador automático y la cola de llamadas que tiene previsto configurar.</span><span class="sxs-lookup"><span data-stu-id="d2603-115">You need one virtual license for each auto attendant and call queue you plan to set up.</span></span> <span data-ttu-id="d2603-116">Se recomienda seleccionar al menos cinco licencias para que pueda configurar fácilmente más operadores automáticos y colas de llamadas en el futuro sin tener que comprar más licencias inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="d2603-116">We recommend selecting at least five licenses so you can easily set up more auto attendants and call queues in the future without having to purchase more licenses right away.</span></span>
5. <span data-ttu-id="d2603-117">Desactive **Asignar automáticamente a todos los usuarios sin licencias.**</span><span class="sxs-lookup"><span data-stu-id="d2603-117">Uncheck **Automatically assign to all of your users with no licenses**.</span></span>
6. <span data-ttu-id="d2603-118">Seleccione **Des check-out now**.</span><span class="sxs-lookup"><span data-stu-id="d2603-118">Select **Check out now**.</span></span>
7. <span data-ttu-id="d2603-119">Confirme el pedido, seleccione **Siguiente** y, a continuación, **Realizar pedido.**</span><span class="sxs-lookup"><span data-stu-id="d2603-119">Confirm your order, select **Next**, and then **Place order**.</span></span>

> [!NOTE]
> <span data-ttu-id="d2603-120">Tenga en cuenta que aún debe  **comprar** la licencia aunque tenga un costo de cero.</span><span class="sxs-lookup"><span data-stu-id="d2603-120">Keep in mind you must still  **Buy** the license even though it has a cost of zero.</span></span>

## <a name="create-a-resource-account"></a><span data-ttu-id="d2603-121">Crear una cuenta de recursos</span><span class="sxs-lookup"><span data-stu-id="d2603-121">Create a resource account</span></span>

<span data-ttu-id="d2603-122">Después de recibir la licencia *Microsoft 365 Sistema telefónico usuario virtual,* puede crear su cuenta de recursos.</span><span class="sxs-lookup"><span data-stu-id="d2603-122">After you've received your *Microsoft 365 Phone System - Virtual User* license, you can create your resource account.</span></span>

![Captura de pantalla de la interfaz de usuario agregar cuenta de recursos](../media/resource-account-add.png)

1. <span data-ttu-id="d2603-124">En el Teams de administración, expanda **Configuración de** toda la organización y, a continuación, haga clic en Cuentas **de recursos.**</span><span class="sxs-lookup"><span data-stu-id="d2603-124">In the Teams admin center, expand **Org-wide settings**, and then click **Resource accounts**.</span></span>
2. <span data-ttu-id="d2603-125">Seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="d2603-125">Select **Add**.</span></span>
3. <span data-ttu-id="d2603-126">En el **panel Agregar cuenta de recursos,** rellene Nombre para **mostrar** y, a continuación, Nombre **de usuario.**</span><span class="sxs-lookup"><span data-stu-id="d2603-126">In the **Add resource account** pane, fill out **Display name**, and then **Username**.</span></span> <span data-ttu-id="d2603-127">Elija un nombre para mostrar descriptivo, como "Operador automático de línea principal" para describir el propósito de la cuenta de recursos.</span><span class="sxs-lookup"><span data-stu-id="d2603-127">Choose a descriptive display name such as "Main line auto attendant" to describe the purpose of the resource account.</span></span>
4. <span data-ttu-id="d2603-128">En **Tipo de cuenta de recursos,** seleccione Operador **automático.**</span><span class="sxs-lookup"><span data-stu-id="d2603-128">In **Resource account type**, select **Auto attendant**.</span></span>
5. <span data-ttu-id="d2603-129">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="d2603-129">Select **Save**.</span></span>

![Captura de pantalla de una lista de cuentas de recursos](../media/resource-accounts-page.png)

## <a name="assign-a-license"></a><span data-ttu-id="d2603-131">Asignar una licencia</span><span class="sxs-lookup"><span data-stu-id="d2603-131">Assign a license</span></span>

<span data-ttu-id="d2603-132">Después de crear la cuenta de recursos, debe asignar una *Microsoft 365 Sistema telefónico:* licencia de usuario virtual *o Sistema telefónico* usuario.</span><span class="sxs-lookup"><span data-stu-id="d2603-132">After you've created your resource account, you need to assign a *Microsoft 365 Phone System - Virtual User* license or *Phone System* license.</span></span>

![Captura de pantalla de la interfaz de usuario asignar licencias en el Microsoft 365 de administración](../media/resource-account-assign-virtual-user-license.png)

1. <span data-ttu-id="d2603-134">En el Microsoft 365 de administración, vaya a **Usuarios**  >  **usuarios activos.**</span><span class="sxs-lookup"><span data-stu-id="d2603-134">In the Microsoft 365 admin center, go to **Users** > **Active users**.</span></span>
2. <span data-ttu-id="d2603-135">Seleccione su cuenta de recursos.</span><span class="sxs-lookup"><span data-stu-id="d2603-135">Select your resource account.</span></span>
1. <span data-ttu-id="d2603-136">En la **pestaña Licencias y aplicaciones,** en **Licencias,** **seleccione Microsoft 365 Sistema telefónico - Usuario virtual.**</span><span class="sxs-lookup"><span data-stu-id="d2603-136">On the **Licenses and Apps** tab, under **Licenses**, select **Microsoft 365 Phone System - Virtual User**.</span></span>
1. <span data-ttu-id="d2603-137">Seleccione **Guardar cambios y,** a continuación, **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="d2603-137">Select **Save changes** and then **Close**.</span></span>

## <a name="assign-a-service-number"></a><span data-ttu-id="d2603-138">Asignar un número de servicio</span><span class="sxs-lookup"><span data-stu-id="d2603-138">Assign a service number</span></span>

![Captura de pantalla de la interfaz de usuario asignar número de servicio](../media/resource-account-assign-phone-number.png)

1. <span data-ttu-id="d2603-140">En el Teams de administración, vaya a Configuración **de toda** la organización y, a continuación, Cuentas **de recursos.**</span><span class="sxs-lookup"><span data-stu-id="d2603-140">In the Teams admin center, go to **Org-wide settings** and then **Resource accounts**.</span></span> 
1. <span data-ttu-id="d2603-141">Seleccione la cuenta de recursos que acaba de crear y, a continuación, haga clic **en Asignar o desasignación.**</span><span class="sxs-lookup"><span data-stu-id="d2603-141">Select the resource account you just created, and then click **Assign/unassign**.</span></span>
1. <span data-ttu-id="d2603-142">En la **lista Teléfono de tipo de número,** elija En **línea.**</span><span class="sxs-lookup"><span data-stu-id="d2603-142">In the **Phone number type** dropdown, choose **Online**.</span></span>
1. <span data-ttu-id="d2603-143">En el **cuadro Número de teléfono** asignado, busque el número que desea usar y haga clic en **Agregar.**</span><span class="sxs-lookup"><span data-stu-id="d2603-143">In the **Assigned phone number** box, search for the number you want to use and click **Add**.</span></span> <span data-ttu-id="d2603-144">Asegúrese de incluir el código de país (por ejemplo, **+1** 250 555 0012)</span><span class="sxs-lookup"><span data-stu-id="d2603-144">Be sure to include the country code (for example, **+1** 250 555 0012)</span></span>
1. <span data-ttu-id="d2603-145">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="d2603-145">Click **Save**.</span></span>
    > [!NOTE]
    > <span data-ttu-id="d2603-146">No es necesario seleccionar un operador  automático en Asignar a porque el operador automático al que desea agregar el número ya está seleccionado.</span><span class="sxs-lookup"><span data-stu-id="d2603-146">You don't need to select an auto attendant under **Assign to** because the auto attendant you want to add the number to is already selected.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="d2603-147">Paso siguiente: Asignar números de teléfono a los usuarios</span><span class="sxs-lookup"><span data-stu-id="d2603-147">Next step: Assign phone numbers to your users</span></span>](set-up-assign-numbers.md)
