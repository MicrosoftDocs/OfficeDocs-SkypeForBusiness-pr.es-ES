---
title: Configuración de la licencia de teléfono de área común de Microsoft Teams
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.date: 12/13/2018
ms.reviewer: kponnus
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- M365-voice
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: 'Obtenga información sobre cómo configurar los teléfonos de área común para salas de espera, áreas de recepción y salas de conferencias '
ms.openlocfilehash: 9e68d5bc4ef0355e80e1fe6359385c10a339c0fe
ms.sourcegitcommit: cf2cb5b7e03385b33e34a5ff89719adb882525b1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2019
ms.locfileid: "33632380"
---
# <a name="set-up-the-common-area-phone-license-for-microsoft-teams"></a><span data-ttu-id="53a07-103">Configuración de la licencia de teléfono de área común de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="53a07-103">Set up the Common Area Phone license for Microsoft Teams</span></span>

<span data-ttu-id="53a07-104">Un teléfono de área común normalmente se coloca en un área como una sala de espera o a otra área que se encuentra disponible a varias personas para realizar una llamada; Por ejemplo, una recepción área, sala de espera o conferencia telefónica.</span><span class="sxs-lookup"><span data-stu-id="53a07-104">A common area phone is typically placed in an area like a lobby or another area which is available to many people to make a call; for example, a reception area, lobby, or conference phone.</span></span> <span data-ttu-id="53a07-105">Teléfonos de área común se configuran como dispositivos en lugar de los usuarios y pueden iniciar sesión automáticamente en una red.</span><span class="sxs-lookup"><span data-stu-id="53a07-105">Common area phones are set up as devices rather than users, and can automatically sign into a network.</span></span>

<span data-ttu-id="53a07-106">En los pasos siguientes, le ayudaremos a configurar una cuenta para el sistema telefónico implementar teléfonos de área común para su organización.</span><span class="sxs-lookup"><span data-stu-id="53a07-106">In the steps below, we’ll help you set up an account for Phone System to deploy common area phones for your organization.</span></span> <span data-ttu-id="53a07-107">Para una sala de reuniones más completa experiencia, incluyendo conferencias de audio, considere la posibilidad de adquirir la licencia de sala de reuniones dedicada con una reunión de dispositivo de sala.</span><span class="sxs-lookup"><span data-stu-id="53a07-107">For a more complete meeting room experience, including audio conferencing, consider purchasing the dedicated Meeting Room license with a meeting room device.</span></span> 

<span data-ttu-id="53a07-108">Las primeras cosas que debe hacer son compra una licencia de teléfono de área común (CAP) y asegúrese de que tiene un teléfono certificado.</span><span class="sxs-lookup"><span data-stu-id="53a07-108">The first things you need to do are purchase a Common Area Phone (CAP) license and make sure that you have a certified phone.</span></span> <span data-ttu-id="53a07-109">Para buscar y obtener más información sobre certificados teléfonos, vaya a [los dispositivos de los equipos de Microsoft](https://products.office.com/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1).</span><span class="sxs-lookup"><span data-stu-id="53a07-109">To search for and learn more about certified phones, go to [Microsoft Teams devices](https://products.office.com/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1).</span></span> 

## <a name="step-1---buy-the-licenses"></a><span data-ttu-id="53a07-110">Paso 1: comprar las licencias</span><span class="sxs-lookup"><span data-stu-id="53a07-110">Step 1 - Buy the licenses</span></span>

1. <span data-ttu-id="53a07-111">En el centro de administración de Microsoft 365, vaya a **facturación** > **Servicios de compra** y, a continuación, expanda **otros planes**.</span><span class="sxs-lookup"><span data-stu-id="53a07-111">In the Microsoft 365 admin center, go to **Billing** > **Purchase services** and then expand **Other plans**.</span></span>

    ![Captura de pantalla que muestra el icono de teléfono de área común](media/set-up-common-area-phone-image1.png)

2. <span data-ttu-id="53a07-113">Seleccione **teléfono de área común** > **comprar ahora**.</span><span class="sxs-lookup"><span data-stu-id="53a07-113">Select **Common Area Phone** > **Buy now**.</span></span>

3. <span data-ttu-id="53a07-114">En la página de **finalización de compra** , haga clic en **comprar ahora**.</span><span class="sxs-lookup"><span data-stu-id="53a07-114">On the **Checkout** page click **Buy now**.</span></span>

4. <span data-ttu-id="53a07-115">Expanda **las suscripciones del complemento** y, a continuación, haga clic en para adquirir un Plan de llamada.</span><span class="sxs-lookup"><span data-stu-id="53a07-115">Expand **Add-on subscriptions** and then click to buy a Calling Plan.</span></span> <span data-ttu-id="53a07-116">Elija la **nacionales llamar al Plan** o la **planeación de la llamada nacional e internacional**.</span><span class="sxs-lookup"><span data-stu-id="53a07-116">Choose either the **Domestic Calling Plan** or **Domestic and International Calling Plan**.</span></span>

> [!NOTE]
> <span data-ttu-id="53a07-117">No necesita una licencia de sistema telefónico.</span><span class="sxs-lookup"><span data-stu-id="53a07-117">You don't need a Phone System license.</span></span> <span data-ttu-id="53a07-118">Está incluida en la licencia del teléfono de área común.</span><span class="sxs-lookup"><span data-stu-id="53a07-118">It's included with the Common Area Phone license.</span></span>

<span data-ttu-id="53a07-119">Para obtener más información sobre las licencias, vea [licencias de complemento de equipos de Microsoft](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="53a07-119">For more information on licenses, see [Microsoft Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>

## <a name="step-2---create-a-new-user-account-for-the-phone-and-assign-the-licenses"></a><span data-ttu-id="53a07-120">Paso 2: crear una nueva cuenta de usuario para el teléfono y asignar las licencias</span><span class="sxs-lookup"><span data-stu-id="53a07-120">Step 2 - Create a new user account for the phone and assign the licenses</span></span>

1. <span data-ttu-id="53a07-121">En el centro de administración de Microsoft 365, vaya a **los usuarios** > **usuarios activos** > **Agregar un usuario**.</span><span class="sxs-lookup"><span data-stu-id="53a07-121">In the Microsoft 365 admin center, go to **users** > **active users** > **add a user**.</span></span>

2. <span data-ttu-id="53a07-122">Escriba un nombre de usuario como "Main" para el nombre y el "Recepción" para el segundo nombre.</span><span class="sxs-lookup"><span data-stu-id="53a07-122">Enter a user name like “Main" for the first name and "Reception” for the second name.</span></span>

3. <span data-ttu-id="53a07-123">Escriba un nombre para mostrar si no es así generar automáticamente como "Main recepción".</span><span class="sxs-lookup"><span data-stu-id="53a07-123">Enter a display name if it doesn't autogenerate one like "Main Reception."</span></span>

4. <span data-ttu-id="53a07-124">Escriba un nombre de usuario, como "MainReception" o "Mainlobby".</span><span class="sxs-lookup"><span data-stu-id="53a07-124">Enter a user name like "MainReception" or "Mainlobby."</span></span>

5. <span data-ttu-id="53a07-125">Para teléfonos de área común, es posible que desee establecer una contraseña manualmente o tener la misma contraseña para todos los teléfonos de área común.</span><span class="sxs-lookup"><span data-stu-id="53a07-125">For common area phones, you might want to set a password manually or have the same password for all your common area phones.</span></span> <span data-ttu-id="53a07-126">Además, es posible que piense desactivando la casilla de verificación **hacer que este usuario cambiar su contraseña cuando inician sesión por primera vez en** .</span><span class="sxs-lookup"><span data-stu-id="53a07-126">Also, you might think about clearing the **Make this user change their password when they first sign in** check box.</span></span>

6. <span data-ttu-id="53a07-127">Asignar las licencias al usuario.</span><span class="sxs-lookup"><span data-stu-id="53a07-127">Assign the licenses to the user.</span></span> <span data-ttu-id="53a07-128">En la misma página, haga clic para expandir las **Licencias de producto**.</span><span class="sxs-lookup"><span data-stu-id="53a07-128">On the same page, click to expand **Product licenses**.</span></span> <span data-ttu-id="53a07-129">Encienda el teléfono de área común y seleccionar un **Llamar a planear nacionales** o un **nacionales y llamar a planear internacional**.</span><span class="sxs-lookup"><span data-stu-id="53a07-129">Turn on the Common Area Phone and pick either a **Domestic Calling Plan** or a **Domestic and International Calling Plan**.</span></span> 

    ![Asignación de licencias de captura de pantalla que muestra](media/set-up-common-area-phone-image2.png)

<span data-ttu-id="53a07-131">Para obtener más información, vea [Agregar un usuario](https://docs.microsoft.com/office365/admin/add-users/add-users?redirectSourcePath=%252farticle%252f1970f7d6-03b5-442f-b385-5880b9c256ec&view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="53a07-131">For more information, see [Add a user](https://docs.microsoft.com/office365/admin/add-users/add-users?redirectSourcePath=%252farticle%252f1970f7d6-03b5-442f-b385-5880b9c256ec&view=o365-worldwide).</span></span>

## <a name="step-3---assign-a-phone-number-to-the-common-area-phone-user-account"></a><span data-ttu-id="53a07-132">Paso 3: asignar un número de teléfono a la cuenta de usuario del teléfono de área común</span><span class="sxs-lookup"><span data-stu-id="53a07-132">Step 3 - Assign a phone number to the Common Area Phone user account</span></span>

<span data-ttu-id="53a07-133">Use el Skype para el centro de administración de negocio para asignar a un número al usuario.</span><span class="sxs-lookup"><span data-stu-id="53a07-133">Use the Skype for Business admin center to assign a number to the user.</span></span>

1. <span data-ttu-id="53a07-134">En el centro de administración de Microsoft 365, seleccione **centros de administración** > **& equipos Skype** > **portal heredado**.</span><span class="sxs-lookup"><span data-stu-id="53a07-134">In the Microsoft 365 admin center, select **Admin centers** > **Teams & Skype** > **Legacy portal**.</span></span>

2. <span data-ttu-id="53a07-135">En Skype para el centro de administración de negocio, seleccione **voz** > **los números de teléfono**.</span><span class="sxs-lookup"><span data-stu-id="53a07-135">In the Skype for Business admin center, select **Voice** > **Phone numbers**.</span></span>

3.  <span data-ttu-id="53a07-136">Seleccione un número de la lista de números de teléfono y haga clic en **Asignar**.</span><span class="sxs-lookup"><span data-stu-id="53a07-136">Select a number from the list of phone numbers and click **Assign**.</span></span>

4. <span data-ttu-id="53a07-137">En la página **asignar** , en el cuadro de usuario de voz, escriba el nombre del usuario que va a utilizar el teléfono y, a continuación, seleccione el usuario en la lista desplegable **Seleccione un usuario de voz** .</span><span class="sxs-lookup"><span data-stu-id="53a07-137">On the **Assign** page, in the Voice user box, type the name of the user who will be using the phone, and then select the user in the **Select a voice user** drop-down list.</span></span>

5. <span data-ttu-id="53a07-138">Allí deberá agregar también una dirección de emergencia.</span><span class="sxs-lookup"><span data-stu-id="53a07-138">While you're there you will need to add an emergency address.</span></span> <span data-ttu-id="53a07-139">Elija **Buscar por ciudad**, **Buscar por descripción**o **Buscar por ubicación** de la lista desplegable y, a continuación, escriba la ciudad, la descripción o la ubicación en el cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="53a07-139">Choose **Search by city**, **Search by description**, or **Search by location** from the drop-down list, and then enter the city, description, or location in the text box.</span></span> <span data-ttu-id="53a07-140">Una vez que buscar, mire en **Seleccione emergencia dirección** para elegir el adecuado para usted.</span><span class="sxs-lookup"><span data-stu-id="53a07-140">Once you search, look under **Select emergency address** to pick the right one for you.</span></span>

6. <span data-ttu-id="53a07-141">Haga clic en **Guardar** y el usuario debería tener este aspecto:</span><span class="sxs-lookup"><span data-stu-id="53a07-141">Click **Save** and your user should look like this:</span></span>

   ![Asignación de licencias de captura de pantalla que muestra](media/set-up-common-area-phone-image3.png)

> [!NOTE]
> <span data-ttu-id="53a07-143">Los usuarios sólo aparecerá si cuentan con una licencia de sistema telefónico aplicada.</span><span class="sxs-lookup"><span data-stu-id="53a07-143">Users will only show up if they have a Phone System license applied.</span></span> <span data-ttu-id="53a07-144">Si acaba de aplicársela, el usuario a veces tarda un poco de tiempo en aparecer en la lista.</span><span class="sxs-lookup"><span data-stu-id="53a07-144">If you just did this, then sometimes it takes a bit for the user to show up in the list.</span></span>

<span data-ttu-id="53a07-145">Para obtener más información, vea la [Introducción de los números de teléfono para los usuarios](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/getting-phone-numbers-for-your-users).</span><span class="sxs-lookup"><span data-stu-id="53a07-145">For more information, see [Getting phone numbers for your users](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/getting-phone-numbers-for-your-users).</span></span>

<span data-ttu-id="53a07-146">También puede tomarse su número de teléfono que tiene con otro operador y "puerto" o transferir a través de Office 365.</span><span class="sxs-lookup"><span data-stu-id="53a07-146">You can also take your phone number that you have with another carrier and "port" or transfer it over to Office 365.</span></span> <span data-ttu-id="53a07-147">Consulte [transferir los números de teléfono para Office 365](transfer-phone-numbers-to-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="53a07-147">See [Transfer phone numbers to Office 365](transfer-phone-numbers-to-office-365.md).</span></span>


