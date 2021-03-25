---
title: Configurar la licencia de Teléfono de área común
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 12/13/2018
ms.reviewer: kponnus
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Phone System
- seo-marvel-mar2020
description: 'Obtenga información sobre cómo configurar teléfonos de área común para lobbies, áreas de recepción y salas de conferencias '
ms.openlocfilehash: bb17b21eac262c160abc3e16a4b552fb32b97d00
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117118"
---
# <a name="set-up-the-common-area-phone-license-for-microsoft-teams"></a><span data-ttu-id="f3e49-103">Configuración de la licencia de teléfono de área común de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f3e49-103">Set up the Common Area Phone license for Microsoft Teams</span></span>
> [!NOTE]
> <span data-ttu-id="f3e49-104">Los teléfonos de área común no admiten correo de voz.</span><span class="sxs-lookup"><span data-stu-id="f3e49-104">Common area phones do not support voicemail.</span></span>

<span data-ttu-id="f3e49-105">Un teléfono de área común normalmente se coloca en un área como una sala de espera u otra área que está disponible para muchas personas para realizar una llamada; por ejemplo, un área de recepción, una sala de espera o un teléfono de conferencia.</span><span class="sxs-lookup"><span data-stu-id="f3e49-105">A common area phone is typically placed in an area like a lobby or another area that is available to many people to make a call; for example, a reception area, lobby, or conference phone.</span></span> <span data-ttu-id="f3e49-106">Los teléfonos de área común se han iniciado sesión con cuentas vinculadas a una licencia de teléfono de área común.</span><span class="sxs-lookup"><span data-stu-id="f3e49-106">Common area phones are signed in with accounts tied to a Common Area Phone license.</span></span> <span data-ttu-id="f3e49-107">La directiva teamsIPPhone también debe establecerse correctamente para que el teléfono tenga una experiencia de usuario de área común.</span><span class="sxs-lookup"><span data-stu-id="f3e49-107">The TeamsIPPhone policy must also be appropriately set for the phone to have a common area user experience.</span></span>

<span data-ttu-id="f3e49-108">En los pasos siguientes, le ayudaremos a configurar una cuenta de Sistema telefónico para implementar teléfonos de área comunes para su organización.</span><span class="sxs-lookup"><span data-stu-id="f3e49-108">In the steps below, we'll help you set up an account for Phone System to deploy common area phones for your organization.</span></span> <span data-ttu-id="f3e49-109">Para obtener una experiencia más completa de la sala de reuniones, incluidas las audioconferencias, considere la posibilidad de comprar la licencia dedicada de la sala de reuniones con un dispositivo de sala de reuniones.</span><span class="sxs-lookup"><span data-stu-id="f3e49-109">For a more complete meeting room experience, including audio conferencing, consider purchasing the dedicated Meeting Room license with a meeting room device.</span></span> 

<span data-ttu-id="f3e49-110">En primer lugar, debe comprar una licencia de Teléfono de área común (CAP) y asegurarse de que tiene un teléfono certificado.</span><span class="sxs-lookup"><span data-stu-id="f3e49-110">First, you need to purchase a Common Area Phone (CAP) license and make sure that you have a certified phone.</span></span> <span data-ttu-id="f3e49-111">Para buscar y obtener más información sobre teléfonos certificados, vaya a [Dispositivos de Microsoft Teams.](https://products.office.com/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1)</span><span class="sxs-lookup"><span data-stu-id="f3e49-111">To search for and learn more about certified phones, go to [Microsoft Teams devices](https://products.office.com/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1).</span></span> 

## <a name="step-1---buy-the-licenses"></a><span data-ttu-id="f3e49-112">Paso 1: comprar las licencias</span><span class="sxs-lookup"><span data-stu-id="f3e49-112">Step 1 - Buy the licenses</span></span>

1. <span data-ttu-id="f3e49-113">En el Centro de administración de Microsoft 365, vaya a Servicios **de** compra de  >  **facturación** y, a continuación, expanda **Otros planes.**</span><span class="sxs-lookup"><span data-stu-id="f3e49-113">In the Microsoft 365 admin center, go to **Billing** > **Purchase services** and then expand **Other plans**.</span></span>

    ![Captura de pantalla que muestra el icono Teléfono de área común](media/set-up-common-area-phone-image1.png)

2. <span data-ttu-id="f3e49-115">Selecciona **Comprar teléfono de área** común  >  **ahora.**</span><span class="sxs-lookup"><span data-stu-id="f3e49-115">Select **Common Area Phone** > **Buy now**.</span></span>

3. <span data-ttu-id="f3e49-116">En la página Desprotección, haga clic **en Comprar ahora.**</span><span class="sxs-lookup"><span data-stu-id="f3e49-116">On the Checkout page, click **Buy now**.</span></span>

4. <span data-ttu-id="f3e49-117">Expanda **Suscripciones de complementos y,** a continuación, haga clic para comprar un plan de llamadas.</span><span class="sxs-lookup"><span data-stu-id="f3e49-117">Expand **Add-on subscriptions** and then click to buy a Calling Plan.</span></span> <span data-ttu-id="f3e49-118">Elija el Plan **de llamadas nacionales** o el Plan **de llamadas nacionales e internacionales.**</span><span class="sxs-lookup"><span data-stu-id="f3e49-118">Choose either the **Domestic Calling Plan** or **Domestic and International Calling Plan**.</span></span>

> [!NOTE]
> <span data-ttu-id="f3e49-119">Si usa Enrutamiento directo de Microsoft Phone System, no necesita una licencia del Plan de llamadas.</span><span class="sxs-lookup"><span data-stu-id="f3e49-119">If you are using Microsoft Phone System Direct Routing, you do not need a Calling Plan license.</span></span>

> [!NOTE]
> <span data-ttu-id="f3e49-120">No es necesario agregar una licencia del sistema telefónico.</span><span class="sxs-lookup"><span data-stu-id="f3e49-120">You don't need to add a Phone System license.</span></span> <span data-ttu-id="f3e49-121">Está incluida en la licencia del teléfono de área común.</span><span class="sxs-lookup"><span data-stu-id="f3e49-121">It's included with the Common Area Phone license.</span></span>

<span data-ttu-id="f3e49-122">Para obtener más información sobre licencias, vea [Licencias de complementos de Microsoft Teams.](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)</span><span class="sxs-lookup"><span data-stu-id="f3e49-122">For more information on licenses, see [Microsoft Teams add-on licensing](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>

<span data-ttu-id="f3e49-123">La licencia de Teléfono de área común es compatible con:</span><span class="sxs-lookup"><span data-stu-id="f3e49-123">The Common Area Phone license supports:</span></span> 


|   |  <span data-ttu-id="f3e49-124">Teléfono de área común</span><span class="sxs-lookup"><span data-stu-id="f3e49-124">Common Area Phone</span></span>  |
|---------|---------|
|<span data-ttu-id="f3e49-125">Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="f3e49-125">Skype for Business</span></span> |   <span data-ttu-id="f3e49-126">&#x2714;</span><span class="sxs-lookup"><span data-stu-id="f3e49-126">&#x2714;</span></span> |
|<span data-ttu-id="f3e49-127">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f3e49-127">Microsoft Teams</span></span> |   <span data-ttu-id="f3e49-128">&#x2714;</span><span class="sxs-lookup"><span data-stu-id="f3e49-128">&#x2714;</span></span> |
|<span data-ttu-id="f3e49-129">Sistema telefónico</span><span class="sxs-lookup"><span data-stu-id="f3e49-129">Phone System</span></span> |    <span data-ttu-id="f3e49-130">&#x2714;</span><span class="sxs-lookup"><span data-stu-id="f3e49-130">&#x2714;</span></span> |
|<span data-ttu-id="f3e49-131">Audioconferencia</span><span class="sxs-lookup"><span data-stu-id="f3e49-131">Audio Conferencing</span></span> |       <span data-ttu-id="f3e49-132">&#x2718; &sup1;</span><span class="sxs-lookup"><span data-stu-id="f3e49-132">&#x2718; &sup1;</span></span>  |
|<span data-ttu-id="f3e49-133">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="f3e49-133">Microsoft Intune</span></span> |    <span data-ttu-id="f3e49-134">&#x2718;</span><span class="sxs-lookup"><span data-stu-id="f3e49-134">&#x2718;</span></span> |
|<span data-ttu-id="f3e49-135">Disponibilidad mundial</span><span class="sxs-lookup"><span data-stu-id="f3e49-135">Worldwide Availability</span></span> |       <span data-ttu-id="f3e49-136">&#x2718; &sup2;</span><span class="sxs-lookup"><span data-stu-id="f3e49-136">&#x2718; &sup2;</span></span>  |
|<span data-ttu-id="f3e49-137">Disponibilidad del canal</span><span class="sxs-lookup"><span data-stu-id="f3e49-137">Channel Availability</span></span> |    <span data-ttu-id="f3e49-138">EA, EAS, CSP, GCC, EES, Web Direct</span><span class="sxs-lookup"><span data-stu-id="f3e49-138">EA, EAS, CSP, GCC, EES, Web Direct</span></span>  |
|      |         |

<span data-ttu-id="f3e49-139">&sup1; Los teléfonos de área común pueden unirse a conferencias de audio a través del número de acceso telefónico proporcionado por el organizador de la reunión</span><span class="sxs-lookup"><span data-stu-id="f3e49-139">&sup1; Common Area Phones can join audio conferences via dial-in number provided by the meeting organizer</span></span>

<span data-ttu-id="f3e49-140">&sup2; No disponible en nubes soberanas</span><span class="sxs-lookup"><span data-stu-id="f3e49-140">&sup2; Not available in sovereign clouds</span></span>  



## <a name="step-2---create-a-new-user-account-for-the-phone-and-assign-the-licenses"></a><span data-ttu-id="f3e49-141">Paso 2: crear una nueva cuenta de usuario para el teléfono y asignar las licencias</span><span class="sxs-lookup"><span data-stu-id="f3e49-141">Step 2 - Create a new user account for the phone and assign the licenses</span></span>

1. <span data-ttu-id="f3e49-142">En el Centro de administración de Microsoft 365, vaya a **Usuarios**  >  **usuarios activos** agregar un  >  **usuario.**</span><span class="sxs-lookup"><span data-stu-id="f3e49-142">In the Microsoft 365 admin center, go to **users** > **active users** > **add a user**.</span></span>

2. <span data-ttu-id="f3e49-143">Escriba un nombre de usuario como "Principal" para el nombre y "Recepción" para el segundo nombre.</span><span class="sxs-lookup"><span data-stu-id="f3e49-143">Enter a user name like "Main" for the first name and "Reception" for the second name.</span></span>

3. <span data-ttu-id="f3e49-144">Escriba un nombre para mostrar si no genera automáticamente uno como "Recepción principal".</span><span class="sxs-lookup"><span data-stu-id="f3e49-144">Enter a display name if it doesn't autogenerate one like "Main Reception."</span></span>

4. <span data-ttu-id="f3e49-145">Escriba un nombre de usuario como "MainReception" o "Mainlobby".</span><span class="sxs-lookup"><span data-stu-id="f3e49-145">Enter a user name like "MainReception" or "Mainlobby."</span></span>

5. <span data-ttu-id="f3e49-146">Para teléfonos de área común, es posible que desee establecer una contraseña manualmente o tener la misma contraseña para todos los teléfonos de área comunes.</span><span class="sxs-lookup"><span data-stu-id="f3e49-146">For common area phones, you might want to set a password manually or have the same password for all your common area phones.</span></span> <span data-ttu-id="f3e49-147">Además, es posible que piense en desactivar la casilla Hacer que este **usuario cambie su contraseña** al iniciar sesión por primera vez.</span><span class="sxs-lookup"><span data-stu-id="f3e49-147">Also, you might think about clearing the **Make this user change their password when they first sign in** check box.</span></span>

6. <span data-ttu-id="f3e49-148">Asigne las licencias al usuario.</span><span class="sxs-lookup"><span data-stu-id="f3e49-148">Assign the licenses to the user.</span></span> <span data-ttu-id="f3e49-149">En la misma página, haga clic para expandir las **Licencias de producto**.</span><span class="sxs-lookup"><span data-stu-id="f3e49-149">On the same page, click to expand **Product licenses**.</span></span> <span data-ttu-id="f3e49-150">Activa el teléfono de área común y elige un **plan de llamadas** nacionales o un plan de llamadas **nacionales e internacionales.**</span><span class="sxs-lookup"><span data-stu-id="f3e49-150">Turn on the Common Area Phone and pick either a **Domestic Calling Plan** or a **Domestic and International Calling Plan**.</span></span> 

    ![Captura de pantalla que muestra la asignación de licencias](media/set-up-common-area-phone-image2.png)

> [!NOTE]
> <span data-ttu-id="f3e49-152">Si usa Enrutamiento directo de Microsoft Phone System, no es necesario asignar una licencia del Plan de llamadas.</span><span class="sxs-lookup"><span data-stu-id="f3e49-152">If you are using Microsoft Phone System Direct Routing, you do not need to assign a Calling Plan license.</span></span>

<span data-ttu-id="f3e49-153">Para obtener más información, vea [Asignar licencias a usuarios.](/microsoft-365/admin/manage/assign-licenses-to-users)</span><span class="sxs-lookup"><span data-stu-id="f3e49-153">For more information, see [Assign licenses to users](/microsoft-365/admin/manage/assign-licenses-to-users).</span></span>

## <a name="step-3---assign-a-phone-number-to-the-common-area-phone-user-account"></a><span data-ttu-id="f3e49-154">Paso 3: asignar un número de teléfono a la cuenta de usuario del teléfono de área común</span><span class="sxs-lookup"><span data-stu-id="f3e49-154">Step 3 - Assign a phone number to the Common Area Phone user account</span></span>

<span data-ttu-id="f3e49-155">Use el Centro de administración de Teams para asignar un número al usuario.</span><span class="sxs-lookup"><span data-stu-id="f3e49-155">Use the Teams admin center to assign a number to the user.</span></span>

1. <span data-ttu-id="f3e49-156">En el Centro de administración de Teams, seleccione **Números de teléfono** de  >  **voz.**</span><span class="sxs-lookup"><span data-stu-id="f3e49-156">In the Teams admin center, select **Voice** > **Phone numbers**.</span></span>

3.    <span data-ttu-id="f3e49-157">Seleccione un número de la lista de números de teléfono y haga clic en **Asignar**.</span><span class="sxs-lookup"><span data-stu-id="f3e49-157">Select a number from the list of phone numbers and click **Assign**.</span></span>

4. <span data-ttu-id="f3e49-158">En **la** página Asignar, en el cuadro Usuario de voz, escriba el nombre del usuario que va a usar el teléfono y, a continuación, seleccione el usuario en la lista desplegable Seleccionar **un** usuario de voz.</span><span class="sxs-lookup"><span data-stu-id="f3e49-158">On the **Assign** page, in the Voice user box, type the name of the user who will be using the phone, and then select the user in the **Select a voice user** drop-down list.</span></span>

5. <span data-ttu-id="f3e49-159">A continuación, debe agregar una dirección de emergencia.</span><span class="sxs-lookup"><span data-stu-id="f3e49-159">Next, you need to add an emergency address.</span></span> <span data-ttu-id="f3e49-160">Elija **Buscar por ciudad,** Buscar  por **descripción** o Buscar por ubicación en la lista desplegable y, a continuación, escriba la ciudad, descripción o ubicación en el cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="f3e49-160">Choose **Search by city**, **Search by description**, or **Search by location** from the drop-down list, and then enter the city, description, or location in the text box.</span></span> <span data-ttu-id="f3e49-161">Una vez que busque, busque en Seleccionar dirección **de emergencia** para elegir la correcta para usted.</span><span class="sxs-lookup"><span data-stu-id="f3e49-161">Once you search, look under **Select emergency address** to pick the right one for you.</span></span>

6. <span data-ttu-id="f3e49-162">Haga clic en **Guardar** y el usuario debería tener este aspecto:</span><span class="sxs-lookup"><span data-stu-id="f3e49-162">Click **Save** and your user should look like this:</span></span>

   ![Captura de pantalla que muestra la asignación de licencias](media/set-up-common-area-phone-image3.png)

> [!NOTE]
> <span data-ttu-id="f3e49-164">Los usuarios solo se mostrarán si tienen una licencia de Sistema telefónico aplicada.</span><span class="sxs-lookup"><span data-stu-id="f3e49-164">Users will only show up if they have a Phone System license applied.</span></span> <span data-ttu-id="f3e49-165">Si acaba de aplicársela, el usuario a veces tarda un poco de tiempo en aparecer en la lista.</span><span class="sxs-lookup"><span data-stu-id="f3e49-165">If you just did this, then sometimes it takes a bit for the user to show up in the list.</span></span>

<span data-ttu-id="f3e49-166">Para obtener más información, vea [Obtener números de teléfono para los usuarios.](getting-phone-numbers-for-your-users.md)</span><span class="sxs-lookup"><span data-stu-id="f3e49-166">For more information, see [Getting phone numbers for your users](getting-phone-numbers-for-your-users.md).</span></span>

<span data-ttu-id="f3e49-167">También puede llevar el número de teléfono que tiene con otro operador y "portabilidad" o transferirlo a Microsoft 365 u Office 365.</span><span class="sxs-lookup"><span data-stu-id="f3e49-167">You can also take your phone number that you have with another carrier and "port" or transfer it over to Microsoft 365 or Office 365.</span></span> <span data-ttu-id="f3e49-168">Vea [Transferir números de teléfono a Teams.](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)</span><span class="sxs-lookup"><span data-stu-id="f3e49-168">See [Transfer phone numbers to Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span></span>