---
title: Configurar Microsoft 365 Business Voice de teléfono
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
description: Obtenga información sobre cómo configurar Microsoft 365 Business Voice de teléfono para los usuarios y servicios de su organización.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 89cb3764e30fa0bf4fcfa9d6a18d29ca69786cef
ms.sourcegitcommit: 2419348e964cfe97b72d533f267c5d7055d5366f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/12/2021
ms.locfileid: "52910042"
---
# <a name="step-2-set-up-business-voice-phone-numbers"></a><span data-ttu-id="b4bf7-103">Paso 2: Configurar números de teléfono de Business Voice</span><span class="sxs-lookup"><span data-stu-id="b4bf7-103">Step 2: Set up Business Voice phone numbers</span></span>

<span data-ttu-id="b4bf7-104">Para poder configurar usuarios o operadores automáticos en su organización, debe obtener números de teléfono para ellos.</span><span class="sxs-lookup"><span data-stu-id="b4bf7-104">Before you can set up users or auto attendants in your organization, you need to get phone numbers for them.</span></span> <span data-ttu-id="b4bf7-105">Hay varios tipos diferentes de números de teléfono, pero los siguientes son los dos tipos de números que necesita agregar en este paso:</span><span class="sxs-lookup"><span data-stu-id="b4bf7-105">There are several different types of phone numbers, however the following are the two types of numbers that you need to add in this step:</span></span>

- <span data-ttu-id="b4bf7-106">**Números de servicio** Estos números se usan para operadores automáticos, audioconferencias y colas de llamadas.</span><span class="sxs-lookup"><span data-stu-id="b4bf7-106">**Service numbers** These numbers are used for auto attendants, audio conferencing, and call queues.</span></span> <span data-ttu-id="b4bf7-107">Pueden ser números gratuitos o de pago y pueden atender grandes cantidades de llamadas al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="b4bf7-107">They can be toll or toll-free numbers and can handle large amounts of calls at the same time.</span></span> <span data-ttu-id="b4bf7-108">El número de teléfono de su empresa debe ser un número de servicio porque se asignará a un operador automático en un paso posterior.</span><span class="sxs-lookup"><span data-stu-id="b4bf7-108">Your company phone number needs to be a service number because it'll be assigned to an auto attendant in a later step.</span></span>
- <span data-ttu-id="b4bf7-109">**Números de suscriptor** Estos números se usan para los usuarios normales para que puedan realizar y recibir llamadas telefónicas.</span><span class="sxs-lookup"><span data-stu-id="b4bf7-109">**Subscriber numbers** These numbers are used for regular users so they can make and receive phone calls.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b4bf7-110">Incluso si desea usar los números de teléfono existentes, debe crear y asignar números de teléfono temporales a la línea telefónica principal de su empresa y a sus usuarios.</span><span class="sxs-lookup"><span data-stu-id="b4bf7-110">Even if you want to use your existing phone numbers, you need to create and assign temporary phone numbers to your company's main phone line and your users.</span></span> <span data-ttu-id="b4bf7-111">Podrá reemplazar estos números temporales por los números de teléfono existentes en un paso posterior.</span><span class="sxs-lookup"><span data-stu-id="b4bf7-111">You'll be able to replace these temporary numbers with your existing phone numbers in a later step.</span></span>

> [!NOTE]
> <span data-ttu-id="b4bf7-112">Los nuevos números de teléfono pueden tardar varias horas en estar disponibles en Teams.</span><span class="sxs-lookup"><span data-stu-id="b4bf7-112">It may take several hours for your new phone numbers to become available in Teams.</span></span>

<span data-ttu-id="b4bf7-113">En el siguiente vídeo se muestra cómo completar estos pasos en el centro Teams administración.</span><span class="sxs-lookup"><span data-stu-id="b4bf7-113">The following video shows you how to complete these steps in the Teams admin center.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWENzQ]

## <a name="set-up-a-service-number"></a><span data-ttu-id="b4bf7-114">Configurar un número de servicio</span><span class="sxs-lookup"><span data-stu-id="b4bf7-114">Set up a service number</span></span>

<span data-ttu-id="b4bf7-115">El número de servicio que configure ahora se usará en un paso posterior para el número de teléfono principal de su empresa.</span><span class="sxs-lookup"><span data-stu-id="b4bf7-115">The service number you set up now will be used in a later step for your company's main phone number.</span></span>

1. <span data-ttu-id="b4bf7-116">Abra el Microsoft Teams de administración e inicie sesión con un usuario que sea administrador global (normalmente es la cuenta que usó para registrarse para Microsoft 365).</span><span class="sxs-lookup"><span data-stu-id="b4bf7-116">Open the Microsoft Teams admin center and log in with a user that is a Global admin (this is usually the account you used to sign up for Microsoft 365).</span></span>
2. <span data-ttu-id="b4bf7-117">En el panel de navegación izquierdo, vaya <a href="https://admin.teams.microsoft.com/phone-numbers" target="_blank"> **a Números**  >  **de Teléfono y,**</a>a continuación, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="b4bf7-117">In the left navigation, go to <a href="https://admin.teams.microsoft.com/phone-numbers" target="_blank">**Voice** > **Phone numbers**</a>, and then click **Add**.</span></span>
3. <span data-ttu-id="b4bf7-118">Escriba un nombre para el pedido y agregue una descripción.</span><span class="sxs-lookup"><span data-stu-id="b4bf7-118">Enter a name for the order and add a description.</span></span>
4. <span data-ttu-id="b4bf7-119">En la página Ubicación y cantidad, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b4bf7-119">On the Location and quantity page, do the following:</span></span>
    1. <span data-ttu-id="b4bf7-120">En **País o región,** seleccione un país o región.</span><span class="sxs-lookup"><span data-stu-id="b4bf7-120">Under **Country or region**, select a country or region.</span></span>
    2. <span data-ttu-id="b4bf7-121">En **Tipo de número**, seleccione una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="b4bf7-121">Under **Number type**, select one of the following options:</span></span>

        - <span data-ttu-id="b4bf7-122">**Operador automático (pago)** Número de teléfono normal, no gratuito.</span><span class="sxs-lookup"><span data-stu-id="b4bf7-122">**Auto attendant (Toll)** Regular, non-toll-free, phone number.</span></span> <span data-ttu-id="b4bf7-123">Las tarifas de larga distancia se cobran al autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="b4bf7-123">Long distance fees are charged to the caller.</span></span>
        - <span data-ttu-id="b4bf7-124">**Operador automático (gratuito)** Número de teléfono gratuito (EE. UU. y Canadá) o gratuito (Reino Unido).</span><span class="sxs-lookup"><span data-stu-id="b4bf7-124">**Auto attendant (Toll Free)** Toll-free (US and Canada) or freephone (UK) phone number.</span></span> <span data-ttu-id="b4bf7-125">Las tarifas de largas distancias se cobran a su empresa.</span><span class="sxs-lookup"><span data-stu-id="b4bf7-125">Long distances fees are charged to your company.</span></span> <span data-ttu-id="b4bf7-126">Para poder seleccionar esta opción, debe comprar créditos de comunicación.</span><span class="sxs-lookup"><span data-stu-id="b4bf7-126">Before you can select this option, you need to purchase Communication Credits.</span></span> <span data-ttu-id="b4bf7-127">Para obtener más información, vea [¿Qué necesito comprar para usar Microsoft 365 Business Voice?](what-to-buy.md).</span><span class="sxs-lookup"><span data-stu-id="b4bf7-127">For more information, see [What do I need to buy to use Microsoft 365 Business Voice?](what-to-buy.md).</span></span>

    3. <span data-ttu-id="b4bf7-128">En **Cantidad**, seleccione **1**.</span><span class="sxs-lookup"><span data-stu-id="b4bf7-128">Under **Quantity**, select **1**.</span></span>
        > [!NOTE]
        > <span data-ttu-id="b4bf7-129">Si recibe el mensaje No tiene licencias **suficientes** para solicitar más números de este tipo, asegúrese de que ha comprado licencias de Business Voice.</span><span class="sxs-lookup"><span data-stu-id="b4bf7-129">If you get the message **You don't have enough licenses to request more numbers of this type**, make sure you've purchased Business Voice licenses.</span></span> <span data-ttu-id="b4bf7-130">Para obtener más información, vea [¿Qué necesito comprar para usar Microsoft 365 Business Voice?](what-to-buy.md).</span><span class="sxs-lookup"><span data-stu-id="b4bf7-130">For more information, see [What do I need to buy to use Microsoft 365 Business Voice?](what-to-buy.md).</span></span>
    4. <span data-ttu-id="b4bf7-131">Elija **Ubicación** **o** Código de área, dependiendo de si desea buscar números de teléfono con la ciudad de una ubicación o si desea buscar números en un código de área específico.</span><span class="sxs-lookup"><span data-stu-id="b4bf7-131">Choose either **Location** or **Area code**, depending on whether you want to search for phone numbers using a location's city, or if you want to search for numbers in a specific area code.</span></span>
    5. <span data-ttu-id="b4bf7-132">Si selecciona **Ubicación:**</span><span class="sxs-lookup"><span data-stu-id="b4bf7-132">If you select **Location**:</span></span>

        1. <span data-ttu-id="b4bf7-133">Escriba la ciudad en la que [](set-up-emergency-locations.md) se encuentra su dirección de emergencia en el paso Configurar ubicaciones de emergencia, o si necesita crear una nueva ubicación para otra oficina o una oficina en el hogar, haga clic en Agregar **una ubicación.**</span><span class="sxs-lookup"><span data-stu-id="b4bf7-133">Type the city in which your emergency address is located in the [Set up emergency locations](set-up-emergency-locations.md) step, or if you need to create a new location for another office or a home office, click **Add a location**.</span></span>
        2. <span data-ttu-id="b4bf7-134">En **Código de área,** seleccione un código de área y, a continuación, **seleccione Siguiente** para reservar el número.</span><span class="sxs-lookup"><span data-stu-id="b4bf7-134">Under **Area code**, select an area code, and then select **Next** to reserve your number.</span></span>

    6. <span data-ttu-id="b4bf7-135">Si selecciona **Código de área**, escriba el código de área que desea buscar y, a continuación, seleccione **Siguiente** para reservar su número.</span><span class="sxs-lookup"><span data-stu-id="b4bf7-135">If you select **Area code**, type the area code you want to search, and then select **Next** to reserve your number.</span></span>

5. <span data-ttu-id="b4bf7-136">Seleccione el número que desee.</span><span class="sxs-lookup"><span data-stu-id="b4bf7-136">Select the number you want.</span></span> <span data-ttu-id="b4bf7-137">Tienes 10 minutos para seleccionar tu número de teléfono y realizar el pedido.</span><span class="sxs-lookup"><span data-stu-id="b4bf7-137">You have 10 minutes to select your phone number and place your order.</span></span> <span data-ttu-id="b4bf7-138">Si lleva más de 10 minutos, el número de teléfono se devolverá al grupo de números.</span><span class="sxs-lookup"><span data-stu-id="b4bf7-138">If you take more than 10 minutes, the phone number will be returned to the pool of numbers.</span></span>
6. <span data-ttu-id="b4bf7-139">Cuando esté listo para realizar el pedido, haga clic **en Realizar pedido** y, a continuación, en **Finalizar**</span><span class="sxs-lookup"><span data-stu-id="b4bf7-139">When you're ready to place your order, click **Place order**, and then **Finish**</span></span>

## <a name="set-up-phone-numbers-for-your-users"></a><span data-ttu-id="b4bf7-140">Configurar números de teléfono para los usuarios</span><span class="sxs-lookup"><span data-stu-id="b4bf7-140">Set up phone numbers for your users</span></span>

1. <span data-ttu-id="b4bf7-141">Abra el Microsoft Teams de administración e inicie sesión con un usuario que sea administrador global (normalmente es la cuenta que usó para registrarse para Microsoft 365).</span><span class="sxs-lookup"><span data-stu-id="b4bf7-141">Open the Microsoft Teams admin center and log in with a user that is a Global admin (this is usually the account you used to sign up for Microsoft 365).</span></span>
2. <span data-ttu-id="b4bf7-142">En el panel de navegación izquierdo, vaya <a href="https://admin.teams.microsoft.com/phone-numbers" target="_blank"> **a Números**  >  **de Teléfono y,**</a>a continuación, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="b4bf7-142">In the left navigation, go to <a href="https://admin.teams.microsoft.com/phone-numbers" target="_blank">**Voice** > **Phone numbers**</a>, and then click **Add**.</span></span>
3. <span data-ttu-id="b4bf7-143">Escriba un nombre para el pedido y agregue una descripción.</span><span class="sxs-lookup"><span data-stu-id="b4bf7-143">Enter a name for the order and add a description.</span></span>
4. <span data-ttu-id="b4bf7-144">En la página Ubicación y cantidad, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b4bf7-144">On the Location and quantity page, do the following:</span></span>

    1. <span data-ttu-id="b4bf7-145">En **País o región,** seleccione un país o región.</span><span class="sxs-lookup"><span data-stu-id="b4bf7-145">Under **Country or region**, select a country or region.</span></span>
    2. <span data-ttu-id="b4bf7-146">En **Tipo de número,** seleccione **Usuario (suscriptor).**</span><span class="sxs-lookup"><span data-stu-id="b4bf7-146">Under **Number type**, select **User (subscriber)**.</span></span>
    3. <span data-ttu-id="b4bf7-147">En **Cantidad**, escriba el número de números que desea para su organización.</span><span class="sxs-lookup"><span data-stu-id="b4bf7-147">Under **Quantity**, enter the number of numbers that you want for your organization.</span></span>
    4. <span data-ttu-id="b4bf7-148">Elija **Ubicación** **o** Código de área, dependiendo de si desea buscar números de teléfono con la ciudad de una ubicación o si desea buscar números en un código de área específico.</span><span class="sxs-lookup"><span data-stu-id="b4bf7-148">Choose either **Location** or **Area code**, depending on whether you want to search for phone numbers using a location's city, or if you want to search for numbers in a specific area code.</span></span>
    5. <span data-ttu-id="b4bf7-149">Si selecciona **Ubicación:**</span><span class="sxs-lookup"><span data-stu-id="b4bf7-149">If you select **Location**:</span></span>

        1. <span data-ttu-id="b4bf7-150">Escriba la ciudad en la que [](set-up-emergency-locations.md) se encuentra su dirección de emergencia en el paso Configurar ubicaciones de emergencia, o si necesita crear una nueva ubicación para otra oficina o una oficina en el hogar, haga clic en Agregar **una ubicación.**</span><span class="sxs-lookup"><span data-stu-id="b4bf7-150">Type the city in which your emergency address is located in the [Set up emergency locations](set-up-emergency-locations.md) step, or if you need to create a new location for another office or a home office, click **Add a location**.</span></span>
        2. <span data-ttu-id="b4bf7-151">En **Código de área,** seleccione un código de área y, a continuación, **seleccione Siguiente** para reservar el número.</span><span class="sxs-lookup"><span data-stu-id="b4bf7-151">Under **Area code**, select an area code, and then select **Next** to reserve your number.</span></span>

    6. <span data-ttu-id="b4bf7-152">Si selecciona **Código de área**, escriba el código de área que desea buscar y, a continuación, seleccione **Siguiente** para reservar su número.</span><span class="sxs-lookup"><span data-stu-id="b4bf7-152">If you select **Area code**, type the area code you want to search, and then select **Next** to reserve your number.</span></span>
5. <span data-ttu-id="b4bf7-153">Seleccione los números que desee.</span><span class="sxs-lookup"><span data-stu-id="b4bf7-153">Select the numbers you want.</span></span> <span data-ttu-id="b4bf7-154">Tienes 10 minutos para seleccionar tus números de teléfono y realizar el pedido.</span><span class="sxs-lookup"><span data-stu-id="b4bf7-154">You have 10 minutes to select your phone numbers and place your order.</span></span> <span data-ttu-id="b4bf7-155">Si lleva más de 10 minutos, los números de teléfono se devolverán al grupo de números.</span><span class="sxs-lookup"><span data-stu-id="b4bf7-155">If you take more than 10 minutes, the phone numbers will be returned to the pool of numbers.</span></span>
6. <span data-ttu-id="b4bf7-156">Cuando esté listo para realizar el pedido, haga clic **en Realizar pedido** y, a continuación, en **Finalizar.**</span><span class="sxs-lookup"><span data-stu-id="b4bf7-156">When you're ready to place your order, click **Place order**, and then **Finish**.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="b4bf7-157">Paso siguiente: Asignar licencias a Teams usuarios</span><span class="sxs-lookup"><span data-stu-id="b4bf7-157">Next step: Assign licenses to Teams users</span></span>](set-up-licenses.md)
