---
title: Instalar los componentes del chat persistente en Skype Empresarial Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 61370aa6-9708-4ff8-b531-b258a928806f
description: 'Resumen: Lea este tema para obtener información sobre cómo usar el Asistente de implementación de Skype empresarial Server para instalar los componentes y servicios de Skype empresarial Server 2015.'
ms.openlocfilehash: 019700b169c3507540c93a3a152c3741de2681fb
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41795691"
---
# <a name="install-persistent-chat-components-in-skype-for-business-server-2015"></a><span data-ttu-id="81f62-103">Instalar los componentes del chat persistente en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="81f62-103">Install Persistent Chat components in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="81f62-104">**Resumen:** Lea este tema para obtener información sobre cómo usar el Asistente de implementación de Skype empresarial Server para instalar los componentes y servicios de Skype empresarial Server 2015.</span><span class="sxs-lookup"><span data-stu-id="81f62-104">**Summary:** Read this topic to learn how to use the Skype for Business Server Deployment Wizard to install Skype for Business Server 2015 components and services.</span></span>
  
<span data-ttu-id="81f62-105">Antes de instalar los componentes de chat persistentes, asegúrese de que ya tiene el hardware y el software necesario, y cree la topología adecuada para admitir el servidor de la conversación persistente.</span><span class="sxs-lookup"><span data-stu-id="81f62-105">Before you install Persistent Chat components, be sure you have already installed prerequisite hardware and software, and created the appropriate topology to support Persistent Chat Server.</span></span> <span data-ttu-id="81f62-106">Para obtener más información acerca de la planificación y los requisitos, consulte [los requisitos de su entorno de Skype empresarial](../../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md) y [planifique el servidor de chat persistente en Skype empresarial Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md).</span><span class="sxs-lookup"><span data-stu-id="81f62-106">For details about planning and requirements, see [Requirements for your Skype for Business environment](../../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md) and [Plan for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md).</span></span> <span data-ttu-id="81f62-107">Para obtener información sobre cómo actualizar y publicar su topología para incluir un servidor de chat persistente, consulte [Agregar un servidor de chat persistente a la topología 2015 de Skype empresarial Server](add-persistent-chat-server.md).</span><span class="sxs-lookup"><span data-stu-id="81f62-107">For information about how to update and publish your topology to include Persistent Chat Server, see [Add Persistent Chat Server to your Skype for Business Server 2015 topology](add-persistent-chat-server.md).</span></span>
  
> [!NOTE] 
> <span data-ttu-id="81f62-108">Chat persistente está disponible en Skype empresarial Server 2015, pero ya no es compatible con Skype empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="81f62-108">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="81f62-109">La misma funcionalidad está disponible en Teams.</span><span class="sxs-lookup"><span data-stu-id="81f62-109">The same functionality is available in Teams.</span></span> <span data-ttu-id="81f62-110">Para obtener más información, consulte [Introducción a la actualización de Microsoft Teams](/microsoftteams/upgrade-start-here).</span><span class="sxs-lookup"><span data-stu-id="81f62-110">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="81f62-111">Si necesita usar una conversación persistente, puede elegir entre migrar los usuarios que tienen esta funcionalidad a teams o continuar usando Skype empresarial Server 2015.</span><span class="sxs-lookup"><span data-stu-id="81f62-111">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 

## <a name="install-and-start-services"></a><span data-ttu-id="81f62-112">Instalar e iniciar servicios</span><span class="sxs-lookup"><span data-stu-id="81f62-112">Install and start services</span></span>

<span data-ttu-id="81f62-113">Con el Asistente para la implementación de Skype empresarial Server, elija instalar o actualizar el sistema de Skype empresarial Server para realizar los siguientes pasos:</span><span class="sxs-lookup"><span data-stu-id="81f62-113">Using the Skype for Business Server Deployment Wizard, choose Install or Update Skype for Business Server System to perform the following steps:</span></span> 
  
1. <span data-ttu-id="81f62-114">Instalar almacén de configuración local</span><span class="sxs-lookup"><span data-stu-id="81f62-114">Install Local Configuration Store</span></span>
    
2. <span data-ttu-id="81f62-115">Instalar o quitar componentes de Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="81f62-115">Setup or Remove Skype for Business Server Components</span></span>
    
3. <span data-ttu-id="81f62-116">Solicitar, instalar o asignar certificados</span><span class="sxs-lookup"><span data-stu-id="81f62-116">Request, Install or Assign Certificates</span></span>
    
4. <span data-ttu-id="81f62-117">Iniciar servicios</span><span class="sxs-lookup"><span data-stu-id="81f62-117">Start services</span></span>
    
<span data-ttu-id="81f62-118">Para obtener más información sobre cómo usar el Asistente para la implementación para instalar componentes, asignar certificados e iniciar servicios, consulte [instalar Skype empresarial server 2015](../../deploy/install/install.md) e [instalar skype empresarial Server 2015 en los servidores de la topología](../../deploy/install/install-skype-for-business-server.md).</span><span class="sxs-lookup"><span data-stu-id="81f62-118">For details on how to use the Deployment Wizard to install components, assign certificates, and start services, see [Install Skype for Business Server 2015](../../deploy/install/install.md) and [Install Skype for Business Server 2015 on servers in the topology](../../deploy/install/install-skype-for-business-server.md).</span></span>
  

