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
ms.openlocfilehash: 6cec0bc8e55ef6be169de1f48a375ab40ca8ccf7
ms.sourcegitcommit: 49cdcf344c63c805bcb6365804c6f5d1393e926a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2021
ms.locfileid: "52130120"
---
# <a name="step-2-set-up-business-voice-phone-numbers"></a><span data-ttu-id="a6e70-103">Paso 2: Configurar números de teléfono de Business Voice</span><span class="sxs-lookup"><span data-stu-id="a6e70-103">Step 2: Set up Business Voice phone numbers</span></span>

<span data-ttu-id="a6e70-104">Para poder configurar usuarios o operadores automáticos en su organización, debe obtener números de teléfono para ellos.</span><span class="sxs-lookup"><span data-stu-id="a6e70-104">Before you can set up users or auto attendants in your organization, you need to get phone numbers for them.</span></span> <span data-ttu-id="a6e70-105">Hay varios tipos diferentes de números de teléfono, pero los siguientes son los dos tipos de números que necesita agregar en este paso:</span><span class="sxs-lookup"><span data-stu-id="a6e70-105">There are several different types of phone numbers, however the following are the two types of numbers that you need to add in this step:</span></span>

- <span data-ttu-id="a6e70-106">**Números de servicio** Estos números se usan para operadores automáticos, audioconferencias y colas de llamadas.</span><span class="sxs-lookup"><span data-stu-id="a6e70-106">**Service numbers** These numbers are used for auto attendants, audio conferencing, and call queues.</span></span> <span data-ttu-id="a6e70-107">Pueden ser números gratuitos o de pago y pueden atender grandes cantidades de llamadas al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="a6e70-107">They can be toll or toll-free numbers and can handle large amounts of calls at the same time.</span></span> <span data-ttu-id="a6e70-108">El número de teléfono de su empresa debe ser un número de servicio porque se asignará a un operador automático en un paso posterior.</span><span class="sxs-lookup"><span data-stu-id="a6e70-108">Your company phone number needs to be a service number because it'll be assigned to an auto attendant in a later step.</span></span>
- <span data-ttu-id="a6e70-109">**Números de suscriptor** Estos números se usan para los usuarios normales para que puedan realizar y recibir llamadas telefónicas.</span><span class="sxs-lookup"><span data-stu-id="a6e70-109">**Subscriber numbers** These numbers are used for regular users so they can make and receive phone calls.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a6e70-110">Incluso si desea usar los números de teléfono existentes, debe crear y asignar números de teléfono temporales a la línea telefónica principal de su empresa y a sus usuarios.</span><span class="sxs-lookup"><span data-stu-id="a6e70-110">Even if you want to use your existing phone numbers, you need to create and assign temporary phone numbers to your company's main phone line and your users.</span></span> <span data-ttu-id="a6e70-111">Podrá reemplazar estos números temporales por los números de teléfono existentes en un paso posterior.</span><span class="sxs-lookup"><span data-stu-id="a6e70-111">You'll be able to replace these temporary numbers with your existing phone numbers in a later step.</span></span>

> [!NOTE]
> <span data-ttu-id="a6e70-112">Los nuevos números de teléfono pueden tardar varias horas en estar disponibles en Teams.</span><span class="sxs-lookup"><span data-stu-id="a6e70-112">It may take several hours for your new phone numbers to become available in Teams.</span></span>

## <a name="set-up-a-service-number"></a><span data-ttu-id="a6e70-113">Configurar un número de servicio</span><span class="sxs-lookup"><span data-stu-id="a6e70-113">Set up a service number</span></span>

<span data-ttu-id="a6e70-114">El número de servicio que configure ahora se usará en un paso posterior para el número de teléfono principal de su empresa.</span><span class="sxs-lookup"><span data-stu-id="a6e70-114">The service number you set up now will be used in a later step for your company's main phone number.</span></span>

1. <span data-ttu-id="a6e70-115">Vaya al Centro Microsoft Teams administración.</span><span class="sxs-lookup"><span data-stu-id="a6e70-115">Go to the Microsoft Teams Admin Center.</span></span>
2. <span data-ttu-id="a6e70-116">En el panel de navegación izquierdo, vaya **a Números** de Teléfono  >  **y,** a continuación, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="a6e70-116">In the left navigation, go to **Voice** > **Phone numbers**, and then click **Add**.</span></span>
3. <span data-ttu-id="a6e70-117">Escriba un nombre para el pedido y agregue una descripción.</span><span class="sxs-lookup"><span data-stu-id="a6e70-117">Enter a name for the order and add a description.</span></span>
4. <span data-ttu-id="a6e70-118">En la página Ubicación y cantidad, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="a6e70-118">On the Location and quantity page, do the following:</span></span>
    1. <span data-ttu-id="a6e70-119">En **País o región,** seleccione un país o región.</span><span class="sxs-lookup"><span data-stu-id="a6e70-119">Under **Country or region**, select a country or region.</span></span>
    2. <span data-ttu-id="a6e70-120">En **Tipo de número**, seleccione una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="a6e70-120">Under **Number type**, select one of the following options:</span></span>

        - <span data-ttu-id="a6e70-121">**Operador automático (pago)** Número de teléfono normal, no gratuito.</span><span class="sxs-lookup"><span data-stu-id="a6e70-121">**Auto attendant (Toll)** Regular, non-toll-free, phone number.</span></span> <span data-ttu-id="a6e70-122">Las tarifas de larga distancia se cobran al autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="a6e70-122">Long distance fees are charged to the caller.</span></span>
        - <span data-ttu-id="a6e70-123">**Operador automático (gratuito)** Número de teléfono gratuito (EE. UU. y Canadá) o gratuito (Reino Unido).</span><span class="sxs-lookup"><span data-stu-id="a6e70-123">**Auto attendant (Toll Free)** Toll-free (US and Canada) or freephone (UK) phone number.</span></span> <span data-ttu-id="a6e70-124">Las tarifas de largas distancias se cobran a su empresa.</span><span class="sxs-lookup"><span data-stu-id="a6e70-124">Long distances fees are charged to your company.</span></span> <span data-ttu-id="a6e70-125">Para poder seleccionar esta opción, debe comprar créditos de comunicación.</span><span class="sxs-lookup"><span data-stu-id="a6e70-125">Before you can select this option, you need to purchase Communication Credits.</span></span> <span data-ttu-id="a6e70-126">Para obtener más información, vea [¿Qué necesito comprar para usar Microsoft 365 Business Voice?](what-to-buy.md).</span><span class="sxs-lookup"><span data-stu-id="a6e70-126">For more information, see [What do I need to buy to use Microsoft 365 Business Voice?](what-to-buy.md).</span></span>

    3. <span data-ttu-id="a6e70-127">En **Cantidad**, seleccione **1**.</span><span class="sxs-lookup"><span data-stu-id="a6e70-127">Under **Quantity**, select **1**.</span></span>
        > [!NOTE]
        > <span data-ttu-id="a6e70-128">Si recibe el mensaje No tiene licencias **suficientes** para solicitar más números de este tipo, asegúrese de que ha comprado licencias de Business Voice.</span><span class="sxs-lookup"><span data-stu-id="a6e70-128">If you get the message **You don't have enough licenses to request more numbers of this type**, make sure you've purchased Business Voice licenses.</span></span> <span data-ttu-id="a6e70-129">Para obtener más información, vea [¿Qué necesito comprar para usar Microsoft 365 Business Voice?](what-to-buy.md).</span><span class="sxs-lookup"><span data-stu-id="a6e70-129">For more information, see [What do I need to buy to use Microsoft 365 Business Voice?](what-to-buy.md).</span></span>
    4. <span data-ttu-id="a6e70-130">En **Ubicación**, escriba el nombre de la ubicación que creó en el paso [Configurar ubicaciones de](set-up-emergency-locations.md) emergencia.</span><span class="sxs-lookup"><span data-stu-id="a6e70-130">Under **Location**, type the name of the location you created in the [Set up emergency locations](set-up-emergency-locations.md) step.</span></span>
    5. <span data-ttu-id="a6e70-131">En **Código de área**, seleccione un código de área y, a continuación, haga clic en **Siguiente** para seleccionar los números</span><span class="sxs-lookup"><span data-stu-id="a6e70-131">Under **Area code**, select an area code, and then click **Next** to select your numbers</span></span>
5. <span data-ttu-id="a6e70-132">Seleccione el número que desee.</span><span class="sxs-lookup"><span data-stu-id="a6e70-132">Select the number you want.</span></span> <span data-ttu-id="a6e70-133">Tienes 10 minutos para seleccionar tu número de teléfono y realizar el pedido.</span><span class="sxs-lookup"><span data-stu-id="a6e70-133">You have 10 minutes to select your phone number and place your order.</span></span> <span data-ttu-id="a6e70-134">Si lleva más de 10 minutos, el número de teléfono se devolverá al grupo de números.</span><span class="sxs-lookup"><span data-stu-id="a6e70-134">If you take more than 10 minutes, the phone number will be returned to the pool of numbers.</span></span>
6. <span data-ttu-id="a6e70-135">Cuando esté listo para realizar el pedido, haga clic **en Realizar pedido** y, a continuación, en **Finalizar**</span><span class="sxs-lookup"><span data-stu-id="a6e70-135">When you're ready to place your order, click **Place order**, and then **Finish**</span></span>

## <a name="set-up-phone-numbers-for-your-users"></a><span data-ttu-id="a6e70-136">Configurar números de teléfono para los usuarios</span><span class="sxs-lookup"><span data-stu-id="a6e70-136">Set up phone numbers for your users</span></span>

1. <span data-ttu-id="a6e70-137">Vaya al Centro Microsoft Teams administración.</span><span class="sxs-lookup"><span data-stu-id="a6e70-137">Go to the Microsoft Teams Admin Center.</span></span>
2. <span data-ttu-id="a6e70-138">En el panel de navegación izquierdo, vaya **a Números** de Teléfono  >  **y,** a continuación, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="a6e70-138">In the left navigation, go to **Voice** > **Phone numbers**, and then click **Add**.</span></span>
3. <span data-ttu-id="a6e70-139">Escriba un nombre para el pedido y agregue una descripción.</span><span class="sxs-lookup"><span data-stu-id="a6e70-139">Enter a name for the order and add a description.</span></span>
4. <span data-ttu-id="a6e70-140">En la página Ubicación y cantidad, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="a6e70-140">On the Location and quantity page, do the following:</span></span>

    1. <span data-ttu-id="a6e70-141">En **País o región,** seleccione un país o región.</span><span class="sxs-lookup"><span data-stu-id="a6e70-141">Under **Country or region**, select a country or region.</span></span>
    2. <span data-ttu-id="a6e70-142">En **Tipo de número,** seleccione **Usuario (suscriptor).**</span><span class="sxs-lookup"><span data-stu-id="a6e70-142">Under **Number type**, select **User (subscriber)**.</span></span>
    3. <span data-ttu-id="a6e70-143">En **Cantidad**, escriba el número de números que desea para su organización.</span><span class="sxs-lookup"><span data-stu-id="a6e70-143">Under **Quantity**, enter the number of numbers that you want for your organization.</span></span>
    4. <span data-ttu-id="a6e70-144">En **Ubicación**, seleccione una ubicación.</span><span class="sxs-lookup"><span data-stu-id="a6e70-144">Under **Location**, select a location.</span></span> <span data-ttu-id="a6e70-145">Puede seleccionar la ubicación de emergencia [](set-up-emergency-locations.md) que agregó en el paso Configurar ubicaciones de emergencia, o si necesita crear una nueva ubicación para otra oficina o una oficina principal, haga clic en Agregar **una ubicación.**</span><span class="sxs-lookup"><span data-stu-id="a6e70-145">You can select either the emergency location you added in the [Set up emergency locations](set-up-emergency-locations.md) step, or if you need to create a new location for another office or a home office, click **Add a location**.</span></span>
    5. <span data-ttu-id="a6e70-146">En **Código de área,** seleccione un código de área y, a continuación, haga clic **en Siguiente** para seleccionar los números.</span><span class="sxs-lookup"><span data-stu-id="a6e70-146">Under **Area code**, select an area code, and then click **Next** to select your numbers.</span></span>
5. <span data-ttu-id="a6e70-147">Seleccione los números que desee.</span><span class="sxs-lookup"><span data-stu-id="a6e70-147">Select the numbers you want.</span></span> <span data-ttu-id="a6e70-148">Tienes 10 minutos para seleccionar tus números de teléfono y realizar el pedido.</span><span class="sxs-lookup"><span data-stu-id="a6e70-148">You have 10 minutes to select your phone numbers and place your order.</span></span> <span data-ttu-id="a6e70-149">Si lleva más de 10 minutos, los números de teléfono se devolverán al grupo de números.</span><span class="sxs-lookup"><span data-stu-id="a6e70-149">If you take more than 10 minutes, the phone numbers will be returned to the pool of numbers.</span></span>
6. <span data-ttu-id="a6e70-150">Cuando esté listo para realizar el pedido, haga clic **en Realizar pedido** y, a continuación, en **Finalizar.**</span><span class="sxs-lookup"><span data-stu-id="a6e70-150">When you're ready to place your order, click **Place order**, and then **Finish**.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="a6e70-151">Paso siguiente: Asignar licencias a Teams usuarios</span><span class="sxs-lookup"><span data-stu-id="a6e70-151">Next step: Assign licenses to Teams users</span></span>](set-up-licenses.md)
