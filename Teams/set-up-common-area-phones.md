---
title: Configurar la licencia de teléfono de área común
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
description: 'Aprenda a configurar teléfonos de área común para lobbies, áreas de recepción y salas de conferencias '
ms.openlocfilehash: f940ea7c14ad55c8cd3842e9830eb82da0d8867f
ms.sourcegitcommit: d7e0406276def8bc731aa6dcbd49802441ec5138
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/15/2020
ms.locfileid: "48476715"
---
# <a name="set-up-the-common-area-phone-license-for-microsoft-teams"></a><span data-ttu-id="9337e-103">Configuración de la licencia de teléfono de área común de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9337e-103">Set up the Common Area Phone license for Microsoft Teams</span></span>
> [!NOTE]
> <span data-ttu-id="9337e-104">Los teléfonos de área comunes no admiten correo de voz.</span><span class="sxs-lookup"><span data-stu-id="9337e-104">Common area phones do not support voicemail.</span></span>

<span data-ttu-id="9337e-105">Un teléfono de área común se coloca normalmente en un área como una sala de espera u otra área que está disponible para muchas personas para hacer una llamada; por ejemplo, un área de recepción, sala de espera o teléfono de conferencia.</span><span class="sxs-lookup"><span data-stu-id="9337e-105">A common area phone is typically placed in an area like a lobby or another area that is available to many people to make a call; for example, a reception area, lobby, or conference phone.</span></span> <span data-ttu-id="9337e-106">Los teléfonos de área comunes han iniciado sesión con cuentas vinculadas a una licencia de Teléfono de área común.</span><span class="sxs-lookup"><span data-stu-id="9337e-106">Common area phones are signed in with accounts tied to a Common Area Phone license.</span></span> <span data-ttu-id="9337e-107">La directiva de TeamsIPPhone también debe establecerse adecuadamente para que el teléfono tenga una experiencia de usuario de área común.</span><span class="sxs-lookup"><span data-stu-id="9337e-107">The TeamsIPPhone policy must also be appropriately set for the phone to have a common area user experience.</span></span>

<span data-ttu-id="9337e-108">En los pasos siguientes, le ayudaremos a configurar una cuenta de Sistema telefónico para implementar teléfonos de área comunes para su organización.</span><span class="sxs-lookup"><span data-stu-id="9337e-108">In the steps below, we'll help you set up an account for Phone System to deploy common area phones for your organization.</span></span> <span data-ttu-id="9337e-109">Para una experiencia de sala de reuniones más completa, incluyendo audioconferencias, considere la posibilidad de comprar la licencia dedicada sala de reuniones con un dispositivo de sala de reuniones.</span><span class="sxs-lookup"><span data-stu-id="9337e-109">For a more complete meeting room experience, including audio conferencing, consider purchasing the dedicated Meeting Room license with a meeting room device.</span></span> 

<span data-ttu-id="9337e-110">En primer lugar, debe comprar una licencia de Teléfono de área común (CAP) y asegurarse de que tiene un teléfono certificado.</span><span class="sxs-lookup"><span data-stu-id="9337e-110">First, you need to purchase a Common Area Phone (CAP) license and make sure that you have a certified phone.</span></span> <span data-ttu-id="9337e-111">Para buscar teléfonos certificados y obtener más información sobre estos, vaya a los [dispositivos de Microsoft Teams.](https://products.office.com/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1)</span><span class="sxs-lookup"><span data-stu-id="9337e-111">To search for and learn more about certified phones, go to [Microsoft Teams devices](https://products.office.com/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1).</span></span> 

## <a name="step-1---buy-the-licenses"></a><span data-ttu-id="9337e-112">Paso 1: comprar las licencias</span><span class="sxs-lookup"><span data-stu-id="9337e-112">Step 1 - Buy the licenses</span></span>

1. <span data-ttu-id="9337e-113">En el Centro de administración de Microsoft 365, vaya a Servicios de compra de facturación y  >   expanda **Otros planes.**</span><span class="sxs-lookup"><span data-stu-id="9337e-113">In the Microsoft 365 admin center, go to **Billing** > **Purchase services** and then expand **Other plans**.</span></span>

    ![Captura de pantalla que muestra el mosaico Teléfono del área común](media/set-up-common-area-phone-image1.png)

2. <span data-ttu-id="9337e-115">Selecciona **Comprar teléfono de área** común  >  **ahora.**</span><span class="sxs-lookup"><span data-stu-id="9337e-115">Select **Common Area Phone** > **Buy now**.</span></span>

3. <span data-ttu-id="9337e-116">En la página Finalizar la compra, haga clic **en Comprar ahora.**</span><span class="sxs-lookup"><span data-stu-id="9337e-116">On the Checkout page, click **Buy now**.</span></span>

4. <span data-ttu-id="9337e-117">Expande **los planes de complementos** y haz clic para comprar un plan de llamadas.</span><span class="sxs-lookup"><span data-stu-id="9337e-117">Expand **Add-on subscriptions** and then click to buy a Calling Plan.</span></span> <span data-ttu-id="9337e-118">Elija el plan **de llamadas nacionales** o el plan **de llamadas nacionales e internacionales.**</span><span class="sxs-lookup"><span data-stu-id="9337e-118">Choose either the **Domestic Calling Plan** or **Domestic and International Calling Plan**.</span></span>

> [!NOTE]
> <span data-ttu-id="9337e-119">Si usa el enrutamiento directo de Microsoft Phone System, no necesita una licencia de plan de llamadas.</span><span class="sxs-lookup"><span data-stu-id="9337e-119">If you are using Microsoft Phone System Direct Routing, you do not need a Calling Plan license.</span></span>

> [!NOTE]
> <span data-ttu-id="9337e-120">No es necesario agregar una licencia de Sistema telefónico.</span><span class="sxs-lookup"><span data-stu-id="9337e-120">You don't need to add a Phone System license.</span></span> <span data-ttu-id="9337e-121">Está incluida en la licencia del teléfono de área común.</span><span class="sxs-lookup"><span data-stu-id="9337e-121">It's included with the Common Area Phone license.</span></span>

<span data-ttu-id="9337e-122">Para obtener más información sobre las licencias, consulte [licencias de complementos de Microsoft Teams.](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing)</span><span class="sxs-lookup"><span data-stu-id="9337e-122">For more information on licenses, see [Microsoft Teams add-on licensing](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing).</span></span>

<span data-ttu-id="9337e-123">La licencia de teléfono de área común admite:</span><span class="sxs-lookup"><span data-stu-id="9337e-123">The Common Area Phone license supports:</span></span> 


|   |  <span data-ttu-id="9337e-124">Teléfono de área común</span><span class="sxs-lookup"><span data-stu-id="9337e-124">Common Area Phone</span></span>  |
|---------|---------|
|<span data-ttu-id="9337e-125">Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="9337e-125">Skype for Business</span></span> |   <span data-ttu-id="9337e-126">&#x2714;</span><span class="sxs-lookup"><span data-stu-id="9337e-126">&#x2714;</span></span> |
|<span data-ttu-id="9337e-127">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9337e-127">Microsoft Teams</span></span> |   <span data-ttu-id="9337e-128">&#x2714;</span><span class="sxs-lookup"><span data-stu-id="9337e-128">&#x2714;</span></span> |
|<span data-ttu-id="9337e-129">Sistema telefónico</span><span class="sxs-lookup"><span data-stu-id="9337e-129">Phone System</span></span> |    <span data-ttu-id="9337e-130">&#x2714;</span><span class="sxs-lookup"><span data-stu-id="9337e-130">&#x2714;</span></span> |
|<span data-ttu-id="9337e-131">Audioconferencia</span><span class="sxs-lookup"><span data-stu-id="9337e-131">Audio Conferencing</span></span> |       <span data-ttu-id="9337e-132">&#x2718; &sup1;</span><span class="sxs-lookup"><span data-stu-id="9337e-132">&#x2718; &sup1;</span></span>  |
|<span data-ttu-id="9337e-133">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="9337e-133">Microsoft Intune</span></span> |    <span data-ttu-id="9337e-134">&#x2718;</span><span class="sxs-lookup"><span data-stu-id="9337e-134">&#x2718;</span></span> |
|<span data-ttu-id="9337e-135">Disponibilidad en todo el mundo</span><span class="sxs-lookup"><span data-stu-id="9337e-135">Worldwide Availability</span></span> |       <span data-ttu-id="9337e-136">&#x2718; &sup2;</span><span class="sxs-lookup"><span data-stu-id="9337e-136">&#x2718; &sup2;</span></span>  |
|<span data-ttu-id="9337e-137">Disponibilidad de canales</span><span class="sxs-lookup"><span data-stu-id="9337e-137">Channel Availability</span></span> |    <span data-ttu-id="9337e-138">EA, EAS, CSP, GCC, EES, Web Direct</span><span class="sxs-lookup"><span data-stu-id="9337e-138">EA, EAS, CSP, GCC, EES, Web Direct</span></span>  |
|      |         |

<span data-ttu-id="9337e-139">&sup1; Los teléfonos de área común pueden unirse a conferencias de audio a través del número de acceso telefónico proporcionado por el organizador de la reunión</span><span class="sxs-lookup"><span data-stu-id="9337e-139">&sup1; Common Area Phones can join audio conferences via dial-in number provided by the meeting organizer</span></span>

<span data-ttu-id="9337e-140">&sup2; No disponible en nubes para entidades independiente</span><span class="sxs-lookup"><span data-stu-id="9337e-140">&sup2; Not available in sovereign clouds</span></span>  



## <a name="step-2---create-a-new-user-account-for-the-phone-and-assign-the-licenses"></a><span data-ttu-id="9337e-141">Paso 2: crear una nueva cuenta de usuario para el teléfono y asignar las licencias</span><span class="sxs-lookup"><span data-stu-id="9337e-141">Step 2 - Create a new user account for the phone and assign the licenses</span></span>

1. <span data-ttu-id="9337e-142">En el Centro de administración de Microsoft 365, vaya a **los usuarios**  >  **activos**  >  **que agreguen un usuario.**</span><span class="sxs-lookup"><span data-stu-id="9337e-142">In the Microsoft 365 admin center, go to **users** > **active users** > **add a user**.</span></span>

2. <span data-ttu-id="9337e-143">Escriba un nombre de usuario como "Principal" para el nombre y "Recepción" para el segundo nombre.</span><span class="sxs-lookup"><span data-stu-id="9337e-143">Enter a user name like "Main" for the first name and "Reception" for the second name.</span></span>

3. <span data-ttu-id="9337e-144">Escriba un nombre para mostrar si no genera automáticamente uno como "Recepción principal".</span><span class="sxs-lookup"><span data-stu-id="9337e-144">Enter a display name if it doesn't autogenerate one like "Main Reception."</span></span>

4. <span data-ttu-id="9337e-145">Escriba un nombre de usuario como "MainReception" o "Mainlobby".</span><span class="sxs-lookup"><span data-stu-id="9337e-145">Enter a user name like "MainReception" or "Mainlobby."</span></span>

5. <span data-ttu-id="9337e-146">En el caso de los teléfonos de área comunes, es posible que desee establecer una contraseña manualmente o tener la misma contraseña para todos los teléfonos de área comunes.</span><span class="sxs-lookup"><span data-stu-id="9337e-146">For common area phones, you might want to set a password manually or have the same password for all your common area phones.</span></span> <span data-ttu-id="9337e-147">Además, puede que piense en desactivar la casilla Hacer que este usuario cambie su contraseña la primera vez que **inicie sesión.**</span><span class="sxs-lookup"><span data-stu-id="9337e-147">Also, you might think about clearing the **Make this user change their password when they first sign in** check box.</span></span>

6. <span data-ttu-id="9337e-148">Asigne las licencias al usuario.</span><span class="sxs-lookup"><span data-stu-id="9337e-148">Assign the licenses to the user.</span></span> <span data-ttu-id="9337e-149">En la misma página, haga clic para expandir las **Licencias de producto**.</span><span class="sxs-lookup"><span data-stu-id="9337e-149">On the same page, click to expand **Product licenses**.</span></span> <span data-ttu-id="9337e-150">Activa el teléfono de área común y elige un plan de llamadas nacionales o un **plan** de **llamadas nacionales e internacionales.**</span><span class="sxs-lookup"><span data-stu-id="9337e-150">Turn on the Common Area Phone and pick either a **Domestic Calling Plan** or a **Domestic and International Calling Plan**.</span></span> 

    ![Captura de pantalla que muestra la asignación de licencias](media/set-up-common-area-phone-image2.png)

> [!NOTE]
> <span data-ttu-id="9337e-152">Si usa el enrutamiento directo de Microsoft Phone System, no es necesario asignar una licencia de plan de llamadas.</span><span class="sxs-lookup"><span data-stu-id="9337e-152">If you are using Microsoft Phone System Direct Routing, you do not need to assign a Calling Plan license.</span></span>

<span data-ttu-id="9337e-153">Para obtener más información, [vea Asignar licencias a usuarios.](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)</span><span class="sxs-lookup"><span data-stu-id="9337e-153">For more information, see [Assign licenses to users](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).</span></span>

## <a name="step-3---assign-a-phone-number-to-the-common-area-phone-user-account"></a><span data-ttu-id="9337e-154">Paso 3: asignar un número de teléfono a la cuenta de usuario del teléfono de área común</span><span class="sxs-lookup"><span data-stu-id="9337e-154">Step 3 - Assign a phone number to the Common Area Phone user account</span></span>

<span data-ttu-id="9337e-155">Use el Centro de administración de Teams para asignar un número al usuario.</span><span class="sxs-lookup"><span data-stu-id="9337e-155">Use the Teams admin center to assign a number to the user.</span></span>

1. <span data-ttu-id="9337e-156">En el Centro de administración de Teams, seleccione **Números de teléfono de**  >  **voz.**</span><span class="sxs-lookup"><span data-stu-id="9337e-156">In the Teams admin center, select **Voice** > **Phone numbers**.</span></span>

3.    <span data-ttu-id="9337e-157">Seleccione un número de la lista de números de teléfono y haga clic en **Asignar**.</span><span class="sxs-lookup"><span data-stu-id="9337e-157">Select a number from the list of phone numbers and click **Assign**.</span></span>

4. <span data-ttu-id="9337e-158">En **la** página Asignar, en el cuadro de usuario de voz, escriba el nombre del usuario que va a usar el teléfono y, **a** continuación, seleccione el usuario en la lista desplegable Seleccionar un usuario de voz.</span><span class="sxs-lookup"><span data-stu-id="9337e-158">On the **Assign** page, in the Voice user box, type the name of the user who will be using the phone, and then select the user in the **Select a voice user** drop-down list.</span></span>

5. <span data-ttu-id="9337e-159">A continuación, debe agregar una dirección de emergencia.</span><span class="sxs-lookup"><span data-stu-id="9337e-159">Next, you need to add an emergency address.</span></span> <span data-ttu-id="9337e-160">Elija **Buscar por** ciudad, Buscar  por descripción o Buscar por ubicación en la lista desplegable y, después, escriba la ciudad, la descripción o la ubicación en el cuadro de texto. </span><span class="sxs-lookup"><span data-stu-id="9337e-160">Choose **Search by city**, **Search by description**, or **Search by location** from the drop-down list, and then enter the city, description, or location in the text box.</span></span> <span data-ttu-id="9337e-161">Una vez que busque, busque en Seleccionar dirección **de emergencia** para elegir la adecuada para usted.</span><span class="sxs-lookup"><span data-stu-id="9337e-161">Once you search, look under **Select emergency address** to pick the right one for you.</span></span>

6. <span data-ttu-id="9337e-162">Haga clic en **Guardar** y el usuario debería tener este aspecto:</span><span class="sxs-lookup"><span data-stu-id="9337e-162">Click **Save** and your user should look like this:</span></span>

   ![Captura de pantalla que muestra la asignación de licencias](media/set-up-common-area-phone-image3.png)

> [!NOTE]
> <span data-ttu-id="9337e-164">Los usuarios solo se mostrarán si tienen aplicada una licencia de Sistema telefónico.</span><span class="sxs-lookup"><span data-stu-id="9337e-164">Users will only show up if they have a Phone System license applied.</span></span> <span data-ttu-id="9337e-165">Si acaba de aplicársela, el usuario a veces tarda un poco de tiempo en aparecer en la lista.</span><span class="sxs-lookup"><span data-stu-id="9337e-165">If you just did this, then sometimes it takes a bit for the user to show up in the list.</span></span>

<span data-ttu-id="9337e-166">Para obtener más información, vea [Obtener números de teléfono para los usuarios.](getting-phone-numbers-for-your-users.md)</span><span class="sxs-lookup"><span data-stu-id="9337e-166">For more information, see [Getting phone numbers for your users](getting-phone-numbers-for-your-users.md).</span></span>

<span data-ttu-id="9337e-167">También puede transferir su número de teléfono que tiene con otro operador y realizar una transferencia a Microsoft 365 u Office 365.</span><span class="sxs-lookup"><span data-stu-id="9337e-167">You can also take your phone number that you have with another carrier and "port" or transfer it over to Microsoft 365 or Office 365.</span></span> <span data-ttu-id="9337e-168">Consulte [Transferir números de teléfono a Teams.](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)</span><span class="sxs-lookup"><span data-stu-id="9337e-168">See [Transfer phone numbers to Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span></span>
