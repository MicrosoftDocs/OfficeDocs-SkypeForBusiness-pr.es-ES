---
title: Instalar los componentes del chat persistente en Skype Empresarial Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 61370aa6-9708-4ff8-b531-b258a928806f
description: 'Resumen: Lea este tema para obtener información sobre cómo usar el Asistente de implementación de Skype empresarial Server para instalar los componentes y servicios de Skype empresarial Server 2015.'
ms.openlocfilehash: 6c30ba33f1ff22b5088080048210c7dcb862cb3b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34273807"
---
# <a name="install-persistent-chat-components-in-skype-for-business-server-2015"></a><span data-ttu-id="12deb-103">Instalar los componentes del chat persistente en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="12deb-103">Install Persistent Chat components in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="12deb-104">**Resumen:** Lea este tema para obtener información sobre cómo usar el Asistente de implementación de Skype empresarial Server para instalar los componentes y servicios de Skype empresarial Server 2015.</span><span class="sxs-lookup"><span data-stu-id="12deb-104">**Summary:** Read this topic to learn how to use the Skype for Business Server Deployment Wizard to install Skype for Business Server 2015 components and services.</span></span>
  
<span data-ttu-id="12deb-105">Antes de instalar los componentes de chat persistentes, asegúrese de que ya tiene el hardware y el software necesario, y cree la topología adecuada para admitir el servidor de la conversación persistente.</span><span class="sxs-lookup"><span data-stu-id="12deb-105">Before you install Persistent Chat components, be sure you have already installed prerequisite hardware and software, and created the appropriate topology to support Persistent Chat Server.</span></span> <span data-ttu-id="12deb-106">Para obtener más información acerca de la planificación y los requisitos, consulte [los requisitos de su entorno de Skype empresarial](../../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md) y [planifique el servidor de chat persistente en Skype empresarial Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md).</span><span class="sxs-lookup"><span data-stu-id="12deb-106">For details about planning and requirements, see [Requirements for your Skype for Business environment](../../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md) and [Plan for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md).</span></span> <span data-ttu-id="12deb-107">Para obtener información sobre cómo actualizar y publicar su topología para incluir un servidor de chat persistente, consulte [Agregar un servidor de chat persistente a la topología 2015 de Skype empresarial Server](add-persistent-chat-server.md).</span><span class="sxs-lookup"><span data-stu-id="12deb-107">For information about how to update and publish your topology to include Persistent Chat Server, see [Add Persistent Chat Server to your Skype for Business Server 2015 topology](add-persistent-chat-server.md).</span></span>
  
> [!NOTE] 
> <span data-ttu-id="12deb-108">Chat persistente está disponible en Skype empresarial Server 2015, pero ya no es compatible con Skype empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="12deb-108">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="12deb-109">La misma funcionalidad está disponible en Teams.</span><span class="sxs-lookup"><span data-stu-id="12deb-109">The same functionality is available in Teams.</span></span> <span data-ttu-id="12deb-110">Para obtener más información, consulte Cómo desplazarse [de Skype empresarial a Microsoft Teams](/microsoftteams/journey-skypeforbusiness-teams).</span><span class="sxs-lookup"><span data-stu-id="12deb-110">For more information, see [Journey from Skype for Business to Microsoft Teams](/microsoftteams/journey-skypeforbusiness-teams).</span></span> <span data-ttu-id="12deb-111">Si necesita usar una conversación persistente, puede elegir entre migrar los usuarios que tienen esta funcionalidad a teams o continuar usando Skype empresarial Server 2015.</span><span class="sxs-lookup"><span data-stu-id="12deb-111">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 

## <a name="install-and-start-services"></a><span data-ttu-id="12deb-112">Instalar e iniciar servicios</span><span class="sxs-lookup"><span data-stu-id="12deb-112">Install and start services</span></span>

<span data-ttu-id="12deb-113">Con el Asistente para la implementación de Skype empresarial Server, elija instalar o actualizar el sistema de Skype empresarial Server para realizar los siguientes pasos:</span><span class="sxs-lookup"><span data-stu-id="12deb-113">Using the Skype for Business Server Deployment Wizard, choose Install or Update Skype for Business Server System to perform the following steps:</span></span> 
  
1. <span data-ttu-id="12deb-114">Instalar almacén de configuración local</span><span class="sxs-lookup"><span data-stu-id="12deb-114">Install Local Configuration Store</span></span>
    
2. <span data-ttu-id="12deb-115">Instalar o quitar componentes de Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="12deb-115">Setup or Remove Skype for Business Server Components</span></span>
    
3. <span data-ttu-id="12deb-116">Solicitar, instalar o asignar certificados</span><span class="sxs-lookup"><span data-stu-id="12deb-116">Request, Install or Assign Certificates</span></span>
    
4. <span data-ttu-id="12deb-117">Iniciar servicios</span><span class="sxs-lookup"><span data-stu-id="12deb-117">Start services</span></span>
    
<span data-ttu-id="12deb-118">Para obtener más información sobre cómo usar el Asistente para la implementación para instalar componentes, asignar certificados e iniciar servicios, consulte [instalar Skype empresarial server 2015](../../deploy/install/install.md) e [instalar skype empresarial Server 2015 en los servidores de la topología](../../deploy/install/install-skype-for-business-server.md).</span><span class="sxs-lookup"><span data-stu-id="12deb-118">For details on how to use the Deployment Wizard to install components, assign certificates, and start services, see [Install Skype for Business Server 2015](../../deploy/install/install.md) and [Install Skype for Business Server 2015 on servers in the topology](../../deploy/install/install-skype-for-business-server.md).</span></span>
  

