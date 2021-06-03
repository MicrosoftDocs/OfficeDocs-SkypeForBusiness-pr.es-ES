---
title: Cómo se puede usar la identificación de llamadas en su organización
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: jens, roykuntz
ms.topic: article
ms.assetid: 5a0bd8ba-3334-46ee-becf-1025597737f6
ms.tgt.pltfrm: cloud
search.appverid: MET150
ms.collection:
- M365-voice
ms.service: msteams
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Calling Plans
- ms.teamsadmincenter.voice.callerid.overview
description: El identificador de llamadas se puede controlar tanto para las llamadas entrantes como salientes para Sistema telefónico usuarios mediante una directiva denominada CallingLineIdentity.
ms.openlocfilehash: 43d3d6633ca46485aa111a7d97b9bd37b0547818
ms.sourcegitcommit: 02e243d6c58eab463a00ed45dadd80112087006e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2021
ms.locfileid: "52723551"
---
# <a name="how-can-caller-id-be-used-in-your-organization"></a><span data-ttu-id="78fad-103">Cómo se puede usar la identificación de llamadas en su organización</span><span class="sxs-lookup"><span data-stu-id="78fad-103">How can caller ID be used in your organization</span></span>

<span data-ttu-id="78fad-104">El identificador de llamada consta de dos partes de información identificables para el usuario:</span><span class="sxs-lookup"><span data-stu-id="78fad-104">Caller ID consists of two user-facing identifiable pieces of information:</span></span>

- <span data-ttu-id="78fad-105">Un número de teléfono (normalmente conocido como CLID o id. de línea de llamada).</span><span class="sxs-lookup"><span data-stu-id="78fad-105">A phone number (typically referred to as CLID or calling line ID).</span></span> <span data-ttu-id="78fad-106">Este es el número de teléfono conmutado público (RTC) que se presenta como la identificación del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="78fad-106">This is the Public Switched Telephone Number (PSTN) presented as the identification of the caller.</span></span>

- <span data-ttu-id="78fad-107">Un nombre de entidad de llamada (normalmente conocido como CNAM).</span><span class="sxs-lookup"><span data-stu-id="78fad-107">A Calling party name (typically referred to as CNAM).</span></span> 
  
<span data-ttu-id="78fad-108">La funcionalidad de identificador de llamada está disponible para todos los Sistema telefónico usuarios independientemente de la opción de conectividad RTC:</span><span class="sxs-lookup"><span data-stu-id="78fad-108">The caller ID functionality is available to all Phone System users regardless of PSTN connectivity option:</span></span>

- <span data-ttu-id="78fad-109">Planes de llamadas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="78fad-109">Microsoft Calling Plans</span></span> 

- <span data-ttu-id="78fad-110">Enrutamiento directo del sistema telefónico</span><span class="sxs-lookup"><span data-stu-id="78fad-110">Phone System Direct Routing</span></span> 
  
<span data-ttu-id="78fad-111">Puede controlar el identificador de llamadas para las llamadas entrantes y salientes mediante una directiva denominada CallingLineIdentity.</span><span class="sxs-lookup"><span data-stu-id="78fad-111">You can control Caller ID for both inbound and outbound calls by using a policy called CallingLineIdentity.</span></span> <span data-ttu-id="78fad-112">Para obtener más información, vea Más información sobre el identificador [de línea de llamadas y el nombre de la parte de llamadas.](more-about-calling-line-id-and-calling-party-name.md)</span><span class="sxs-lookup"><span data-stu-id="78fad-112">For more information, see [More about Calling Line ID and Calling Party Name](more-about-calling-line-id-and-calling-party-name.md).</span></span>

  
## <a name="outbound-pstn-caller-id"></a><span data-ttu-id="78fad-113">Identificador de llamada RTC saliente</span><span class="sxs-lookup"><span data-stu-id="78fad-113">Outbound PSTN caller ID</span></span>

<span data-ttu-id="78fad-114">Para el identificador de llamada RTC saliente, están disponibles las siguientes opciones.</span><span class="sxs-lookup"><span data-stu-id="78fad-114">For the outbound PSTN caller ID, the following options are available.</span></span> 
  
- <span data-ttu-id="78fad-115">El número de teléfono asignado al usuario, que es el predeterminado.</span><span class="sxs-lookup"><span data-stu-id="78fad-115">The telephone number assigned to the user, which is the default.</span></span>

- <span data-ttu-id="78fad-116">Anónimo, que está disponible quitando la presentación del número RTC del usuario.</span><span class="sxs-lookup"><span data-stu-id="78fad-116">Anonymous, which is available by removing the presentation of the user’s PSTN number.</span></span> 

- <span data-ttu-id="78fad-117">Un número de teléfono sustituto, que puede ser:</span><span class="sxs-lookup"><span data-stu-id="78fad-117">A substitute phone number, which can be:</span></span>

  - <span data-ttu-id="78fad-118">Un número de teléfono que se clasifica como servicio y número gratuito en el inventario de números de teléfono planes de llamadas.</span><span class="sxs-lookup"><span data-stu-id="78fad-118">A telephone number that is classified as a service and toll-free number in your Calling Plans telephone number inventory.</span></span> <span data-ttu-id="78fad-119">Normalmente se asigna a un Teams Operador automático o cola de llamadas.</span><span class="sxs-lookup"><span data-stu-id="78fad-119">It is usually assigned to a Teams Auto Attendant or Call Queue.</span></span>

  - <span data-ttu-id="78fad-120">Un número de teléfono local a través del enrutamiento directo que se asigna a una cuenta de recursos usada por una Teams Operador automático o cola de llamadas.</span><span class="sxs-lookup"><span data-stu-id="78fad-120">An on-premises telephone number through Direct Routing that is assigned to a resource account used by a Teams Auto Attendant or Call Queue.</span></span> 

- <span data-ttu-id="78fad-121">El nombre de la parte de llamada o CNAM establecido en la llamada RTC saliente.</span><span class="sxs-lookup"><span data-stu-id="78fad-121">The Calling Party Name or CNAM set on the outbound PSTN call.</span></span>  
    
<span data-ttu-id="78fad-122">Para obtener más información, vea [Establecer el identificador de llamada de un usuario.](./set-the-caller-id-for-a-user.md)</span><span class="sxs-lookup"><span data-stu-id="78fad-122">For more information, see [Set the Caller ID for a user](./set-the-caller-id-for-a-user.md).</span></span>
  
### <a name="end-user-control-of-outbound-caller-id"></a><span data-ttu-id="78fad-123">Control de usuario final del identificador de llamada saliente</span><span class="sxs-lookup"><span data-stu-id="78fad-123">End user control of outbound caller ID</span></span>

<span data-ttu-id="78fad-124">Los usuarios pueden cambiar su configuración de identificador de llamada a **Anónimo** estableciendo el atributo EnableUserOverride.</span><span class="sxs-lookup"><span data-stu-id="78fad-124">Users can change their caller ID setting to **Anonymous** by setting the EnableUserOverride attribute.</span></span> 

<span data-ttu-id="78fad-125">Si el identificador de llamada saliente se establece en Anónimo, EnableUserOverride no tiene ningún efecto y el identificador de llamada siempre se establece en Anónimo.</span><span class="sxs-lookup"><span data-stu-id="78fad-125">If the outbound caller ID is set to Anonymous, the EnableUserOverride has no effect and the caller ID is always set to Anonymous.</span></span> <span data-ttu-id="78fad-126">El valor predeterminado de EnableUserOverride es False.</span><span class="sxs-lookup"><span data-stu-id="78fad-126">The default value of EnableUserOverride is False.</span></span>

<span data-ttu-id="78fad-127">Los usuarios finales pueden establecer su identificador de llamada en Anónimo yendo **a Configuración > Llamadas** y, a continuación, en Identificador de llamada, seleccione Ocultar mi número de teléfono e información de perfil para todas las **llamadas.** </span><span class="sxs-lookup"><span data-stu-id="78fad-127">Your end users can set their caller ID to Anonymous by going to **Settings > Calls**, and then under **Caller ID**, select **Hide my phone number and profile information for all calls**.</span></span>

### <a name="notes"></a><span data-ttu-id="78fad-128">Notas</span><span class="sxs-lookup"><span data-stu-id="78fad-128">Notes</span></span>

<span data-ttu-id="78fad-129">Tenga en cuenta lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="78fad-129">Keep the following in mind:</span></span>

- <span data-ttu-id="78fad-130">No puede asignar los siguientes tipos de números de teléfono para el identificador de llamada saliente:</span><span class="sxs-lookup"><span data-stu-id="78fad-130">You can't assign the following types of phone numbers for the outbound caller ID:</span></span>

  - <span data-ttu-id="78fad-131">Cualquier número de teléfono que se clasifique como usuario en el inventario de números de teléfono planes de llamadas.</span><span class="sxs-lookup"><span data-stu-id="78fad-131">Any phone numbers that are classified as a user in your Calling Plans telephone number inventory.</span></span>

  - <span data-ttu-id="78fad-132">Cualquier número de teléfono local mediante enrutamiento directo asignado a un usuario.</span><span class="sxs-lookup"><span data-stu-id="78fad-132">Any on-premises telephone number via Direct Routing that is assigned to a user.</span></span>

  - <span data-ttu-id="78fad-133">Un Skype Empresarial Server de teléfono local.</span><span class="sxs-lookup"><span data-stu-id="78fad-133">A Skype for Business Server on-premises telephone number.</span></span>

- <span data-ttu-id="78fad-134">El uso de la sustitución de números de teléfono de cuenta de recursos solo funciona para Teams usuarios.</span><span class="sxs-lookup"><span data-stu-id="78fad-134">The use of resource account phone number substitution only works for Teams users.</span></span> <span data-ttu-id="78fad-135">La sustitución del número de teléfono de servicio funciona tanto para Skype Empresarial en línea como Teams usuarios.</span><span class="sxs-lookup"><span data-stu-id="78fad-135">The substitution of service phone number works for both Skype for Business Online and Teams users.</span></span>

- <span data-ttu-id="78fad-136">El nombre de la persona que llama solo se envía en las llamadas en las que el identificador de llamada se sustituye por LineUri, un número de teléfono de cuenta de servicio o recurso y cuando el autor de la llamada es Teams usuario.</span><span class="sxs-lookup"><span data-stu-id="78fad-136">Calling Party Name is only sent on calls where the caller ID is substituted with LineUri, a service or resource account phone number and when the caller is a Teams user.</span></span>

- <span data-ttu-id="78fad-137">El nombre de la persona que llama puede tener un máximo de 200 caracteres, pero los sistemas descendentes pueden admitir menos caracteres.</span><span class="sxs-lookup"><span data-stu-id="78fad-137">Calling Party Name can have a maximum of 200 characters, but downstream systems might support fewer characters.</span></span>

- <span data-ttu-id="78fad-138">Para enrutamiento directo, la sustitución de números de teléfono y el nombre de la parte que llama se envían en el encabezado DE SIP.</span><span class="sxs-lookup"><span data-stu-id="78fad-138">For Direct Routing, the phone number substitution and the Calling Party Name is sent in the FROM SIP header.</span></span> <span data-ttu-id="78fad-139">Si el correspondiente OnlinePstnGateway está configurado con ForwardPai = True, el encabezado SIP P-ASSERTED-IDENTITY contendrá el usuario real de las llamadas.</span><span class="sxs-lookup"><span data-stu-id="78fad-139">If the corresponding OnlinePstnGateway is configured with ForwardPai = True, the P-ASSERTED-IDENTITY SIP header will contain the real calling user.</span></span>

- <span data-ttu-id="78fad-140">EnableUserOverride tiene prioridad sobre otras opciones de configuración de la directiva, a menos que la sustitución se establezca en Anónimo.</span><span class="sxs-lookup"><span data-stu-id="78fad-140">EnableUserOverride has precedence over other settings in the policy--unless substitution is set to Anonymous.</span></span> <span data-ttu-id="78fad-141">Por ejemplo, supongamos que la instancia de directiva ha sustituido con una cuenta de recursos y el usuario establece y habilita EnableUserOverride.</span><span class="sxs-lookup"><span data-stu-id="78fad-141">For example, assume policy instance has substitution using a resource account and EnableUserOverride is set and enabled by the user.</span></span> <span data-ttu-id="78fad-142">En este caso, se bloqueará el identificador de llamada saliente y se usará Anónimo.</span><span class="sxs-lookup"><span data-stu-id="78fad-142">In this case, the outbound caller ID will be blocked and Anonymous will be used.</span></span> <span data-ttu-id="78fad-143">Si una instancia de directiva tiene establecido el valor de sustitución en Anónimo y EnableUserOverride, el identificador de llamada saliente siempre será Anónimo, independientemente de la configuración del usuario final.</span><span class="sxs-lookup"><span data-stu-id="78fad-143">If a policy instance has substitution set to Anonymous and EnableUserOverride is set, then the outbound caller ID will always be Anonymous, regardless of the end user setting.</span></span>

   
## <a name="inbound-caller-id"></a><span data-ttu-id="78fad-144">Id. de llamada entrante</span><span class="sxs-lookup"><span data-stu-id="78fad-144">Inbound caller ID</span></span>

<span data-ttu-id="78fad-145">Sistema telefónico mostrará el número de teléfono externo entrante como identificador de llamada.</span><span class="sxs-lookup"><span data-stu-id="78fad-145">Phone System will show the incoming external phone number as the caller ID.</span></span> <span data-ttu-id="78fad-146">Si el número está asociado a un usuario o contacto en Azure AD o a un contacto personal, los clientes Skype Empresarial y Teams mostrarán el identificador de llamada en función de esa información.</span><span class="sxs-lookup"><span data-stu-id="78fad-146">If the number is associated with a user or contact in Azure AD or a personal contact, the Skype for Business and Teams clients will show the caller ID based on that information.</span></span> <span data-ttu-id="78fad-147">Si el número de teléfono no está en Azure AD o en un contacto personal, el nombre para mostrar proporcionado por la compañía telefónica se mostrará si está disponible.</span><span class="sxs-lookup"><span data-stu-id="78fad-147">If the phone number is not in Azure AD or a personal contact, the telco-provided display name will be shown if it is available.</span></span>

<span data-ttu-id="78fad-148">El atributo BlockIncomingCallerID permite bloquear la identificación de llamadas en las llamadas RTC de entrada.</span><span class="sxs-lookup"><span data-stu-id="78fad-148">The BlockIncomingCallerID attribute allows for blocking the caller ID on incoming PSTN calls.</span></span> <span data-ttu-id="78fad-149">Puede establecer este atributo, pero no está disponible para los usuarios finales en la página de configuración de usuario.</span><span class="sxs-lookup"><span data-stu-id="78fad-149">You can set this attribute, but it isn't available to your end users on the user settings page.</span></span> <span data-ttu-id="78fad-150">Cuando esta configuración está habilitada, el autor de la llamada RTC entrante se mostrará como procedente de Anónimo.</span><span class="sxs-lookup"><span data-stu-id="78fad-150">When this setting is enabled the incoming PSTN caller will be displayed as coming from Anonymous.</span></span>
  
<span data-ttu-id="78fad-151">Para bloquear el identificador de llamada entrante, vea [Establecer el identificador de llamada para un usuario.](./set-the-caller-id-for-a-user.md)</span><span class="sxs-lookup"><span data-stu-id="78fad-151">To block the inbound caller ID, see [Set the Caller ID for a user](./set-the-caller-id-for-a-user.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="78fad-152">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="78fad-152">Related topics</span></span>
[<span data-ttu-id="78fad-153">Preguntas comunes sobre la transferencia de números de teléfono</span><span class="sxs-lookup"><span data-stu-id="78fad-153">Transferring phone numbers common questions</span></span>](./phone-number-calling-plans/port-order-overview.md)

[<span data-ttu-id="78fad-154">Diferentes tipos de números de teléfono que se usan para Planes de llamada</span><span class="sxs-lookup"><span data-stu-id="78fad-154">Different kinds of phone numbers used for Calling Plans</span></span>](./different-kinds-of-phone-numbers-used-for-calling-plans.md)

[<span data-ttu-id="78fad-155">Administrar los números de teléfono para su organización</span><span class="sxs-lookup"><span data-stu-id="78fad-155">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)

[<span data-ttu-id="78fad-156">Términos y condiciones de las llamadas de emergencia</span><span class="sxs-lookup"><span data-stu-id="78fad-156">Emergency calling terms and conditions</span></span>](./emergency-calling-terms-and-conditions.md)

<span data-ttu-id="78fad-157">[Skype Empresarial Online: Etiqueta de aviso de declinación de responsabilidades de las llamadas de emergencia](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="78fad-157">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>

  
