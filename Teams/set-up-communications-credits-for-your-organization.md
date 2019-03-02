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
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
- Strat_SB_PSTN
- M365-voice
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Licensing
description: 'Learn how to set up communication credits (PSTN Consumption) billing licenses for your users and organization. '
ms.openlocfilehash: 172cfef66b6f16ecd70c2ad4ea5db2918140f6cd
ms.sourcegitcommit: 59eda0c17ff39a3e6632810391d78bbadc214419
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/01/2019
ms.locfileid: "30353493"
---
# <a name="set-up-communications-credits-for-your-organization"></a><span data-ttu-id="f3357-103">Configurar Créditos de comunicaciones para su organización</span><span class="sxs-lookup"><span data-stu-id="f3357-103">Set up Communications Credits for your organization</span></span>

<span data-ttu-id="f3357-104">Debe configurar créditos de comunicaciones si pretende usar números gratuitos con Skype for Business y Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="f3357-104">You will need to set up Communications Credits if you would like to use toll-free numbers with Skype for Business and Microsoft Teams.</span></span> <span data-ttu-id="f3357-105">Además, se recomienda que configure Communications créditos para sus planes de llamada (nacional o internacional) y conferencias de Audio a los usuarios que necesitan la capacidad de marcar un número a **cualquier destino**.</span><span class="sxs-lookup"><span data-stu-id="f3357-105">Also, we recommend that you set up Communications Credits for your Calling Plans (Domestic or International) and Audio Conferencing users who need the ability to dial out to **any destination**.</span></span> <span data-ttu-id="f3357-106">Muchos países o regiones se incluyen, pero algunos destinos no pueden incluirse en las suscripciones de planeación de la llamada o conferencia de Audio.</span><span class="sxs-lookup"><span data-stu-id="f3357-106">Many countries/regions are included, but some destinations may not be included in your Calling Plan or Audio Conferencing subscriptions.</span></span> <span data-ttu-id="f3357-107">Si no configura créditos de comunicaciones de facturación y asigna una licencia de **Créditos de comunicaciones** a los usuarios y ejecutar minutos para la organización (dependiendo del Plan de llamada o conferencia de Audio plan en su país o región), esos usuarios no podrá realizar llamadas o marcar un número de las reuniones de conferencia de Audio.</span><span class="sxs-lookup"><span data-stu-id="f3357-107">If you don't set up Communications Credits billing and assign a **Communications Credits** license to your users and you run out minutes for your organization (depending on your Calling Plan or Audio Conferencing plan in your country/region), those users won't be able to make calls or dial out from Audio Conferencing meetings.</span></span> <span data-ttu-id="f3357-108">Puede obtener más información, recomienda incluir fondos importes, mediante la lectura de [¿Cuáles son las comunicaciones créditos?](what-are-communications-credits.md)</span><span class="sxs-lookup"><span data-stu-id="f3357-108">You can get more information, including recommended funding amounts, by reading [What are Communications Credits?](what-are-communications-credits.md)</span></span>
  
> [!NOTE]
> <span data-ttu-id="f3357-109">Para saber cuánto cuesta, [consulte aquí las tarifas](https://go.microsoft.com/fwlink/p/?LinkId=799523 ).</span><span class="sxs-lookup"><span data-stu-id="f3357-109">To find out how much it costs, [see the rates here](https://go.microsoft.com/fwlink/p/?LinkId=799523 ).</span></span> 
  
## <a name="step-1-assign-an-audio-conferencing-and-calling-plan-license-to-your-users"></a><span data-ttu-id="f3357-110">Paso 1: Asignar una licencia de conferencias de Audio y la planeación de la llamada a los usuarios</span><span class="sxs-lookup"><span data-stu-id="f3357-110">Step 1: Assign an Audio Conferencing and Calling Plan license to your users</span></span>

<span data-ttu-id="f3357-111">Cuando se suscriba, obtenga un cierto número de minutos dependiendo de su país o región.</span><span class="sxs-lookup"><span data-stu-id="f3357-111">When you sign up, you get a certain number of minutes depending on your country/region.</span></span> <span data-ttu-id="f3357-112">Puede ver el número de minutos que obtiene la búsqueda para el país o la región [aquí](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).</span><span class="sxs-lookup"><span data-stu-id="f3357-112">You can see the number of minutes you will get search for the country or region [here](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).</span></span> <span data-ttu-id="f3357-113">Después de usar esos minutos, las llamadas se desconectarán.</span><span class="sxs-lookup"><span data-stu-id="f3357-113">After you use those minutes, calls will be disconnected.</span></span> <span data-ttu-id="f3357-114">Para evitar que esto ocurra, debe configurar Communications créditos.</span><span class="sxs-lookup"><span data-stu-id="f3357-114">To prevent this from happening, you need to set up Communications Credits.</span></span>
  
<span data-ttu-id="f3357-115">Para ello, **es necesario asignarle una conferencia de Audio o el sistema telefónico licencia** a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="f3357-115">To do so, **you need to assign an Audio Conferencing or Phone System license** to your users.</span></span>
  
- <span data-ttu-id="f3357-116">Asignar una licencia de **Conferencias de Audio** a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="f3357-116">Assign an **Audio Conferencing** license to your users.</span></span> <span data-ttu-id="f3357-117">Vea [las licencias de asignar los equipos de Microsoft](assign-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="f3357-117">See [Assign Microsoft Teams licenses](assign-teams-licenses.md).</span></span>
    
    <span data-ttu-id="f3357-118">Después de asignar esta licencia, debe configurar conferencias de audio.</span><span class="sxs-lookup"><span data-stu-id="f3357-118">After you assign this license, you will need to set up audio conferencing.</span></span> <span data-ttu-id="f3357-119">Para obtener instrucciones detalladas, vea [probar o comprar conferencias de Audio en Office 365](try-or-purchase-audio-conferencing-in-office-365-for-teams.md).</span><span class="sxs-lookup"><span data-stu-id="f3357-119">For step-by-step instructions, see [Try or purchase Audio Conferencing in Office 365](try-or-purchase-audio-conferencing-in-office-365-for-teams.md).</span></span>
    
- <span data-ttu-id="f3357-120">Asignar el **Sistema telefónico** y una licencia de llamar a planear nacional o nacional e internacional a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="f3357-120">Assign **Phone System** and a domestic or domestic and international Calling Plan license to your users.</span></span> <span data-ttu-id="f3357-121">Vea [las licencias de asignar los equipos de Microsoft](assign-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="f3357-121">See [Assign Microsoft Teams licenses](assign-teams-licenses.md).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="f3357-122">Aunque no es necesario para comunicaciones créditos, deberá asignar también un **Llamar a planear nacionales** o una licencia **nacionales y llamar a planear internacional** .</span><span class="sxs-lookup"><span data-stu-id="f3357-122">Although it's not required for Communications Credits, you still need to also assign a **Domestic Calling Plan** or an **Domestic and International Calling Plan** license.</span></span>
  
    <span data-ttu-id="f3357-123">Después de asignar estas licencias, tendrá que obtener sus números de teléfono para la organización y asignarlos a los miembros de su organización.</span><span class="sxs-lookup"><span data-stu-id="f3357-123">After you assign these licenses, you will need to get your phone numbers for your organization, and then assign those numbers to the people in your organization.</span></span> <span data-ttu-id="f3357-124">Para obtener instrucciones detalladas, consulte [Configurar planes de llamada](set-up-calling-plans.md).</span><span class="sxs-lookup"><span data-stu-id="f3357-124">For step-by-step instructions, see [Set up Calling Plans](set-up-calling-plans.md).</span></span>
    
<span data-ttu-id="f3357-125">Para obtener más información, vea [licencias de complemento de equipos de Microsoft](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)</span><span class="sxs-lookup"><span data-stu-id="f3357-125">For more information, see [Microsoft Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)</span></span>
  
## <a name="step-2-set-up-communications-credits-for-your-organization"></a><span data-ttu-id="f3357-126">Paso 2: Configurar Communications créditos para su organización</span><span class="sxs-lookup"><span data-stu-id="f3357-126">Step 2: Set up Communications Credits for your organization</span></span>

1. <span data-ttu-id="f3357-127">Inicie sesión en Office 365 con su cuenta profesional o educativa.</span><span class="sxs-lookup"><span data-stu-id="f3357-127">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="f3357-128">En la izquierda el centro de administración de Office 365, vaya a **facturación** > **suscripciones** > **Agregar suscripciones**.</span><span class="sxs-lookup"><span data-stu-id="f3357-128">In the left navigation of the Office 365 admin center, go to **Billing** > **Subscriptions** > **Add subscriptions**.</span></span>

3. <span data-ttu-id="f3357-129">Expanda **las suscripciones del complemento**y, a continuación, elija **Communications créditos** > **comprar ahora**.</span><span class="sxs-lookup"><span data-stu-id="f3357-129">Expand **Add-on subscriptions**, and then choose **Communications Credits** > **Buy now**.</span></span>
    
4. <span data-ttu-id="f3357-130">En la página de suscripción de **Créditos Communications** , rellene la información y, a continuación, haga clic en **siguiente**:</span><span class="sxs-lookup"><span data-stu-id="f3357-130">On the **Communications Credits** subscription page, fill in your information, and then click **Next**:</span></span>
    
   - <span data-ttu-id="f3357-131">**Agregar fondos** Escriba la cantidad que se desea agregar a su cuenta.</span><span class="sxs-lookup"><span data-stu-id="f3357-131">**Add funds** Enter the amount that you want to add to your account.</span></span> <span data-ttu-id="f3357-132">Si no habilita auto-recarga, una vez que se agota estos fondos, se interrumpirá la llamada capacidades que están habilitadas utilizando créditos Communications (por ejemplo, un servicio gratuito entrante).</span><span class="sxs-lookup"><span data-stu-id="f3357-132">If you don't enable auto-recharge, once these funds are depleted, calling capabilities that are enabled using Communications Credits will be disrupted (such as inbound toll-free service).</span></span> <span data-ttu-id="f3357-133">Para evitar tener que reabastecer manualmente su saldo Communications créditos cada vez que su saldo llega a 0 (cero), se recomienda que habilitar la característica auto-recarga.</span><span class="sxs-lookup"><span data-stu-id="f3357-133">To avoid having to manually replenish your Communications Credits balance each time your balance reaches 0 (zero), we recommend you enable the auto-recharge feature.</span></span>
    
   - <span data-ttu-id="f3357-134">**Recarga automática** Si habilita la recarga automática, ls cuenta se rellenará automáticamente cuando el saldo esté por debajo del umbral que establezca.</span><span class="sxs-lookup"><span data-stu-id="f3357-134">**Auto-recharge** Enabling auto-recharge will automatically refill your account when the balance falls below the threshold that you set.</span></span>
    
     <span data-ttu-id="f3357-135">Se recomienda que utilice la opción **automático recarga** para evitar cualquier interrupción del servicio debe su saldo Communications créditos llegar a 0 (cero).</span><span class="sxs-lookup"><span data-stu-id="f3357-135">It's recommended that you use the **Auto-recharge** setting to avoid any disruption of service should your Communications Credits balance reach 0 (zero).</span></span> <span data-ttu-id="f3357-136">Se le enviará un correo electrónico cuando se realizan con éxito en las transacciones de recarga, cuando las transacciones de recarga producirá un error (por ejemplo, una tarjeta de crédito caducada) y cuando su saldo Communications créditos llega a 0 (cero).</span><span class="sxs-lookup"><span data-stu-id="f3357-136">You will be sent an email when recharge transactions succeed, when recharge transactions fail (such as an expired credit card), and when your Communications Credits balance reaches 0 (zero).</span></span>
    
   - <span data-ttu-id="f3357-137">**Recargar el importe** Escriba la cantidad en el cuadro **recargue con la** que desee agregar a su cuenta una vez que alcanza la cantidad de desencadenador que aparece a continuación.</span><span class="sxs-lookup"><span data-stu-id="f3357-137">**Recharge amount** Enter the amount in the **Recharge with** box that you want added to your account once it reaches the trigger amount below.</span></span>
    
   - <span data-ttu-id="f3357-138">**Cantidad de desencadenador** Escriba la cantidad en **cuando el saldo cae por debajo de** cuadro que se va a usar para ' *desencadenador* ' la recarga automático.</span><span class="sxs-lookup"><span data-stu-id="f3357-138">**Trigger amount** Enter the amount in **When the balance falls below** box that will be used to ' *trigger*  ' the auto-recharge.</span></span> <span data-ttu-id="f3357-139">Una vez que su saldo cae por debajo de esta cantidad, la cantidad de recarga se agregará automáticamente a su cuenta.</span><span class="sxs-lookup"><span data-stu-id="f3357-139">Once your balance falls below this amount, the recharge amount will be added automatically to your account.</span></span>

      > [!NOTE]
     > <span data-ttu-id="f3357-140">Fondos se aplicará sólo a créditos Communications en Microsoft publicado tasas cuando se usan los servicios.</span><span class="sxs-lookup"><span data-stu-id="f3357-140">Funds will be applied only to Communications Credits at Microsoft published rates when the services are used.</span></span> <span data-ttu-id="f3357-141">Los fondos que no se usen en 12 meses desde la fecha de compra se perderán.</span><span class="sxs-lookup"><span data-stu-id="f3357-141">Any funds not used within 12 months of the purchase date will expire and be forfeited.</span></span> 
    
5. <span data-ttu-id="f3357-142">Escriba la información de pago y haga clic en **Realizar pedido**.</span><span class="sxs-lookup"><span data-stu-id="f3357-142">Enter your payment information and click **Place order**.</span></span>
    >[!IMPORTANT]
    ><span data-ttu-id="f3357-143">Si es un cliente de licencias por volumen, puede elegir su número de enterprise agreement para el pago.</span><span class="sxs-lookup"><span data-stu-id="f3357-143">If you are a volume licensing customer, you may choose your enterprise agreement number for payment.</span></span> <span data-ttu-id="f3357-144">Si tiene varios números, podrá seleccionar qué enterprise agreement prefiere usar para dicho pago.</span><span class="sxs-lookup"><span data-stu-id="f3357-144">If you have multiple enterprise agreement numbers, you will be able to select which enterprise agreement you would like to use for payment.</span></span> <span data-ttu-id="f3357-145">También podrá especificar un número de pedido de compra que asociar al número del enterprise agreement (si procede).</span><span class="sxs-lookup"><span data-stu-id="f3357-145">You will also be given an opportunity to specify a purchase order number to associate with the enterprise agreement number (if applicable).</span></span>
    
<span data-ttu-id="f3357-146">Cada organización va a tener un uso diferente de volumen de una llamada a planear e índices a tener en cuenta.</span><span class="sxs-lookup"><span data-stu-id="f3357-146">Each organization will have a different usage of Calling Plan volume and rates to consider.</span></span> <span data-ttu-id="f3357-147">You will need to get this type of usage data from your current service provider.</span><span class="sxs-lookup"><span data-stu-id="f3357-147">You will need to get this type of usage data from your current service provider.</span></span> <span data-ttu-id="f3357-148">Las organizaciones que ya utilizan Skype para profesionales Online ya como su proveedor de servicios pueden obtener datos de uso mediante la revisión en el **Skype para el centro de administración de negocio** > **informes** > informe de**Detalles de uso de RTC** .</span><span class="sxs-lookup"><span data-stu-id="f3357-148">Organizations already using Skype for Business Online already as their service provider can get usage data by reviewing it in the **Skype for Business admin center** > **Reports** > **PSTN usage details** report.</span></span>
  
<span data-ttu-id="f3357-149">Cuando está configurando créditos Communications, debe investigar el uso de la llamada de la organización determinar los importes que necesitará para poner en.</span><span class="sxs-lookup"><span data-stu-id="f3357-149">When you are setting up Communications Credits, you will need to investigate call usage for your organization to determine the amounts that you will need to put in.</span></span> <span data-ttu-id="f3357-150">Puede obtener la información del uso de llamadas en el informe **Detalles de uso de RTC**.</span><span class="sxs-lookup"><span data-stu-id="f3357-150">You can get call usage information by reviewing the **PSTN usage details** report.</span></span> <span data-ttu-id="f3357-151">Este informe le permite exportar los registros de datos de la llamada a Excel si desea exportar los datos para el almacenamiento o crear informes personalizados.</span><span class="sxs-lookup"><span data-stu-id="f3357-151">This report lets you export the call data records to Excel if you want to export the data for storage or create custom reports.</span></span> <span data-ttu-id="f3357-152">Para ver el uso, vea [Skype para el informe de uso de RTC de negocio](/SkypeForBusiness/skype-for-business-online-reporting/pstn-usage-report)</span><span class="sxs-lookup"><span data-stu-id="f3357-152">To see usage, see [Skype for Business PSTN usage report](/SkypeForBusiness/skype-for-business-online-reporting/pstn-usage-report)</span></span>
  
## <a name="step-3-assign-a-communications-credits-license-to-users"></a><span data-ttu-id="f3357-153">Paso 3: Asignar una licencia de créditos de comunicaciones a los usuarios</span><span class="sxs-lookup"><span data-stu-id="f3357-153">Step 3: Assign a Communications Credits license to users</span></span>

1. <span data-ttu-id="f3357-154">Inicie sesión en Office 365 con su cuenta profesional o educativa.</span><span class="sxs-lookup"><span data-stu-id="f3357-154">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="f3357-155">En la izquierda el centro de administración de Office 365, vaya a **los usuarios** > **usuarios activos**y, a continuación, seleccione un usuario o usuarios de la lista.</span><span class="sxs-lookup"><span data-stu-id="f3357-155">In the left navigation of the Office 365 admin center, go to **Users** > **Active users**, and then select a user or users from the list.</span></span>
    
3. <span data-ttu-id="f3357-156">En el panel de acciones, en **Licencias de productos**, haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="f3357-156">In the Action pane under **Product licenses**, click **Edit**.</span></span>
    
4. <span data-ttu-id="f3357-157">En la página **licencias de producto** , alternar **Communications créditos** **en** para asignar esta licencia y, a continuación, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="f3357-157">On the **Product licenses** page, toggle **Communications Credits** to **On** to assign this license, and then click **Save**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="f3357-158">Incluso si tiene usuarios que tengan asignados una licencia **Enterprise E5** , sigue siendo recomendable hacer esto.</span><span class="sxs-lookup"><span data-stu-id="f3357-158">Even if you have users who are assigned an **Enterprise E5** license, it's still recommended that you do this.</span></span>
  
## <a name="want-to-know-about-plans-and-pricing"></a><span data-ttu-id="f3357-159">¿Desea obtener información acerca de los planes y los precios?</span><span class="sxs-lookup"><span data-stu-id="f3357-159">Want to know about plans and pricing?</span></span>

<span data-ttu-id="f3357-160">Puede ver los planes y precios, visite uno de los siguientes vínculos:</span><span class="sxs-lookup"><span data-stu-id="f3357-160">You can see the plans and pricing by visiting one of the following links:</span></span>
  
- [<span data-ttu-id="f3357-161">Planes de llamadas</span><span class="sxs-lookup"><span data-stu-id="f3357-161">Calling Plans</span></span>](https://go.microsoft.com/fwlink/?LinkId=799761 )
    
- [<span data-ttu-id="f3357-162">Planes de conferencias de audio</span><span class="sxs-lookup"><span data-stu-id="f3357-162">Audio Conferencing Plans</span></span>](https://go.microsoft.com/fwlink/?LinkId=799762 )
    
- [<span data-ttu-id="f3357-163">Planes de sistema de teléfono</span><span class="sxs-lookup"><span data-stu-id="f3357-163">Phone System Plans</span></span>](https://go.microsoft.com/fwlink/?LinkId=799763)
    
<span data-ttu-id="f3357-164">También puede ver información iniciando [sesión en el centro de administración de Office 365](https://portal.office.com/adminportal/home?add=sub&amp;adminportal=1#/catalog) y va a **facturación** > **suscripciones** > **Agregar suscripciones**.</span><span class="sxs-lookup"><span data-stu-id="f3357-164">You can also see information by [signing in to the Office 365 admin center](https://portal.office.com/adminportal/home?add=sub&amp;adminportal=1#/catalog) and going to **Billing** > **Subscriptions** > **Add subscriptions**.</span></span>
  
<span data-ttu-id="f3357-165">Para ver una tabla con la licencia o licencias que necesitará para cada característica, vea [licencias de complemento de equipos de Microsoft](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="f3357-165">To see a table with the license or licenses you will need for each feature, see [Microsoft Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="f3357-166">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="f3357-166">Related topics</span></span>

- [<span data-ttu-id="f3357-167">Configurar Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="f3357-167">Set up Skype for Business Online</span></span>](/SkypeForBusiness/set-up-skype-for-business-online/set-up-skype-for-business-online)
    
- [<span data-ttu-id="f3357-168">Configurar el correo de voz de Sistema telefónico - Ayuda para el administrador</span><span class="sxs-lookup"><span data-stu-id="f3357-168">Set up Phone System voicemail - Admin help</span></span>](set-up-phone-system-voicemail.md)
    
- <span data-ttu-id="f3357-169">[Configurar planes de llamada](set-up-calling-plans.md) y [Planes de llamada de Office 365](calling-plans-for-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="f3357-169">[Set up Calling Plans](set-up-calling-plans.md) and [Calling Plans for Office 365](calling-plans-for-office-365.md)</span></span>
    
- [<span data-ttu-id="f3357-170">Agregar fondos y administrar los créditos de comunicaciones</span><span class="sxs-lookup"><span data-stu-id="f3357-170">Add funds and manage Communications Credits</span></span>](add-funds-and-manage-communications-credits.md)
    
  
 