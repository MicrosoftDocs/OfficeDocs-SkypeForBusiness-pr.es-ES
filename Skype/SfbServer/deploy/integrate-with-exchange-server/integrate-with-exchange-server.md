---
title: Integrar Skype empresarial Server con Exchange Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 795dc1c6-524f-4012-8b66-103b55198044
description: 'Resumen: Revise los pasos de integración de Exchange Server 2016 o de Exchange Server 2013 y Skype empresarial Server.'
ms.openlocfilehash: 25b2260805cf4e42bc15d1ae5607baa3f830fba6
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34277989"
---
# <a name="integrate-skype-for-business-server-with-exchange-server"></a><span data-ttu-id="85246-103">Integrar Skype empresarial Server con Exchange Server</span><span class="sxs-lookup"><span data-stu-id="85246-103">Integrate Skype for Business Server with Exchange Server</span></span>

<span data-ttu-id="85246-104">**Resumen:** Revise los pasos de integración de Exchange Server 2013 o posterior y Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="85246-104">**Summary:** Review integration steps for Exchange Server 2013 or later and Skype for Business Server.</span></span>

<span data-ttu-id="85246-105">Exchange Server 2013 o posterior y Skype empresarial Server son compatibles y se integran correctamente.</span><span class="sxs-lookup"><span data-stu-id="85246-105">Exchange Server 2013 or later and Skype for Business Server are compatible and integrate well.</span></span> <span data-ttu-id="85246-106">Por ejemplo, se puede informar de la información de presencia de los usuarios de Skype empresarial en Microsoft Outlook. de forma similar, Skype empresarial puede acceder al calendario de Outlook de un usuario, observar que el usuario tiene una reunión programada y mostrar la presencia del usuario como ocupado durante la reunión.</span><span class="sxs-lookup"><span data-stu-id="85246-106">For example, Skype for Business user presence information can be reported in Microsoft Outlook; likewise, Skype for Business can access a user's Outlook calendar, notice the user has a meeting scheduled, and show the user's presence as Busy during the meeting.</span></span> <span data-ttu-id="85246-107">Aunque no es necesario ejecutar Exchange Server para poder ejecutar Skype empresarial Server (o viceversa), los dos productos mejoran la experiencia del usuario de cada uno.</span><span class="sxs-lookup"><span data-stu-id="85246-107">Although you do not have to run Exchange Server in order to run Skype for Business Server (or vice-versa) the two products together enhance each other's user experience.</span></span>

<span data-ttu-id="85246-108">Esta documentación proporciona información sobre la integración de Skype empresarial Server y Exchange Server 2016 o Exchange Server 2013, pero supone que ya se ha producido la configuración y la configuración iniciales de estos dos productos.</span><span class="sxs-lookup"><span data-stu-id="85246-108">This documentation provides information on integrating Skype for Business Server and Exchange Server 2016 or Exchange Server 2013, but it assumes the initial setup and configuration of these two products has already happened.</span></span> <span data-ttu-id="85246-109">Para obtener detalles sobre la implementación de Skype empresarial Server, consulte el [Centro Tecnológico de Skype empresarial Server](https://go.microsoft.com/fwlink/p/?LinkId=246127).</span><span class="sxs-lookup"><span data-stu-id="85246-109">For details about deploying Skype for Business Server see the [Skype for Business Server Tech Center](https://go.microsoft.com/fwlink/p/?LinkId=246127).</span></span> <span data-ttu-id="85246-110">Para obtener más información sobre la implementación de Exchange Server, consulte la documentación de implementación de su versión de Exchange.</span><span class="sxs-lookup"><span data-stu-id="85246-110">For details about deploying Exchange Server see the deployment documentation for your version of Exchange.</span></span>

<span data-ttu-id="85246-111">Si está integrando una instalación local de Skype empresarial Server con Microsoft Exchange Online, consulte Configurar la [integración entre Skype empresarial Server local y Outlook Web App](outlook-web-app.md).</span><span class="sxs-lookup"><span data-stu-id="85246-111">If you are integrating an on premises installation of Skype for Business Server with Microsoft Exchange Online, see [Configure integration between on-premises Skype for Business Server and Outlook Web App](outlook-web-app.md).</span></span>

<span data-ttu-id="85246-112">Si está integrando Skype empresarial online con Exchange Server local, consulte [configurar OAuth entre Skype empresarial online y Exchange local](oauth-with-online-and-on-premises.md).</span><span class="sxs-lookup"><span data-stu-id="85246-112">If you are integrating Skype for Business Online with Exchange Server on premises, see [Configure OAuth between Skype for Business Online and Exchange on premises](oauth-with-online-and-on-premises.md).</span></span>

## <a name="in-this-section"></a><span data-ttu-id="85246-113">En esta sección</span><span class="sxs-lookup"><span data-stu-id="85246-113">In this section</span></span>

[<span data-ttu-id="85246-114">Configurar aplicaciones de socio en Skype empresarial Server y Exchange Server</span><span class="sxs-lookup"><span data-stu-id="85246-114">Configure partner applications in Skype for Business Server and Exchange Server</span></span>](configure-partner-applications.md)

[<span data-ttu-id="85246-115">Configurar Skype empresarial Server para usar el archivado de Exchange Server</span><span class="sxs-lookup"><span data-stu-id="85246-115">Configure Skype for Business Server to use Exchange Server archiving</span></span>](use-exchange-archiving.md)

[<span data-ttu-id="85246-116">Configurar SharePoint Server para buscar datos archivados de Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="85246-116">Configure SharePoint Server to search for archived Skype for Business data</span></span>](sharepoint-to-search-for-archived-data.md)

[<span data-ttu-id="85246-117">Configurar Skype Empresarial Server para usar el almacenamiento de contactos unificado</span><span class="sxs-lookup"><span data-stu-id="85246-117">Configure Skype for Business Server to use the unified contact store</span></span>](use-the-unified-contact-store.md)

[<span data-ttu-id="85246-118">Configurar el uso de fotos de alta resolución en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="85246-118">Configure the use of high-resolution photos in Skype for Business Server</span></span>](high-resolution-photos.md)

[<span data-ttu-id="85246-119">Configurar la mensajería unificada de Exchange Server para el correo de voz de Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="85246-119">Configure Exchange Server Unified Messaging for Skype for Business Server voice mail</span></span>](exchangeunified-messaging-for-voice-mail.md)

[<span data-ttu-id="85246-120">Integración de Skype empresarial Server y Microsoft Outlook Web App 2013</span><span class="sxs-lookup"><span data-stu-id="85246-120">Integrating Skype for Business Server and Microsoft Outlook Web App 2013</span></span>](https://technet.microsoft.com/library/513d4cc7-aa87-4f68-b99d-d58b63bdf242.aspx)

[<span data-ttu-id="85246-121">Configurar el almacén de contactos personales en equipos cliente para Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="85246-121">Configure the personal contacts store on client computers for Skype for Business Server</span></span>](personal-contacts-store.md)

## <a name="see-also"></a><span data-ttu-id="85246-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="85246-122">See also</span></span>

[<span data-ttu-id="85246-123">Plan para la integración de Skype Empresarial y Exchange</span><span class="sxs-lookup"><span data-stu-id="85246-123">Plan to integrate Skype for Business and Exchange</span></span>](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md)
