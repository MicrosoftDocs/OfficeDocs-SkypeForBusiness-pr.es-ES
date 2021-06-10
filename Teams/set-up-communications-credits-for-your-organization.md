---
title: Configurar Créditos de comunicaciones para su organización
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: mikedav
ms.topic: article
ms.assetid: bb9f2a8d-f5be-41ed-9d19-25dea5ca9f52
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Licensing
- seo-marvel-apr2020
description: 'Learn how to set up communication credits (PSTN Consumption) billing licenses for your users and organization. '
ms.openlocfilehash: 98591d7603cdf63a76bef3478834f37504d8ff6c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117108"
---
# <a name="set-up-communications-credits-for-your-organization"></a><span data-ttu-id="8f5c7-103">Configurar Créditos de comunicaciones para su organización</span><span class="sxs-lookup"><span data-stu-id="8f5c7-103">Set up Communications Credits for your organization</span></span>

<span data-ttu-id="8f5c7-104">Debe configurar créditos de comunicaciones si pretende usar números gratuitos con Skype for Business y Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="8f5c7-104">You will need to set up Communications Credits if you would like to use toll-free numbers with Skype for Business and Microsoft Teams.</span></span> <span data-ttu-id="8f5c7-105">Además, le recomendamos que configure créditos de comunicaciones para sus planes de llamadas (nacionales o internacionales) y usuarios de audioconferencia que necesiten la capacidad de llamar a **cualquier destino.**</span><span class="sxs-lookup"><span data-stu-id="8f5c7-105">Also, we recommend that you set up Communications Credits for your Calling Plans (Domestic or International) and Audio Conferencing users who need the ability to dial out to **any destination**.</span></span> <span data-ttu-id="8f5c7-106">Se incluyen muchos países o regiones, pero es posible que algunos destinos no se incluyan en sus planes de llamadas o en las suscripciones de audioconferencia.</span><span class="sxs-lookup"><span data-stu-id="8f5c7-106">Many countries/regions are included, but some destinations may not be included in your Calling Plan or Audio Conferencing subscriptions.</span></span> <span data-ttu-id="8f5c7-107">Si no configura la facturación de créditos de comunicaciones y asigna una licencia de créditos de comunicaciones **a** los usuarios y se le ejecutan minutos para su organización (según el plan de llamadas o el plan de audioconferencias de su país o región), esos usuarios no podrán realizar llamadas ni llamar desde reuniones de audioconferencias.</span><span class="sxs-lookup"><span data-stu-id="8f5c7-107">If you don't set up Communications Credits billing and assign a **Communications Credits** license to your users and you run out minutes for your organization (depending on your Calling Plan or Audio Conferencing plan in your country/region), those users won't be able to make calls or dial out from Audio Conferencing meetings.</span></span> <span data-ttu-id="8f5c7-108">Puede obtener más información, incluidas las cantidades de financiación recomendadas, leyendo ¿Qué son los créditos [de comunicaciones?](what-are-communications-credits.md)</span><span class="sxs-lookup"><span data-stu-id="8f5c7-108">You can get more information, including recommended funding amounts, by reading [What are Communications Credits?](what-are-communications-credits.md)</span></span>
  
> [!NOTE]
> <span data-ttu-id="8f5c7-109">Para saber cuánto cuesta, [consulte aquí las tarifas](https://go.microsoft.com/fwlink/p/?LinkId=799523 ).</span><span class="sxs-lookup"><span data-stu-id="8f5c7-109">To find out how much it costs, [see the rates here](https://go.microsoft.com/fwlink/p/?LinkId=799523 ).</span></span> 
  
## <a name="step-1-assign-an-audio-conferencing-or-calling-plan-license-to-your-users"></a><span data-ttu-id="8f5c7-110">Paso 1: Asignar una licencia de audioconferencia o plan de llamadas a los usuarios</span><span class="sxs-lookup"><span data-stu-id="8f5c7-110">Step 1: Assign an Audio Conferencing or Calling Plan license to your users</span></span>

<span data-ttu-id="8f5c7-111">Cuando se registra, obtiene un número determinado de minutos dependiendo de su país o región.</span><span class="sxs-lookup"><span data-stu-id="8f5c7-111">When you sign up, you get a certain number of minutes depending on your country/region.</span></span> <span data-ttu-id="8f5c7-112">Puede buscar su país o [](./country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md#select-your-country-or-region-to-see-whats-available-for-your-organization) región en la lista de disponibilidad país o región para planes de audioconferencias y llamadas para ver el número de minutos que recibirá.</span><span class="sxs-lookup"><span data-stu-id="8f5c7-112">You can search for your country or region in the [Country or region availability list for Audio Conferencing and Calling Plans](./country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md#select-your-country-or-region-to-see-whats-available-for-your-organization) to see the number of minutes you will get.</span></span> <span data-ttu-id="8f5c7-113">Después de usar esos minutos, las llamadas se desconectarán.</span><span class="sxs-lookup"><span data-stu-id="8f5c7-113">After you use those minutes, calls will be disconnected.</span></span> <span data-ttu-id="8f5c7-114">Para evitar que esto suceda, debe configurar créditos de comunicaciones.</span><span class="sxs-lookup"><span data-stu-id="8f5c7-114">To prevent this from happening, you need to set up Communications Credits.</span></span>
  
<span data-ttu-id="8f5c7-115">Para ello, debe asignar una licencia de **audioconferencia o Sistema telefónico a** los usuarios.</span><span class="sxs-lookup"><span data-stu-id="8f5c7-115">To do so, **you need to assign an Audio Conferencing or Phone System license** to your users.</span></span>
  
- <span data-ttu-id="8f5c7-116">Asigne una **licencia de audioconferencia** a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="8f5c7-116">Assign an **Audio Conferencing** license to your users.</span></span> <span data-ttu-id="8f5c7-117">Vea [Asignar Microsoft Teams de complementos.](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)</span><span class="sxs-lookup"><span data-stu-id="8f5c7-117">See [Assign Microsoft Teams add-on licenses](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>
    
    <span data-ttu-id="8f5c7-118">Después de asignar esta licencia, tendrá que configurar las audioconferencias.</span><span class="sxs-lookup"><span data-stu-id="8f5c7-118">After you assign this license, you will need to set up audio conferencing.</span></span> <span data-ttu-id="8f5c7-119">Para obtener instrucciones paso a paso, vea Probar o comprar audioconferencias en [Microsoft 365 o Office 365](try-or-purchase-audio-conferencing-in-office-365-for-teams.md).</span><span class="sxs-lookup"><span data-stu-id="8f5c7-119">For step-by-step instructions, see [Try or purchase Audio Conferencing in Microsoft 365 or Office 365](try-or-purchase-audio-conferencing-in-office-365-for-teams.md).</span></span>
    
- <span data-ttu-id="8f5c7-120">Asigne **Sistema telefónico** y una licencia del Plan de llamadas **nacionales** o nacionales e internacionales a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="8f5c7-120">Assign **Phone System** and a **Domestic or Domestic and International** Calling Plan license to your users.</span></span> <span data-ttu-id="8f5c7-121">Vea [Asignar Microsoft Teams de complementos.](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)</span><span class="sxs-lookup"><span data-stu-id="8f5c7-121">See [Assign Microsoft Teams add-on licenses](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="8f5c7-122">Aunque no es necesario para los créditos de comunicaciones, aún debe asignar un plan de llamadas nacionales o una licencia del **Plan** de **llamadas** nacionales e internacionales.</span><span class="sxs-lookup"><span data-stu-id="8f5c7-122">Although it's not required for Communications Credits, you still need to also assign a **Domestic Calling Plan** or a **Domestic and International Calling Plan** license.</span></span>
  
    <span data-ttu-id="8f5c7-123">Después de asignar estas licencias, tendrá que obtener sus números de teléfono para la organización y asignarlos a los miembros de su organización.</span><span class="sxs-lookup"><span data-stu-id="8f5c7-123">After you assign these licenses, you will need to get your phone numbers for your organization, and then assign those numbers to the people in your organization.</span></span> <span data-ttu-id="8f5c7-124">Para obtener instrucciones paso a paso, vea [Configurar planes de llamadas.](set-up-calling-plans.md)</span><span class="sxs-lookup"><span data-stu-id="8f5c7-124">For step-by-step instructions, see [Set up Calling Plans](set-up-calling-plans.md).</span></span>
    
<span data-ttu-id="8f5c7-125">Para obtener más información, [vea Microsoft Teams de complementos](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)</span><span class="sxs-lookup"><span data-stu-id="8f5c7-125">For more information, see [Microsoft Teams add-on licensing](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)</span></span>
  
## <a name="step-2-set-up-communications-credits-for-your-organization"></a><span data-ttu-id="8f5c7-126">Paso 2: Configurar créditos de comunicaciones para su organización</span><span class="sxs-lookup"><span data-stu-id="8f5c7-126">Step 2: Set up Communications Credits for your organization</span></span>

1. <span data-ttu-id="8f5c7-127">Inicie sesión en el [Microsoft 365 de administración con](https://portal.office.com/Adminportal) su cuenta de trabajo o escuela.</span><span class="sxs-lookup"><span data-stu-id="8f5c7-127">Sign in to the [Microsoft 365 admin center](https://portal.office.com/Adminportal) with your work or school account.</span></span>
    
2. <span data-ttu-id="8f5c7-128">En el panel de navegación izquierdo del centro Microsoft 365 administración, vaya a **Servicios de compra** de  >  **facturación.**</span><span class="sxs-lookup"><span data-stu-id="8f5c7-128">In the left navigation of the Microsoft 365 admin center, go to **Billing** > **Purchase Services**.</span></span> <span data-ttu-id="8f5c7-129">Desplácese hacia abajo y **seleccione Complementos.**</span><span class="sxs-lookup"><span data-stu-id="8f5c7-129">Scroll down and select **Add-Ons**.</span></span>

3. <span data-ttu-id="8f5c7-130">Seleccione **Créditos de comunicaciones**.</span><span class="sxs-lookup"><span data-stu-id="8f5c7-130">Select **Communications Credits**.</span></span>
    
4. <span data-ttu-id="8f5c7-131">En la página **Descréditos** de comunicaciones, rellene la información y, a continuación, haga clic en **Siguiente:**</span><span class="sxs-lookup"><span data-stu-id="8f5c7-131">On the **Communications Credits** subscription page, fill in your information, and then click **Next**:</span></span>
    
   - <span data-ttu-id="8f5c7-132">**Agregar fondos** Escriba la cantidad que desea agregar a su cuenta.</span><span class="sxs-lookup"><span data-stu-id="8f5c7-132">**Add funds** Enter the amount that you want to add to your account.</span></span> <span data-ttu-id="8f5c7-133">Si no habilita la recarga automática, una vez agotados estos fondos, las capacidades de llamadas habilitadas con créditos de comunicaciones se interrumpirán (como el servicio gratuito de entrada).</span><span class="sxs-lookup"><span data-stu-id="8f5c7-133">If you don't enable auto-recharge, once these funds are depleted, calling capabilities that are enabled using Communications Credits will be disrupted (such as inbound toll-free service).</span></span> <span data-ttu-id="8f5c7-134">Para evitar tener que reponer manualmente el saldo de créditos de comunicaciones cada vez que el saldo llegue a 0 (cero), le recomendamos que habilite la característica de recarga automática.</span><span class="sxs-lookup"><span data-stu-id="8f5c7-134">To avoid having to manually replenish your Communications Credits balance each time your balance reaches 0 (zero), we recommend you enable the auto-recharge feature.</span></span>
    
   - <span data-ttu-id="8f5c7-135">**Recarga automática** Si habilita la recarga automática, ls cuenta se rellenará automáticamente cuando el saldo esté por debajo del umbral que establezca.</span><span class="sxs-lookup"><span data-stu-id="8f5c7-135">**Auto-recharge** Enabling auto-recharge will automatically refill your account when the balance falls below the threshold that you set.</span></span>
    
     <span data-ttu-id="8f5c7-136">Se recomienda usar la  opción recarga automática para evitar cualquier interrupción del servicio si el saldo de créditos de comunicaciones llega a 0 (cero).</span><span class="sxs-lookup"><span data-stu-id="8f5c7-136">It's recommended that you use the **Auto-recharge** setting to avoid any disruption of service should your Communications Credits balance reach 0 (zero).</span></span> <span data-ttu-id="8f5c7-137">Se te enviará un correo electrónico cuando las transacciones de recarga tengan éxito, cuando las transacciones de recarga no se cumplan (por ejemplo, una tarjeta de crédito expirada) y cuando el saldo de créditos de comunicaciones llegue a 0 (cero).</span><span class="sxs-lookup"><span data-stu-id="8f5c7-137">You will be sent an email when recharge transactions succeed, when recharge transactions fail (such as an expired credit card), and when your Communications Credits balance reaches 0 (zero).</span></span>
    
   - <span data-ttu-id="8f5c7-138">**Importe de recarga** Escriba la cantidad en el cuadro **Recargar** con que desea agregar a su cuenta una vez que alcance la cantidad de desencadenador que aparece a continuación.</span><span class="sxs-lookup"><span data-stu-id="8f5c7-138">**Recharge amount** Enter the amount in the **Recharge with** box that you want added to your account once it reaches the trigger amount below.</span></span>
    
   - <span data-ttu-id="8f5c7-139">**Cantidad del desencadenador** Escriba la cantidad en **Cuando el saldo esté por** debajo del cuadro que se usará para *"desencadenar"*  la recarga automática.</span><span class="sxs-lookup"><span data-stu-id="8f5c7-139">**Trigger amount** Enter the amount in **When the balance falls below** box that will be used to ' *trigger*  ' the auto-recharge.</span></span> <span data-ttu-id="8f5c7-140">Una vez que el saldo esté por debajo de esta cantidad, la cantidad de recarga se agregará automáticamente a tu cuenta.</span><span class="sxs-lookup"><span data-stu-id="8f5c7-140">Once your balance falls below this amount, the recharge amount will be added automatically to your account.</span></span>

      > [!NOTE]
     > <span data-ttu-id="8f5c7-141">Los fondos se aplicarán solo a los créditos de comunicaciones con las tarifas publicadas por Microsoft cuando se usan los servicios.</span><span class="sxs-lookup"><span data-stu-id="8f5c7-141">Funds will be applied only to Communications Credits at Microsoft published rates when the services are used.</span></span> <span data-ttu-id="8f5c7-142">Los fondos que no se usen en 12 meses desde la fecha de compra se perderán.</span><span class="sxs-lookup"><span data-stu-id="8f5c7-142">Any funds not used within 12 months of the purchase date will expire and be forfeited.</span></span> 
     > 
     > <span data-ttu-id="8f5c7-143">La facturación mensual de créditos de comunicación solo se aplicará si se ha usado el [](/skypeforbusiness/skype-for-business-online-reporting/pstn-usage-report) fondo a la vez, para obtener información sobre cómo comprobar el uso mensual, lea Skype Empresarial informe de uso de RTC</span><span class="sxs-lookup"><span data-stu-id="8f5c7-143">Monthly billing for Communication Credits will only be applied if the alloted fund has been used, to learn how to check your monthly usage, read [Skype for Business PSTN usage report](/skypeforbusiness/skype-for-business-online-reporting/pstn-usage-report)</span></span>
    
5. <span data-ttu-id="8f5c7-144">Escriba la información de pago y haga clic en **Realizar pedido**.</span><span class="sxs-lookup"><span data-stu-id="8f5c7-144">Enter your payment information and click **Place order**.</span></span>
    >[!IMPORTANT]
    ><span data-ttu-id="8f5c7-145">Si es un cliente de licencias por volumen, puede elegir su número de enterprise agreement para el pago.</span><span class="sxs-lookup"><span data-stu-id="8f5c7-145">If you are a volume licensing customer, you may choose your enterprise agreement number for payment.</span></span> <span data-ttu-id="8f5c7-146">Si tiene varios números, podrá seleccionar qué enterprise agreement prefiere usar para dicho pago.</span><span class="sxs-lookup"><span data-stu-id="8f5c7-146">If you have multiple enterprise agreement numbers, you will be able to select which enterprise agreement you would like to use for payment.</span></span> <span data-ttu-id="8f5c7-147">También podrá especificar un número de pedido de compra que asociar al número del enterprise agreement (si procede).</span><span class="sxs-lookup"><span data-stu-id="8f5c7-147">You will also be given an opportunity to specify a purchase order number to associate with the enterprise agreement number (if applicable).</span></span>
    
<span data-ttu-id="8f5c7-148">Cada organización tendrá un uso diferente del volumen y las tarifas del Plan de llamadas a tener en cuenta.</span><span class="sxs-lookup"><span data-stu-id="8f5c7-148">Each organization will have a different usage of Calling Plan volume and rates to consider.</span></span> <span data-ttu-id="8f5c7-149">You will need to get this type of usage data from your current service provider.</span><span class="sxs-lookup"><span data-stu-id="8f5c7-149">You will need to get this type of usage data from your current service provider.</span></span> <span data-ttu-id="8f5c7-150">Las organizaciones que ya usan Skype Empresarial Online como su proveedor de servicios pueden obtener datos de uso revisándose en el informe de detalles de uso rtc de informes del Centro de administración de  >    >   Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="8f5c7-150">Organizations already using Skype for Business Online already as their service provider can get usage data by reviewing it in the **Microsoft Teams admin center** > **Reports** > **PSTN usage details** report.</span></span>
  
<span data-ttu-id="8f5c7-151">Cuando esté configurando créditos de comunicaciones, tendrá que investigar el uso de llamadas de su organización para determinar los importes que necesita.</span><span class="sxs-lookup"><span data-stu-id="8f5c7-151">When you are setting up Communications Credits, you will need to investigate call usage for your organization to determine the amounts you need.</span></span> <span data-ttu-id="8f5c7-152">Puede obtener la información del uso de llamadas en el informe **Detalles de uso de RTC**.</span><span class="sxs-lookup"><span data-stu-id="8f5c7-152">You can get call usage information by reviewing the **PSTN usage details** report.</span></span> <span data-ttu-id="8f5c7-153">Este informe le permite exportar los registros de datos de llamada a Excel si necesita almacenar los datos o crear informes personalizados.</span><span class="sxs-lookup"><span data-stu-id="8f5c7-153">This report lets you export the call data records to Excel if you need to store the data or create custom reports.</span></span> <span data-ttu-id="8f5c7-154">Para obtener información sobre cómo ver el uso, lea [Informe de uso de RTC.](/skypeforbusiness/skype-for-business-online-reporting/pstn-usage-report)</span><span class="sxs-lookup"><span data-stu-id="8f5c7-154">To learn how to see usage, read [PSTN usage report](/skypeforbusiness/skype-for-business-online-reporting/pstn-usage-report).</span></span>
  
## <a name="step-3-assign-a-communications-credits-license-to-users"></a><span data-ttu-id="8f5c7-155">Paso 3: Asignar una licencia de créditos de comunicaciones a los usuarios</span><span class="sxs-lookup"><span data-stu-id="8f5c7-155">Step 3: Assign a Communications Credits license to users</span></span>

1. <span data-ttu-id="8f5c7-156">Inicie sesión en el [Microsoft 365 de administración con](https://portal.office.com/Adminportal) su cuenta de trabajo o escuela.</span><span class="sxs-lookup"><span data-stu-id="8f5c7-156">Sign in to the [Microsoft 365 admin center](https://portal.office.com/Adminportal) with your work or school account.</span></span>
    
2. <span data-ttu-id="8f5c7-157">En el panel de navegación izquierdo del Microsoft 365 de administración, vaya a Usuarios usuarios activos y, a continuación, seleccione  >  un usuario de la lista.</span><span class="sxs-lookup"><span data-stu-id="8f5c7-157">In the left navigation of the Microsoft 365 admin center, go to **Users** > **Active users**, and then select a user from the list.</span></span>
    
3. <span data-ttu-id="8f5c7-158">Elija **Licencias y aplicaciones.**</span><span class="sxs-lookup"><span data-stu-id="8f5c7-158">Choose **Licenses and Apps**.</span></span>
    
4. <span data-ttu-id="8f5c7-159">Active **Créditos de** **comunicaciones** para asignar esta licencia y, a continuación, **seleccione Guardar.**</span><span class="sxs-lookup"><span data-stu-id="8f5c7-159">Toggle **Communications Credits** to **On** to assign this license, and then select **Save**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="8f5c7-160">Incluso si tiene usuarios a los que se les ha **asignado Enterprise licencia de E5,** se recomienda que lo haga.</span><span class="sxs-lookup"><span data-stu-id="8f5c7-160">Even if you have users who are assigned an **Enterprise E5** license, it's still recommended that you do this.</span></span>

    > [!TIP]
    > <span data-ttu-id="8f5c7-161">Puede usar [Powershell para](/powershell/module/skype/?view=skype-ps) asignar licencias y aplicaciones a varios usuarios con un solo comando.</span><span class="sxs-lookup"><span data-stu-id="8f5c7-161">You can use [Powershell](/powershell/module/skype/?view=skype-ps) to assign licenses and apps to multiple users with one command.</span></span>
  
## <a name="want-to-know-about-plans-and-pricing"></a><span data-ttu-id="8f5c7-162">¿Desea obtener información acerca de los planes y los precios?</span><span class="sxs-lookup"><span data-stu-id="8f5c7-162">Want to know about plans and pricing?</span></span>

<span data-ttu-id="8f5c7-163">Puede ver los planes y precios visitando uno de los siguientes vínculos:</span><span class="sxs-lookup"><span data-stu-id="8f5c7-163">You can see the plans and pricing by visiting one of the following links:</span></span>
  
- [<span data-ttu-id="8f5c7-164">Planes de llamadas</span><span class="sxs-lookup"><span data-stu-id="8f5c7-164">Calling Plans</span></span>](https://go.microsoft.com/fwlink/?LinkId=799761 )
    
- [<span data-ttu-id="8f5c7-165">Planes de audioconferencia</span><span class="sxs-lookup"><span data-stu-id="8f5c7-165">Audio Conferencing Plans</span></span>](https://go.microsoft.com/fwlink/?LinkId=799762 )
    
- [<span data-ttu-id="8f5c7-166">Sistema telefónico Planes</span><span class="sxs-lookup"><span data-stu-id="8f5c7-166">Phone System Plans</span></span>](https://go.microsoft.com/fwlink/?LinkId=799763)
    
<span data-ttu-id="8f5c7-167">También puede ver información iniciando sesión en el centro de administración [de Microsoft 365](https://portal.office.com/adminportal/home?add=sub&amp;adminportal=1#/catalog) y yendo a Suscripciones de facturación   >    >  **Agregar suscripciones.**</span><span class="sxs-lookup"><span data-stu-id="8f5c7-167">You can also see information by [signing in to the Microsoft 365 admin center](https://portal.office.com/adminportal/home?add=sub&amp;adminportal=1#/catalog) and going to **Billing** > **Subscriptions** > **Add subscriptions**.</span></span>
  
<span data-ttu-id="8f5c7-168">Para ver una tabla con la licencia o licencias que necesitará para cada característica, vea Microsoft Teams [de complementos.](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)</span><span class="sxs-lookup"><span data-stu-id="8f5c7-168">To see a table with the license or licenses you will need for each feature, see [Microsoft Teams add-on licensing](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="8f5c7-169">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="8f5c7-169">Related topics</span></span>

- [<span data-ttu-id="8f5c7-170">Configurar Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="8f5c7-170">Set up Skype for Business Online</span></span>](/SkypeForBusiness/set-up-skype-for-business-online/set-up-skype-for-business-online)
    
- [<span data-ttu-id="8f5c7-171">Configurar el Correo de voz en la nube. Ayuda para el administrador</span><span class="sxs-lookup"><span data-stu-id="8f5c7-171">Set up Cloud Voicemail - Admin help</span></span>](set-up-phone-system-voicemail.md)
    
- <span data-ttu-id="8f5c7-172">[Configurar planes de llamadas y](set-up-calling-plans.md) planes de llamadas para Microsoft 365 o [Office 365](calling-plans-for-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="8f5c7-172">[Set up Calling Plans](set-up-calling-plans.md) and [Calling Plans for Microsoft 365 or Office 365](calling-plans-for-office-365.md)</span></span>
    
- [<span data-ttu-id="8f5c7-173">Agregar fondos y administrar los créditos de comunicaciones</span><span class="sxs-lookup"><span data-stu-id="8f5c7-173">Add funds and manage Communications Credits</span></span>](add-funds-and-manage-communications-credits.md)
    
  
