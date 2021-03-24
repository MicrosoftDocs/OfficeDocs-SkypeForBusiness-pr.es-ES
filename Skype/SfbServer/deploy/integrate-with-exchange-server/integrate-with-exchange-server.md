---
title: Integrar Skype Empresarial Server con Exchange Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 795dc1c6-524f-4012-8b66-103b55198044
description: 'Resumen: revise los pasos de integración para Exchange Server 2016 o Exchange Server 2013 y Skype Empresarial Server.'
ms.openlocfilehash: b19aa73e62b12674551690b716144fb67b4cd715
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51104856"
---
# <a name="integrate-skype-for-business-server-with-exchange-server"></a><span data-ttu-id="3cf60-103">Integrar Skype Empresarial Server con Exchange Server</span><span class="sxs-lookup"><span data-stu-id="3cf60-103">Integrate Skype for Business Server with Exchange Server</span></span>

<span data-ttu-id="3cf60-104">**Resumen:** Revise los pasos de integración Exchange Server 2013 o posterior y Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="3cf60-104">**Summary:** Review integration steps for Exchange Server 2013 or later and Skype for Business Server.</span></span>

<span data-ttu-id="3cf60-105">Exchange Server 2013 o posterior y Skype Empresarial Server son compatibles e integran bien.</span><span class="sxs-lookup"><span data-stu-id="3cf60-105">Exchange Server 2013 or later and Skype for Business Server are compatible and integrate well.</span></span> <span data-ttu-id="3cf60-106">Por ejemplo, la información de presencia de usuarios de Skype Empresarial puede ser notificada en Microsoft Outlook; Asimismo, Skype Empresarial puede tener acceso al calendario de Outlook de un usuario, observar que el usuario tiene programada una reunión y mostrar la presencia del usuario como Ocupado durante la reunión.</span><span class="sxs-lookup"><span data-stu-id="3cf60-106">For example, Skype for Business user presence information can be reported in Microsoft Outlook; likewise, Skype for Business can access a user's Outlook calendar, notice the user has a meeting scheduled, and show the user's presence as Busy during the meeting.</span></span> <span data-ttu-id="3cf60-107">Aunque no es necesario ejecutar Exchange Server para ejecutar Skype Empresarial Server (o viceversa) los dos productos mejoran entre sí la experiencia del usuario.</span><span class="sxs-lookup"><span data-stu-id="3cf60-107">Although you do not have to run Exchange Server in order to run Skype for Business Server (or vice-versa) the two products together enhance each other's user experience.</span></span>

<span data-ttu-id="3cf60-108">Esta documentación proporciona información sobre la integración de Skype Empresarial Server y Exchange Server 2016 o Exchange Server 2013, pero supone que ya se ha producido la configuración y configuración iniciales de estos dos productos.</span><span class="sxs-lookup"><span data-stu-id="3cf60-108">This documentation provides information on integrating Skype for Business Server and Exchange Server 2016 or Exchange Server 2013, but it assumes the initial setup and configuration of these two products has already happened.</span></span> <span data-ttu-id="3cf60-109">Para obtener más información acerca de la implementación de Skype Empresarial Server, vea el Centro técnico de [Skype Empresarial Server](../../../Hub/index.yml).</span><span class="sxs-lookup"><span data-stu-id="3cf60-109">For details about deploying Skype for Business Server see the [Skype for Business Server Tech Center](../../../Hub/index.yml).</span></span> <span data-ttu-id="3cf60-110">Para obtener más información acerca de la Exchange Server vea la documentación de implementación de la versión de Exchange.</span><span class="sxs-lookup"><span data-stu-id="3cf60-110">For details about deploying Exchange Server see the deployment documentation for your version of Exchange.</span></span>

<span data-ttu-id="3cf60-111">Si va a integrar una instalación local de Skype Empresarial Server con Microsoft Exchange Online, vea [Configure integration between on-premises Skype for Business Server and Outlook Web App](outlook-web-app.md).</span><span class="sxs-lookup"><span data-stu-id="3cf60-111">If you are integrating an on premises installation of Skype for Business Server with Microsoft Exchange Online, see [Configure integration between on-premises Skype for Business Server and Outlook Web App](outlook-web-app.md).</span></span>

<span data-ttu-id="3cf60-112">Si va a integrar Skype Empresarial Online con Exchange Server local, vea [Configure OAuth between Skype for Business Online and Exchange on premises](oauth-with-online-and-on-premises.md).</span><span class="sxs-lookup"><span data-stu-id="3cf60-112">If you are integrating Skype for Business Online with Exchange Server on premises, see [Configure OAuth between Skype for Business Online and Exchange on premises](oauth-with-online-and-on-premises.md).</span></span>

## <a name="in-this-section"></a><span data-ttu-id="3cf60-113">En esta sección</span><span class="sxs-lookup"><span data-stu-id="3cf60-113">In this section</span></span>

[<span data-ttu-id="3cf60-114">Configurar aplicaciones de partners en Skype Empresarial Server y Exchange Server</span><span class="sxs-lookup"><span data-stu-id="3cf60-114">Configure partner applications in Skype for Business Server and Exchange Server</span></span>](configure-partner-applications.md)

[<span data-ttu-id="3cf60-115">Configurar Skype Empresarial Server para usar Exchange Server archivado</span><span class="sxs-lookup"><span data-stu-id="3cf60-115">Configure Skype for Business Server to use Exchange Server archiving</span></span>](use-exchange-archiving.md)

[<span data-ttu-id="3cf60-116">Configurar SharePoint Server para buscar datos archivados de Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="3cf60-116">Configure SharePoint Server to search for archived Skype for Business data</span></span>](sharepoint-to-search-for-archived-data.md)

[<span data-ttu-id="3cf60-117">Configurar Skype Empresarial Server para usar el almacén de contactos unificado</span><span class="sxs-lookup"><span data-stu-id="3cf60-117">Configure Skype for Business Server to use the unified contact store</span></span>](use-the-unified-contact-store.md)

[<span data-ttu-id="3cf60-118">Configurar el uso de fotos de alta resolución en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="3cf60-118">Configure the use of high-resolution photos in Skype for Business Server</span></span>](high-resolution-photos.md)

[<span data-ttu-id="3cf60-119">Configurar Exchange Server mensajería unificada para el correo de voz de Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="3cf60-119">Configure Exchange Server Unified Messaging for Skype for Business Server voice mail</span></span>](exchangeunified-messaging-for-voice-mail.md)

<span data-ttu-id="3cf60-120">[Integración de Skype Empresarial Server y Microsoft Outlook Web App 2013](/previous-versions/office/communications/jj688055(v=ocs.16))</span><span class="sxs-lookup"><span data-stu-id="3cf60-120">[Integrating Skype for Business Server and Microsoft Outlook Web App 2013](/previous-versions/office/communications/jj688055(v=ocs.16))</span></span>

[<span data-ttu-id="3cf60-121">Configurar el almacén de contactos personales en equipos cliente para Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="3cf60-121">Configure the personal contacts store on client computers for Skype for Business Server</span></span>](personal-contacts-store.md)

## <a name="see-also"></a><span data-ttu-id="3cf60-122">Ver también</span><span class="sxs-lookup"><span data-stu-id="3cf60-122">See also</span></span>

[<span data-ttu-id="3cf60-123">Plan para la integración de Skype Empresarial y Exchange</span><span class="sxs-lookup"><span data-stu-id="3cf60-123">Plan to integrate Skype for Business and Exchange</span></span>](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md)