---
title: Integrar Skype Empresarial Server 2015 con Exchange Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 795dc1c6-524f-4012-8b66-103b55198044
description: 'Resumen: Revisar los pasos de integración de 2016 de Exchange Server o Exchange Server 2013 y Skype para Business Server 2015.'
ms.openlocfilehash: c8cbecd6b78e3dc14ad2133a93d9fc2d1f6bb3d6
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="integrate-skype-for-business-server-2015-with-exchange-server"></a><span data-ttu-id="ec8b1-103">Integrar Skype Empresarial Server 2015 con Exchange Server</span><span class="sxs-lookup"><span data-stu-id="ec8b1-103">Integrate Skype for Business Server 2015 with Exchange Server</span></span>
 
<span data-ttu-id="ec8b1-104">**Resumen:** Revise los pasos de integración de 2016 de Exchange Server o Exchange Server 2013 y Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="ec8b1-104">**Summary:** Review integration steps for Exchange Server 2016 or Exchange Server 2013 and Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="ec8b1-105">2016 de Exchange Server o Exchange Server 2013 y Skype para Business Server 2015 son compatibles e integrarán bien.</span><span class="sxs-lookup"><span data-stu-id="ec8b1-105">Exchange Server 2016 or Exchange Server 2013 and Skype for Business Server 2015 are compatible and integrate well.</span></span> <span data-ttu-id="ec8b1-106">Por ejemplo, puede indicarse Skype para la información de presencia de usuarios de negocio en Microsoft Outlook; del mismo modo, Skype para el negocio puede tener acceso a calendario de Outlook de un usuario, observe que el usuario tiene una reunión programada y mostrar la presencia del usuario como ocupado durante la reunión.</span><span class="sxs-lookup"><span data-stu-id="ec8b1-106">For example, Skype for Business user presence information can be reported in Microsoft Outlook; likewise, Skype for Business can access a user's Outlook calendar, notice the user has a meeting scheduled, and show the user's presence as Busy during the meeting.</span></span> <span data-ttu-id="ec8b1-107">Aunque no tiene que ejecutar Exchange Server para ejecutar Skype para Business Server (o viceversa) de los dos productos mejorar la experiencia del usuario de la otra.</span><span class="sxs-lookup"><span data-stu-id="ec8b1-107">Although you do not have to run Exchange Server in order to run Skype for Business Server (or vice-versa) the two products together enhance each other's user experience.</span></span>
  
<span data-ttu-id="ec8b1-108">Esta documentación proporciona información sobre la integración de Skype para Business Server 2015 y 2016 de Exchange Server o Exchange Server 2013, pero se supone que la instalación inicial y configuración de estos dos productos ya ha ocurrido.</span><span class="sxs-lookup"><span data-stu-id="ec8b1-108">This documentation provides information on integrating Skype for Business Server 2015 and Exchange Server 2016 or Exchange Server 2013, but it assumes the initial setup and configuration of these two products has already happened.</span></span> <span data-ttu-id="ec8b1-109">Para obtener más información sobre la implementación de Skype para Business Server 2015 vea el [Skype para 2015 Business Server TechCenter](https://go.microsoft.com/fwlink/p/?LinkId=246127).</span><span class="sxs-lookup"><span data-stu-id="ec8b1-109">For details about deploying Skype for Business Server 2015 see the [Skype for Business Server 2015 Tech Center](https://go.microsoft.com/fwlink/p/?LinkId=246127).</span></span> <span data-ttu-id="ec8b1-110">Para obtener más información acerca de la implementación de Exchange Server, consulte la documentación de implementación para la versión de Exchange.</span><span class="sxs-lookup"><span data-stu-id="ec8b1-110">For details about deploying Exchange Server see the deployment documentation for your version of Exchange.</span></span>
  
<span data-ttu-id="ec8b1-111">Si va a integrar una instalación local en de Skype para el año 2015 de servidor empresariales con Microsoft Exchange Online, vea [Configurar la integración entre locales Skype para Business Server 2015 y Outlook Web App](outlook-web-app.md).</span><span class="sxs-lookup"><span data-stu-id="ec8b1-111">If you are integrating an on premises installation of Skype for Business Server 2015 with Microsoft Exchange Online, see [Configure integration between on-premises Skype for Business Server 2015 and Outlook Web App](outlook-web-app.md).</span></span>
  
<span data-ttu-id="ec8b1-112">Si está integrando Skype para los negocios en línea con Exchange Server en locales, consulte [Configurar OAuth entre Skype para los negocios en línea y Exchange en instalaciones](oauth-with-online-and-on-premises.md).</span><span class="sxs-lookup"><span data-stu-id="ec8b1-112">If you are integrating Skype for Business Online with Exchange Server on premises, see [Configure OAuth between Skype for Business Online and Exchange on premises](oauth-with-online-and-on-premises.md).</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="ec8b1-113">En esta sección</span><span class="sxs-lookup"><span data-stu-id="ec8b1-113">In this section</span></span>

[<span data-ttu-id="ec8b1-114">Configurar aplicaciones de socios en Skype para 2015 de Business Server y Exchange Server</span><span class="sxs-lookup"><span data-stu-id="ec8b1-114">Configure partner applications in Skype for Business Server 2015 and Exchange Server</span></span>](configure-partner-applications.md)
  
[<span data-ttu-id="ec8b1-115">Configurar Skype para Business Server 2015 utilizar el archivado de Exchange Server</span><span class="sxs-lookup"><span data-stu-id="ec8b1-115">Configure Skype for Business Server 2015 to use Exchange Server archiving</span></span>](use-exchange-archiving.md)
  
[<span data-ttu-id="ec8b1-116">Configurar el servidor de SharePoint para buscar Skype archivado para datos profesionales</span><span class="sxs-lookup"><span data-stu-id="ec8b1-116">Configure SharePoint Server to search for archived Skype for Business data</span></span>](sharepoint-to-search-for-archived-data.md)
  
[<span data-ttu-id="ec8b1-117">Configurar Skype para Business Server 2015 utilizar el almacén de contactos unificado</span><span class="sxs-lookup"><span data-stu-id="ec8b1-117">Configure Skype for Business Server 2015 to use the unified contact store</span></span>](use-the-unified-contact-store.md)
  
[<span data-ttu-id="ec8b1-118">Configurar el uso de fotografías de alta resolución en Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="ec8b1-118">Configure the use of high-resolution photos in Skype for Business Server 2015</span></span>](high-resolution-photos.md)
  
[<span data-ttu-id="ec8b1-119">Configurar la mensajería unificada de Exchange Server para Skype Business Server 2015 para correo de voz</span><span class="sxs-lookup"><span data-stu-id="ec8b1-119">Configure Exchange Server Unified Messaging for Skype for Business Server 2015 voice mail</span></span>](exchangeunified-messaging-for-voice-mail.md)
  
[<span data-ttu-id="ec8b1-120">Integración de Skype para Business Server 2015 y Microsoft Outlook Web App de 2013</span><span class="sxs-lookup"><span data-stu-id="ec8b1-120">Integrating Skype for Business Server 2015 and Microsoft Outlook Web App 2013</span></span>](http://technet.microsoft.com/library/513d4cc7-aa87-4f68-b99d-d58b63bdf242.aspx)
  
[<span data-ttu-id="ec8b1-121">Configurar el almacén de contactos personales en los equipos cliente para Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="ec8b1-121">Configure the personal contacts store on client computers for Skype for Business Server 2015</span></span>](personal-contacts-store.md)
  
## <a name="see-also"></a><span data-ttu-id="ec8b1-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="ec8b1-122">See also</span></span>

#### 

[<span data-ttu-id="ec8b1-123">Planear la integración de Skype para empresas y Exchange</span><span class="sxs-lookup"><span data-stu-id="ec8b1-123">Plan to integrate Skype for Business and Exchange</span></span>](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md)

