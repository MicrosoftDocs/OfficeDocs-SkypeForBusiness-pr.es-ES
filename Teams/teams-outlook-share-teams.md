---
title: Compartir en Teams
author: cichur
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: kblevens
localization_priority: Normal
search.appverid: MET150
description: Obtenga información sobre la característica Compartir en Teams, que permite a los usuarios compartir correos electrónicos y datos adjuntos de correo electrónico desde Outlook a cualquier chat o canal de Teams.
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: af5c2f6029b0c5314c507de7734abf8c479af709
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51098226"
---
# <a name="share-to-teams-from-outlook"></a><span data-ttu-id="41697-103">Compartir en Teams desde Outlook</span><span class="sxs-lookup"><span data-stu-id="41697-103">Share to Teams from Outlook</span></span>

<span data-ttu-id="41697-104">Compartir en Teams desde Outlook (Compartir en Teams) permite a los usuarios compartir correos electrónicos, incluidos los datos adjuntos, desde Outlook a cualquier chat o canal en Teams.</span><span class="sxs-lookup"><span data-stu-id="41697-104">Share to Teams from Outlook (Share to Teams) enables users to share emails, including attachments, from Outlook to any chat or channel in Teams.</span></span>

## <a name="outlook-add-in-for-share-to-teams"></a><span data-ttu-id="41697-105">Complemento de Outlook para compartir en Teams</span><span class="sxs-lookup"><span data-stu-id="41697-105">Outlook add-in for Share to Teams</span></span> 

<span data-ttu-id="41697-106">La característica Compartir en Teams requiere un complemento para Outlook.</span><span class="sxs-lookup"><span data-stu-id="41697-106">The Share to Teams feature requires an add-in for Outlook.</span></span> <span data-ttu-id="41697-107">Este complemento se instala automáticamente siempre que un usuario inicie sesión en la aplicación web de Teams o en el cliente de escritorio de Teams.</span><span class="sxs-lookup"><span data-stu-id="41697-107">This add-in is installed automatically whenever a user logs on to either the Teams Web app or the Teams desktop client.</span></span>

> [!NOTE]
> <span data-ttu-id="41697-108">Asegúrese de revisar complementos para Outlook en [Exchange Online](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/add-ins-for-outlook) y reglas de acceso de cliente en [Exchange Online](/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules) para asegurarse de que los complementos para Outlook funcionan correctamente.</span><span class="sxs-lookup"><span data-stu-id="41697-108">Be sure to review [Add-ins for Outlook in Exchange Online](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/add-ins-for-outlook) and [Client Access Rules in Exchange Online](/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules) to make sure your add-ins for Outlook function correctly.</span></span> <span data-ttu-id="41697-109">Además, deshabilitar las experiencias conectadas puede impedir que los complementos de Outlook funcionen correctamente.</span><span class="sxs-lookup"><span data-stu-id="41697-109">Also, disabling connected experiences can prevent add-ins for Outlook from working properly.</span></span> <span data-ttu-id="41697-110">Vea [Experiencias conectadas en Office](https://support.microsoft.com/topic/connected-experiences-in-office-8d2c04f7-6428-4e6e-ac58-5828d4da5b7c) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="41697-110">See [Connected experiences in Office](https://support.microsoft.com/topic/connected-experiences-in-office-8d2c04f7-6428-4e6e-ac58-5828d4da5b7c) for more information.</span></span>  

<span data-ttu-id="41697-111">Compartir en Teams usa el mismo mecanismo de transporte que cuando un usuario envía un correo electrónico a un canal.</span><span class="sxs-lookup"><span data-stu-id="41697-111">Share to Teams uses the same transport mechanism as when a user emails a channel.</span></span> <span data-ttu-id="41697-112">Para compartir en chats, los correos electrónicos (incluidos los datos adjuntos de correo electrónico) se copian en OneDrive del remitente.</span><span class="sxs-lookup"><span data-stu-id="41697-112">For sharing to chats, emails (including email attachments) are copied to the sender’s OneDrive.</span></span> <span data-ttu-id="41697-113">Para compartir con canales, los correos electrónicos y los datos adjuntos se copian en la carpeta **Mensajes de** correo electrónico de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="41697-113">For sharing to channels, emails and attachments are copied to the **Email messages** folder in SharePoint.</span></span>

<span data-ttu-id="41697-114">El complemento de Outlook para compartir en Teams usa el conjunto de requisitos 1.7, como se detalla en la documentación de complementos de [Outlook,](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/add-ins-for-outlook)que incluye detalles sobre complementos de Outlook, requisitos de entorno para complementos de Outlook y los clientes específicos de Outlook compatibles con el conjunto de requisitos 1.7.</span><span class="sxs-lookup"><span data-stu-id="41697-114">The Outlook add-in for Share to Teams uses requirement set 1.7, as detailed in [Outlook add-ins documentation](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/add-ins-for-outlook), which includes details on Outlook add-ins, environment requirements for Outlook add-ins, and the specific Outlook clients that are supported with requirement set 1.7.</span></span>

## <a name="enabling-or-disabling-share-to-teams"></a><span data-ttu-id="41697-115">Habilitar o deshabilitar Compartir en Teams</span><span class="sxs-lookup"><span data-stu-id="41697-115">Enabling or disabling Share to Teams</span></span>

<span data-ttu-id="41697-116">El complemento de Outlook para compartir en Teams se puede deshabilitar o habilitar selectivamente por usuario con los siguientes cmdlets de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="41697-116">The Outlook add-in for Share to Teams can be selectively disabled or enabled on a per-user basis using the following PowerShell cmdlets.</span></span>

> [!NOTE]
> <span data-ttu-id="41697-117">Deshabilitar el complemento solo es posible después de instalar el complemento.</span><span class="sxs-lookup"><span data-stu-id="41697-117">Disabling the add-in is only possible after the add-in has been installed.</span></span> <span data-ttu-id="41697-118">Si desea exigir la deshabilitación para todos los usuarios de su inquilino, ejecute un script periódicamente.</span><span class="sxs-lookup"><span data-stu-id="41697-118">If you would like to enforce disabling for all users in your tenant, run a script periodically.</span></span>

<span data-ttu-id="41697-119">Para deshabilitar el complemento para Outlook que usa Compartir en Teams, ejecute el [cmdlet que se encuentra aquí.](/powershell/module/exchange/disable-app?view=exchange-ps)</span><span class="sxs-lookup"><span data-stu-id="41697-119">To disable the add-in for Outlook used by Share to Teams, run the [cmdlet found here](/powershell/module/exchange/disable-app?view=exchange-ps).</span></span> 

<span data-ttu-id="41697-120">Para habilitar el complemento para Outlook que usa Compartir en Teams, ejecute el [cmdlet que se encuentra aquí.](/powershell/module/exchange/enable-app?view=exchange-ps)</span><span class="sxs-lookup"><span data-stu-id="41697-120">To enable the add-in for Outlook used by Share to Teams, run the [cmdlet found here](/powershell/module/exchange/enable-app?view=exchange-ps).</span></span>

## <a name="browsers-and-single-sign-on"></a><span data-ttu-id="41697-121">Exploradores y inicio de sesión único</span><span class="sxs-lookup"><span data-stu-id="41697-121">Browsers and Single Sign-on</span></span>

<span data-ttu-id="41697-122">Compartir en Teams, tanto en Outlook en la web como en clientes de escritorio de Outlook, se basa en un explorador WebView.</span><span class="sxs-lookup"><span data-stu-id="41697-122">Share to Teams, in both Outlook on the web and Outlook desktop clients, relies on a browser WebView.</span></span> <span data-ttu-id="41697-123">Vea [Exploradores usados por los complementos de Office](/office/dev/add-ins/concepts/browsers-used-by-office-web-add-ins) para obtener información detallada sobre qué clientes usan los exploradores específicos.</span><span class="sxs-lookup"><span data-stu-id="41697-123">See [Browsers used by Office Add-ins](/office/dev/add-ins/concepts/browsers-used-by-office-web-add-ins) for details on which clients use which specific browsers.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="41697-124">Compartir en Teams requiere que las cookies de terceros y el acceso de almacenamiento local se habiliten para los exploradores de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="41697-124">Share to Teams requires both third-party cookies and local storage access to be enabled for users' browsers.</span></span>

<span data-ttu-id="41697-125">Compartir en Teams usa el inicio de sesión único (SSO), lo que significa que los usuarios no necesitan proporcionar sus credenciales al usar el complemento a través de Compartir en Teams.</span><span class="sxs-lookup"><span data-stu-id="41697-125">Share to Teams uses Single Sign-on (SSO), which means users don’t need to provide their credentials when using the add-in via Share to Teams.</span></span> <span data-ttu-id="41697-126">SSO para Outlook en la web admite https://outlook.office365.com/owa/extSSO.aspx y responde direcciones URL de forma https://outlook.office.com/owa/extSSO.aspx predeterminada.</span><span class="sxs-lookup"><span data-stu-id="41697-126">SSO for Outlook on the web supports https://outlook.office365.com/owa/extSSO.aspx and https://outlook.office.com/owa/extSSO.aspx reply URLs by default.</span></span> <span data-ttu-id="41697-127">Para los dominios de vanidad, los administradores deben agregar la dirección URL de respuesta de Azure Active Directory adecuada.</span><span class="sxs-lookup"><span data-stu-id="41697-127">For vanity domains, administrators need to add the appropriate Azure Active Directory reply URL.</span></span>