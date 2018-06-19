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
description: 'Resumen: Revise los pasos de integración de 2016 de Exchange Server o Exchange Server 2013 y Skype para Business Server 2015.'
ms.openlocfilehash: a592638b3a62ffa2e2e39bfcc14b66cba4e09afd
ms.sourcegitcommit: b14cfca231b618ec28cf9f4efe11cb3e8aceb34b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2018
ms.locfileid: "19500654"
---
# <a name="integrate-skype-for-business-server-2015-with-exchange-server"></a><span data-ttu-id="7dbde-103">Integrar Skype Empresarial Server 2015 con Exchange Server</span><span class="sxs-lookup"><span data-stu-id="7dbde-103">Integrate Skype for Business Server 2015 with Exchange Server</span></span>
 
<span data-ttu-id="7dbde-104">**Resumen:** Revise los pasos de integración de 2016 de Exchange Server o Exchange Server 2013 y Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="7dbde-104">**Summary:** Review integration steps for Exchange Server 2016 or Exchange Server 2013 and Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="7dbde-105">Exchange Server 2016 o Exchange Server 2013 y Skype para Business Server 2015 son compatibles e integrarán bien.</span><span class="sxs-lookup"><span data-stu-id="7dbde-105">Exchange Server 2016 or Exchange Server 2013 and Skype for Business Server 2015 are compatible and integrate well.</span></span> <span data-ttu-id="7dbde-106">Por ejemplo, se puede notificar Skype para obtener información de presencia de usuario empresarial en Microsoft Outlook; del mismo modo, Skype para la empresa puede tener acceso a calendario de Outlook de un usuario, tenga en cuenta que el usuario tiene una reunión programada y mostrar la presencia del usuario como no disponible durante la reunión.</span><span class="sxs-lookup"><span data-stu-id="7dbde-106">For example, Skype for Business user presence information can be reported in Microsoft Outlook; likewise, Skype for Business can access a user's Outlook calendar, notice the user has a meeting scheduled, and show the user's presence as Busy during the meeting.</span></span> <span data-ttu-id="7dbde-107">Aunque no es necesario que ejecutar el servidor de Exchange para la ejecución de Skype para Business Server (o viceversa) de los dos productos juntos con el fin de mejorar la experiencia del usuario del otro.</span><span class="sxs-lookup"><span data-stu-id="7dbde-107">Although you do not have to run Exchange Server in order to run Skype for Business Server (or vice-versa) the two products together enhance each other's user experience.</span></span>
  
<span data-ttu-id="7dbde-108">Esta documentación proporciona información sobre la integración de Skype para Business Server 2015 y 2016 de Exchange Server o Exchange Server 2013, pero se supone que la instalación inicial y la configuración de estos dos productos que ya se ha realizado.</span><span class="sxs-lookup"><span data-stu-id="7dbde-108">This documentation provides information on integrating Skype for Business Server 2015 and Exchange Server 2016 or Exchange Server 2013, but it assumes the initial setup and configuration of these two products has already happened.</span></span> <span data-ttu-id="7dbde-109">Para obtener información detallada sobre la implementación de Skype para Business Server 2015, vea el [Skype para Business Server 2015 Tech Center](https://go.microsoft.com/fwlink/p/?LinkId=246127).</span><span class="sxs-lookup"><span data-stu-id="7dbde-109">For details about deploying Skype for Business Server 2015 see the [Skype for Business Server 2015 Tech Center](https://go.microsoft.com/fwlink/p/?LinkId=246127).</span></span> <span data-ttu-id="7dbde-110">Para obtener información detallada sobre la implementación de Exchange Server, consulte la documentación de implementación para su versión de Exchange.</span><span class="sxs-lookup"><span data-stu-id="7dbde-110">For details about deploying Exchange Server see the deployment documentation for your version of Exchange.</span></span>
  
<span data-ttu-id="7dbde-111">Si va a integrar una instalación local en de Skype para Business Server 2015 con Microsoft Exchange Online, vea [Configurar la integración entre local Skype para Business Server 2015 y Outlook Web App](outlook-web-app.md).</span><span class="sxs-lookup"><span data-stu-id="7dbde-111">If you are integrating an on premises installation of Skype for Business Server 2015 with Microsoft Exchange Online, see [Configure integration between on-premises Skype for Business Server 2015 and Outlook Web App](outlook-web-app.md).</span></span>
  
<span data-ttu-id="7dbde-112">Si va a integrar Skype para profesionales en línea con el servidor de Exchange local, vea [Configurar OAuth entre Skype para profesionales en línea y de Exchange local](oauth-with-online-and-on-premises.md).</span><span class="sxs-lookup"><span data-stu-id="7dbde-112">If you are integrating Skype for Business Online with Exchange Server on premises, see [Configure OAuth between Skype for Business Online and Exchange on premises](oauth-with-online-and-on-premises.md).</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="7dbde-113">En esta sección</span><span class="sxs-lookup"><span data-stu-id="7dbde-113">In this section</span></span>

[<span data-ttu-id="7dbde-114">Configuración de las aplicaciones asociadas en Skype para Business Server 2015 y Exchange Server</span><span class="sxs-lookup"><span data-stu-id="7dbde-114">Configure partner applications in Skype for Business Server 2015 and Exchange Server</span></span>](configure-partner-applications.md)
  
[<span data-ttu-id="7dbde-115">Configuración de Skype para Business Server 2015 utilizar el archivado de Exchange Server</span><span class="sxs-lookup"><span data-stu-id="7dbde-115">Configure Skype for Business Server 2015 to use Exchange Server archiving</span></span>](use-exchange-archiving.md)
  
[<span data-ttu-id="7dbde-116">Configuración de SharePoint Server para buscar archivado Skype para datos profesionales</span><span class="sxs-lookup"><span data-stu-id="7dbde-116">Configure SharePoint Server to search for archived Skype for Business data</span></span>](sharepoint-to-search-for-archived-data.md)
  
[<span data-ttu-id="7dbde-117">Configuración de Skype para Business Server 2015 usar el almacén de contactos unificados</span><span class="sxs-lookup"><span data-stu-id="7dbde-117">Configure Skype for Business Server 2015 to use the unified contact store</span></span>](use-the-unified-contact-store.md)
  
[<span data-ttu-id="7dbde-118">Configurar el uso de fotografías de alta resolución en Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="7dbde-118">Configure the use of high-resolution photos in Skype for Business Server 2015</span></span>](high-resolution-photos.md)
  
[<span data-ttu-id="7dbde-119">Configurar la mensajería unificada de Exchange Server para Skype para correo de voz empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="7dbde-119">Configure Exchange Server Unified Messaging for Skype for Business Server 2015 voice mail</span></span>](exchangeunified-messaging-for-voice-mail.md)
  
[<span data-ttu-id="7dbde-120">Integración de Skype para Business Server 2015 y Microsoft Outlook Web App 2013</span><span class="sxs-lookup"><span data-stu-id="7dbde-120">Integrating Skype for Business Server 2015 and Microsoft Outlook Web App 2013</span></span>](http://technet.microsoft.com/library/513d4cc7-aa87-4f68-b99d-d58b63bdf242.aspx)
  
[<span data-ttu-id="7dbde-121">Configurar el almacén de contactos personales en los equipos cliente de Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="7dbde-121">Configure the personal contacts store on client computers for Skype for Business Server 2015</span></span>](personal-contacts-store.md)
  
## <a name="see-also"></a><span data-ttu-id="7dbde-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="7dbde-122">See also</span></span>

[<span data-ttu-id="7dbde-123">Planear la integración de Skype para empresas y Exchange</span><span class="sxs-lookup"><span data-stu-id="7dbde-123">Plan to integrate Skype for Business and Exchange</span></span>](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md)