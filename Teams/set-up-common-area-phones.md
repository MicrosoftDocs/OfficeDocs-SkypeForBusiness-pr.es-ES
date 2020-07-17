---
title: Configurar la licencia telefónica de área común
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
description: 'Más información sobre cómo configurar teléfonos de área común para salas, áreas de recepción y salas de conferencias '
ms.openlocfilehash: ef75c23ff72d9b640fb5a53feff7cf46fec43292
ms.sourcegitcommit: 2cc36c954200f50de33b909856b33fe0a9a6b7a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/14/2020
ms.locfileid: "45125993"
---
# <a name="set-up-the-common-area-phone-license-for-microsoft-teams"></a><span data-ttu-id="75eb5-103">Configuración de la licencia de teléfono de área común de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="75eb5-103">Set up the Common Area Phone license for Microsoft Teams</span></span>
> [!NOTE]
> <span data-ttu-id="75eb5-104">Los teléfonos de área común no admiten el buzón de voz.</span><span class="sxs-lookup"><span data-stu-id="75eb5-104">Common area phones do not support voicemail.</span></span>

<span data-ttu-id="75eb5-105">Un teléfono de área común suele colocarse en un área como una sala de recepción u otra área que está disponible para muchas personas para hacer una llamada; por ejemplo, un área de recepción, una sala de recepción o un teléfono de conferencia.</span><span class="sxs-lookup"><span data-stu-id="75eb5-105">A common area phone is typically placed in an area like a lobby or another area that is available to many people to make a call; for example, a reception area, lobby, or conference phone.</span></span> <span data-ttu-id="75eb5-106">Los teléfonos de área común se configuran como dispositivos en lugar de usuarios y pueden iniciar sesión automáticamente en una red.</span><span class="sxs-lookup"><span data-stu-id="75eb5-106">Common area phones are set up as devices rather than users, and can automatically sign into a network.</span></span>

<span data-ttu-id="75eb5-107">En los pasos siguientes, le ayudaremos a configurar una cuenta para el sistema telefónico para implementar teléfonos de área común para su organización.</span><span class="sxs-lookup"><span data-stu-id="75eb5-107">In the steps below, we'll help you set up an account for Phone System to deploy common area phones for your organization.</span></span> <span data-ttu-id="75eb5-108">Para obtener una experiencia de sala de reuniones más completa, incluidas las conferencias de audio, considere la posibilidad de comprar la licencia de sala de reuniones dedicada con un dispositivo de sala de reuniones.</span><span class="sxs-lookup"><span data-stu-id="75eb5-108">For a more complete meeting room experience, including audio conferencing, consider purchasing the dedicated Meeting Room license with a meeting room device.</span></span> 

<span data-ttu-id="75eb5-109">En primer lugar, debe comprar una licencia de teléfono de área común (CAP) y asegurarse de que tiene un teléfono certificado.</span><span class="sxs-lookup"><span data-stu-id="75eb5-109">First, you need to purchase a Common Area Phone (CAP) license and make sure that you have a certified phone.</span></span> <span data-ttu-id="75eb5-110">Para buscar y obtener más información sobre teléfonos certificados, vaya a [dispositivos de Microsoft Teams](https://products.office.com/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1).</span><span class="sxs-lookup"><span data-stu-id="75eb5-110">To search for and learn more about certified phones, go to [Microsoft Teams devices](https://products.office.com/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1).</span></span> 

## <a name="step-1---buy-the-licenses"></a><span data-ttu-id="75eb5-111">Paso 1: comprar las licencias</span><span class="sxs-lookup"><span data-stu-id="75eb5-111">Step 1 - Buy the licenses</span></span>

1. <span data-ttu-id="75eb5-112">En el centro de administración de Microsoft 365, vaya a servicios de compra de **facturación**  >  **Purchase services** y, a continuación, expanda **otros planes**.</span><span class="sxs-lookup"><span data-stu-id="75eb5-112">In the Microsoft 365 admin center, go to **Billing** > **Purchase services** and then expand **Other plans**.</span></span>

    ![Captura de pantalla que muestra el icono de teléfono de área común](media/set-up-common-area-phone-image1.png)

2. <span data-ttu-id="75eb5-114">Seleccione el **teléfono de área común**  >  **comprar ahora**.</span><span class="sxs-lookup"><span data-stu-id="75eb5-114">Select **Common Area Phone** > **Buy now**.</span></span>

3. <span data-ttu-id="75eb5-115">En la página Desproteger, haga clic en **comprar ahora**.</span><span class="sxs-lookup"><span data-stu-id="75eb5-115">On the Checkout page, click **Buy now**.</span></span>

4. <span data-ttu-id="75eb5-116">Expanda **suscripciones de complementos** y, a continuación, haga clic para comprar un plan de llamadas.</span><span class="sxs-lookup"><span data-stu-id="75eb5-116">Expand **Add-on subscriptions** and then click to buy a Calling Plan.</span></span> <span data-ttu-id="75eb5-117">Elige el **plan de llamadas nacionales** o el **plan de llamadas nacionales e internacionales**.</span><span class="sxs-lookup"><span data-stu-id="75eb5-117">Choose either the **Domestic Calling Plan** or **Domestic and International Calling Plan**.</span></span>

> [!NOTE]
> <span data-ttu-id="75eb5-118">Si está usando el enrutamiento directo de Microsoft Phone System, no necesita una licencia de plan de llamadas.</span><span class="sxs-lookup"><span data-stu-id="75eb5-118">If you are using Microsoft Phone System Direct Routing, you do not need a Calling Plan license.</span></span>

> [!NOTE]
> <span data-ttu-id="75eb5-119">No es necesario agregar una licencia de sistema telefónico.</span><span class="sxs-lookup"><span data-stu-id="75eb5-119">You don't need to add a Phone System license.</span></span> <span data-ttu-id="75eb5-120">Está incluida en la licencia del teléfono de área común.</span><span class="sxs-lookup"><span data-stu-id="75eb5-120">It's included with the Common Area Phone license.</span></span>

<span data-ttu-id="75eb5-121">Para obtener más información sobre las licencias, vea [licencias complementarias de Microsoft Teams](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="75eb5-121">For more information on licenses, see [Microsoft Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>

<span data-ttu-id="75eb5-122">La licencia de telefonía por área común admite:</span><span class="sxs-lookup"><span data-stu-id="75eb5-122">The Common Area Phone license supports:</span></span> 


|   |  <span data-ttu-id="75eb5-123">Teléfono de área común</span><span class="sxs-lookup"><span data-stu-id="75eb5-123">Common Area Phone</span></span>  |
|---------|---------|
|<span data-ttu-id="75eb5-124">Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="75eb5-124">Skype for Business</span></span> |   <span data-ttu-id="75eb5-125">&#x2714;</span><span class="sxs-lookup"><span data-stu-id="75eb5-125">&#x2714;</span></span> |
|<span data-ttu-id="75eb5-126">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="75eb5-126">Microsoft Teams</span></span> |   <span data-ttu-id="75eb5-127">&#x2714;</span><span class="sxs-lookup"><span data-stu-id="75eb5-127">&#x2714;</span></span> |
|<span data-ttu-id="75eb5-128">Sistema telefónico</span><span class="sxs-lookup"><span data-stu-id="75eb5-128">Phone System</span></span> |    <span data-ttu-id="75eb5-129">&#x2714;</span><span class="sxs-lookup"><span data-stu-id="75eb5-129">&#x2714;</span></span> |
|<span data-ttu-id="75eb5-130">Audioconferencia</span><span class="sxs-lookup"><span data-stu-id="75eb5-130">Audio Conferencing</span></span> |       <span data-ttu-id="75eb5-131">&#x2718; &Sup1;</span><span class="sxs-lookup"><span data-stu-id="75eb5-131">&#x2718; &sup1;</span></span>  |
|<span data-ttu-id="75eb5-132">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="75eb5-132">Microsoft Intune</span></span> |        <span data-ttu-id="75eb5-133">&#x2718; &sup2;</span><span class="sxs-lookup"><span data-stu-id="75eb5-133">&#x2718; &sup2;</span></span> |
|<span data-ttu-id="75eb5-134">Disponibilidad en todo el mundo</span><span class="sxs-lookup"><span data-stu-id="75eb5-134">Worldwide Availability</span></span> |    <span data-ttu-id="75eb5-135">&#x2714;</span><span class="sxs-lookup"><span data-stu-id="75eb5-135">&#x2714;</span></span> |
|<span data-ttu-id="75eb5-136">Disponibilidad del canal</span><span class="sxs-lookup"><span data-stu-id="75eb5-136">Channel Availability</span></span> |    <span data-ttu-id="75eb5-137">EA, EAS, CSP, GCC, EES, Web Direct</span><span class="sxs-lookup"><span data-stu-id="75eb5-137">EA, EAS, CSP, GCC, EES, Web Direct</span></span>  |
|      |         |

<span data-ttu-id="75eb5-138">&Sup1; Los teléfonos de área común pueden unirse a conferencias de audio a través del número de acceso telefónico proporcionado por el organizador de la reunión</span><span class="sxs-lookup"><span data-stu-id="75eb5-138">&sup1; Common Area Phones can join audio conferences via dial-in number provided by the meeting organizer</span></span>

<span data-ttu-id="75eb5-139">&sup2; No disponible en nubes soberanos</span><span class="sxs-lookup"><span data-stu-id="75eb5-139">&sup2; Not available in sovereign clouds</span></span>  



## <a name="step-2---create-a-new-user-account-for-the-phone-and-assign-the-licenses"></a><span data-ttu-id="75eb5-140">Paso 2: crear una nueva cuenta de usuario para el teléfono y asignar las licencias</span><span class="sxs-lookup"><span data-stu-id="75eb5-140">Step 2 - Create a new user account for the phone and assign the licenses</span></span>

1. <span data-ttu-id="75eb5-141">En el centro de administración de Microsoft 365, **vaya a usuarios**  >  **activos**,  >  **Agregar un usuario**.</span><span class="sxs-lookup"><span data-stu-id="75eb5-141">In the Microsoft 365 admin center, go to **users** > **active users** > **add a user**.</span></span>

2. <span data-ttu-id="75eb5-142">Escriba un nombre de usuario como "Main" para el nombre y "recepción" para el segundo nombre.</span><span class="sxs-lookup"><span data-stu-id="75eb5-142">Enter a user name like "Main" for the first name and "Reception" for the second name.</span></span>

3. <span data-ttu-id="75eb5-143">Escriba un nombre para mostrar si no genera automáticamente una "recepción principal".</span><span class="sxs-lookup"><span data-stu-id="75eb5-143">Enter a display name if it doesn't autogenerate one like "Main Reception."</span></span>

4. <span data-ttu-id="75eb5-144">Escriba un nombre de usuario como "MainReception" o "Mainlobby".</span><span class="sxs-lookup"><span data-stu-id="75eb5-144">Enter a user name like "MainReception" or "Mainlobby."</span></span>

5. <span data-ttu-id="75eb5-145">Para teléfonos de área común, es posible que desee establecer una contraseña de forma manual o tener la misma contraseña para todos los teléfonos de área común.</span><span class="sxs-lookup"><span data-stu-id="75eb5-145">For common area phones, you might want to set a password manually or have the same password for all your common area phones.</span></span> <span data-ttu-id="75eb5-146">Además, es posible que piense desactivando la casilla de verificación **hacer que este usuario cambie la contraseña la primera vez que inicie sesión** .</span><span class="sxs-lookup"><span data-stu-id="75eb5-146">Also, you might think about clearing the **Make this user change their password when they first sign in** check box.</span></span>

6. <span data-ttu-id="75eb5-147">Asigne las licencias al usuario.</span><span class="sxs-lookup"><span data-stu-id="75eb5-147">Assign the licenses to the user.</span></span> <span data-ttu-id="75eb5-148">En la misma página, haga clic para expandir las **Licencias de producto**.</span><span class="sxs-lookup"><span data-stu-id="75eb5-148">On the same page, click to expand **Product licenses**.</span></span> <span data-ttu-id="75eb5-149">Enciende el teléfono de área común y elige un plan de **llamadas nacionales** o un **plan de llamadas nacionales e internacionales**.</span><span class="sxs-lookup"><span data-stu-id="75eb5-149">Turn on the Common Area Phone and pick either a **Domestic Calling Plan** or a **Domestic and International Calling Plan**.</span></span> 

    ![Captura de pantalla que muestra la asignación de licencias](media/set-up-common-area-phone-image2.png)

> [!NOTE]
> <span data-ttu-id="75eb5-151">Si está usando el enrutamiento directo de Microsoft Phone System, no es necesario que asigne una licencia de plan de llamadas.</span><span class="sxs-lookup"><span data-stu-id="75eb5-151">If you are using Microsoft Phone System Direct Routing, you do not need to assign a Calling Plan license.</span></span>

<span data-ttu-id="75eb5-152">Para obtener más información, vea [asignar licencias a usuarios](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).</span><span class="sxs-lookup"><span data-stu-id="75eb5-152">For more information, see [Assign licenses to users](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).</span></span>

## <a name="step-3---assign-a-phone-number-to-the-common-area-phone-user-account"></a><span data-ttu-id="75eb5-153">Paso 3: asignar un número de teléfono a la cuenta de usuario del teléfono de área común</span><span class="sxs-lookup"><span data-stu-id="75eb5-153">Step 3 - Assign a phone number to the Common Area Phone user account</span></span>

<span data-ttu-id="75eb5-154">Use el centro de administración de Teams para asignar un número al usuario.</span><span class="sxs-lookup"><span data-stu-id="75eb5-154">Use the Teams admin center to assign a number to the user.</span></span>

1. <span data-ttu-id="75eb5-155">En el centro de administración de Teams, seleccione números de teléfono de **voz**  >  **Phone numbers**.</span><span class="sxs-lookup"><span data-stu-id="75eb5-155">In the Teams admin center, select **Voice** > **Phone numbers**.</span></span>

3.    <span data-ttu-id="75eb5-156">Seleccione un número de la lista de números de teléfono y haga clic en **Asignar**.</span><span class="sxs-lookup"><span data-stu-id="75eb5-156">Select a number from the list of phone numbers and click **Assign**.</span></span>

4. <span data-ttu-id="75eb5-157">En la página **asignar** , en el cuadro usuario de voz, escriba el nombre del usuario que va a usar el teléfono y, a continuación, seleccione el usuario en la lista desplegable **seleccionar un usuario de voz** .</span><span class="sxs-lookup"><span data-stu-id="75eb5-157">On the **Assign** page, in the Voice user box, type the name of the user who will be using the phone, and then select the user in the **Select a voice user** drop-down list.</span></span>

5. <span data-ttu-id="75eb5-158">A continuación, debe agregar una dirección de emergencia.</span><span class="sxs-lookup"><span data-stu-id="75eb5-158">Next, you need to add an emergency address.</span></span> <span data-ttu-id="75eb5-159">Elija **Buscar por ciudad**, **Buscar por Descripción**o **Buscar por ubicación** en la lista desplegable y, a continuación, escriba la ciudad, la descripción o la ubicación en el cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="75eb5-159">Choose **Search by city**, **Search by description**, or **Search by location** from the drop-down list, and then enter the city, description, or location in the text box.</span></span> <span data-ttu-id="75eb5-160">Una vez que haya buscado, mire en **seleccionar dirección de emergencia** para elegir el adecuado para usted.</span><span class="sxs-lookup"><span data-stu-id="75eb5-160">Once you search, look under **Select emergency address** to pick the right one for you.</span></span>

6. <span data-ttu-id="75eb5-161">Haga clic en **Guardar** y el usuario debería tener este aspecto:</span><span class="sxs-lookup"><span data-stu-id="75eb5-161">Click **Save** and your user should look like this:</span></span>

   ![Captura de pantalla que muestra la asignación de licencias](media/set-up-common-area-phone-image3.png)

> [!NOTE]
> <span data-ttu-id="75eb5-163">Los usuarios solo aparecerán si tienen una licencia de sistema telefónico aplicada.</span><span class="sxs-lookup"><span data-stu-id="75eb5-163">Users will only show up if they have a Phone System license applied.</span></span> <span data-ttu-id="75eb5-164">Si acaba de aplicársela, el usuario a veces tarda un poco de tiempo en aparecer en la lista.</span><span class="sxs-lookup"><span data-stu-id="75eb5-164">If you just did this, then sometimes it takes a bit for the user to show up in the list.</span></span>

<span data-ttu-id="75eb5-165">Para obtener más información, vea [obtener números de teléfono para los usuarios](getting-phone-numbers-for-your-users.md).</span><span class="sxs-lookup"><span data-stu-id="75eb5-165">For more information, see [Getting phone numbers for your users](getting-phone-numbers-for-your-users.md).</span></span>

<span data-ttu-id="75eb5-166">También puede tomar su número de teléfono con otro operador y "puerto" o transferirlo a Microsoft 365 u Office 365.</span><span class="sxs-lookup"><span data-stu-id="75eb5-166">You can also take your phone number that you have with another carrier and "port" or transfer it over to Microsoft 365 or Office 365.</span></span> <span data-ttu-id="75eb5-167">Consulte [transferir números de teléfono a teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span><span class="sxs-lookup"><span data-stu-id="75eb5-167">See [Transfer phone numbers to Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span></span>
