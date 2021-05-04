---
title: Configurar Microsoft 365 Business Voice
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
description: Obtenga información sobre cómo configurar Microsoft 365 Business Voice en su pequeña o mediana empresa u organización.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 534005df5161a69fd64ac94c444046508b9d7fd1
ms.sourcegitcommit: 49cdcf344c63c805bcb6365804c6f5d1393e926a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2021
ms.locfileid: "52130489"
---
# <a name="set-up-microsoft-365-business-voice"></a><span data-ttu-id="bcccf-103">Configurar Microsoft 365 Business Voice</span><span class="sxs-lookup"><span data-stu-id="bcccf-103">Set up Microsoft 365 Business Voice</span></span>

<span data-ttu-id="bcccf-104">Business Voice es un sistema telefónico completo que puede reemplazar a su proveedor de telefonía existente.</span><span class="sxs-lookup"><span data-stu-id="bcccf-104">Business Voice is a complete phone system that can replace your existing telephony provider.</span></span> <span data-ttu-id="bcccf-105">Tanto si es una empresa nueva configurando números de teléfono por primera vez, como si una empresa establecida se mueve de un proveedor de telefonía local heredado, los pasos de estos artículos pueden ayudarle a moverse con Business Voice.</span><span class="sxs-lookup"><span data-stu-id="bcccf-105">Whether you're a new business setting up phone numbers for the first time, or an established business moving from a legacy on-premises telephony provider, the steps in these articles can help you get up and running with Business Voice.</span></span> <span data-ttu-id="bcccf-106">Cuando haya terminado de configurar Business Voice:</span><span class="sxs-lookup"><span data-stu-id="bcccf-106">When you're finished setting up Business Voice:</span></span>

* <span data-ttu-id="bcccf-107">Podrás recibir llamadas telefónicas gratuitas o de pago en una línea telefónica de la compañía principal.</span><span class="sxs-lookup"><span data-stu-id="bcccf-107">You'll be able to receive toll or toll-free phone calls on a main company phone line.</span></span> <span data-ttu-id="bcccf-108">Incluso puede configurar un menú de llamada si lo desea.</span><span class="sxs-lookup"><span data-stu-id="bcccf-108">You can even set up a call menu if you want.</span></span>
* <span data-ttu-id="bcccf-109">Los usuarios configurados con Business Voice tendrán sus propios números de teléfono de marcado directo que pueden usar para realizar y recibir llamadas telefónicas desde cualquier dispositivo con Teams instalado.</span><span class="sxs-lookup"><span data-stu-id="bcccf-109">Users set up with Business Voice will have their own direct-dial phone numbers that they can use to make and receive phone calls from any device with Teams installed.</span></span>
* <span data-ttu-id="bcccf-110">Los participantes de la reunión podrán llamar a reuniones con un teléfono normal si no pueden unirse desde un Teams cliente.</span><span class="sxs-lookup"><span data-stu-id="bcccf-110">Meeting participants will be able to call in to meetings using a regular phone if they're unable to join from a Teams client.</span></span>
* <span data-ttu-id="bcccf-111">Si tiene números de teléfono existentes, podrá seguir usándolos después de moverlos a Business Voice.</span><span class="sxs-lookup"><span data-stu-id="bcccf-111">If you have existing phone numbers, you'll be able to continue using them after they're moved to Business Voice.</span></span>

<span data-ttu-id="bcccf-112">Si desea obtener más información sobre Business Voice, consulte [¿Qué Microsoft 365 Business Voice?](whats-business-voice.md).</span><span class="sxs-lookup"><span data-stu-id="bcccf-112">If you want to learn more about Business Voice, check out [What is Microsoft 365 Business Voice?](whats-business-voice.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bcccf-113">La información de estos artículos solo se aplica a Business Voice **con** plan de llamadas.</span><span class="sxs-lookup"><span data-stu-id="bcccf-113">The information in these articles is applicable to Business Voice **with** Calling Plan only.</span></span> <span data-ttu-id="bcccf-114">El plan de llamadas de Business Voice está disponible solo en determinados países y regiones.</span><span class="sxs-lookup"><span data-stu-id="bcccf-114">Business Voice with Calling Plan is available only in select countries and regions.</span></span> <span data-ttu-id="bcccf-115">Antes de empezar a configurar Business Voice, compruebe la disponibilidad de país y región para [Business Voice](country-region-availability.md) para ver si su país o región admite Business Voice con plan de llamadas.</span><span class="sxs-lookup"><span data-stu-id="bcccf-115">Before you start setting up Business Voice, check [Country and region availability for Business Voice](country-region-availability.md) to see whether your country or region supports Business Voice with Calling Plan.</span></span>
>
> <span data-ttu-id="bcccf-116">Si su espacio empresarial se encuentra en un país o región que no admita el plan de llamadas de Business Voice, consulte [Obtener ayuda de un revendedor o partner de Microsoft](reseller-partner-support.md).</span><span class="sxs-lookup"><span data-stu-id="bcccf-116">If your tenant is located in a country or region that doesn't support Business Voice with Calling Plan, check out [Get help from a Microsoft reseller or partner](reseller-partner-support.md).</span></span>
>
> <span data-ttu-id="bcccf-117">Microsoft Teams y Business Voice solo funcionan cuando los buzones de los usuarios se encuentran ubicados en Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="bcccf-117">Microsoft Teams and Business Voice only work when your users' mailboxes are located in Microsoft 365.</span></span>  <span data-ttu-id="bcccf-118">No admiten buzones de correo en servidores de Exchange locales.</span><span class="sxs-lookup"><span data-stu-id="bcccf-118">They don't support mailboxes on on-premises Exchange Server.</span></span>
>
> <span data-ttu-id="bcccf-119">Este proceso de configuración no admite Skype Empresarial implementaciones híbridas.</span><span class="sxs-lookup"><span data-stu-id="bcccf-119">This setup process doesn't support Skype for Business hybrid deployments.</span></span> <span data-ttu-id="bcccf-120">Si tiene una implementación híbrida de Skype Empresarial y quiere configurar Business Voice, consulte [Configurar el sistema telefónico en la organización](../setting-up-your-phone-system.md).</span><span class="sxs-lookup"><span data-stu-id="bcccf-120">If you have a Skype for Business hybrid deployment and want to set up Business Voice, check out [Set up Phone System in your organization](../setting-up-your-phone-system.md).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="bcccf-121">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="bcccf-121">Before you begin</span></span>

<span data-ttu-id="bcccf-122">Antes de configurar Business Voice, hay algunas cosas que debe hacer.</span><span class="sxs-lookup"><span data-stu-id="bcccf-122">Before you set up Business Voice, there are a few things you need to do.</span></span> <span data-ttu-id="bcccf-123">Las siguientes tareas se asegurarán de que su organización esté lista para Business Voice.</span><span class="sxs-lookup"><span data-stu-id="bcccf-123">The following tasks will make sure your organization is ready for Business Voice.</span></span>

* <span data-ttu-id="bcccf-124">**Compre licencias de Business Voice** y, si desea obtener un número gratuito o realizar llamadas telefónicas de larga distancia, créditos de comunicación.</span><span class="sxs-lookup"><span data-stu-id="bcccf-124">**Buy Business Voice licenses** and, if you want to get a toll-free number or make long-distance phone calls, Communication Credits.</span></span> <span data-ttu-id="bcccf-125">Para obtener más información, vea [¿Qué necesito comprar para usar Microsoft 365 Business Voice?](what-to-buy.md).</span><span class="sxs-lookup"><span data-stu-id="bcccf-125">For more information, see [What do I need to buy to use Microsoft 365 Business Voice?](what-to-buy.md).</span></span>
* <span data-ttu-id="bcccf-126">**Asegúrese de que su conexión a Internet puede admitir Business Voice.**</span><span class="sxs-lookup"><span data-stu-id="bcccf-126">**Make sure your Internet connection can support Business Voice**.</span></span> <span data-ttu-id="bcccf-127">Para obtener más información, vea [Comprobar la conexión a Internet para Business Voice.](get-ready-internet.md)</span><span class="sxs-lookup"><span data-stu-id="bcccf-127">For more information, see [Check your Internet connection for Business Voice](get-ready-internet.md).</span></span>
* <span data-ttu-id="bcccf-128">**Configure Teams en los dispositivos** de los usuarios, configure saludos de correo de voz y ayude a los usuarios a obtener información sobre Teams.</span><span class="sxs-lookup"><span data-stu-id="bcccf-128">**Set up Teams on your users' devices**, set up voicemail greetings, and help your users learn about Teams.</span></span> <span data-ttu-id="bcccf-129">Para obtener más información, vea ¿Cómo puedo preparar a mis [usuarios para Microsoft 365 Business Voice?](prepare-users.md).</span><span class="sxs-lookup"><span data-stu-id="bcccf-129">For more information, see [How do I get my users ready for Microsoft 365 Business Voice?](prepare-users.md).</span></span>

<span data-ttu-id="bcccf-130">Después de preparar su organización para Business Voice, seleccione **Siguiente paso: Empezar a configurar Business Voice**.</span><span class="sxs-lookup"><span data-stu-id="bcccf-130">After you've prepare your organization for Business Voice, select **Next step: Start setting up Business Voice**.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="bcccf-131">Siguiente paso: Empezar a configurar Business Voice</span><span class="sxs-lookup"><span data-stu-id="bcccf-131">Next step: Start setting up Business Voice</span></span>](set-up-emergency-locations.md)
