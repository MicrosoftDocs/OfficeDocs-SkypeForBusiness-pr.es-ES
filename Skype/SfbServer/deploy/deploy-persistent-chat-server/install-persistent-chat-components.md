---
title: Instalar los componentes del chat persistente en Skype Empresarial Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 61370aa6-9708-4ff8-b531-b258a928806f
description: 'Resumen: Lea este tema para obtener información sobre cómo usar el Skype para el Asistente para la implementación de Business Server para instalar Skype para los servicios y componentes de Business Server 2015.'
ms.openlocfilehash: 16b967c2f90ae5811be6bd6436b2025217a1efab
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33894545"
---
# <a name="install-persistent-chat-components-in-skype-for-business-server-2015"></a><span data-ttu-id="0e112-103">Instalar los componentes del chat persistente en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="0e112-103">Install Persistent Chat components in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="0e112-104">**Resumen:** Lea este tema para obtener información sobre cómo usar el Skype para el Asistente para la implementación de Business Server para instalar Skype para los servicios y componentes de Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="0e112-104">**Summary:** Read this topic to learn how to use the Skype for Business Server Deployment Wizard to install Skype for Business Server 2015 components and services.</span></span>
  
<span data-ttu-id="0e112-105">Antes de instalar los componentes de Chat persistente, asegúrese de que ya ha instalado el software y hardware como requisito previo y ha creado la topología adecuada para admitir el servidor de Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="0e112-105">Before you install Persistent Chat components, be sure you have already installed prerequisite hardware and software, and created the appropriate topology to support Persistent Chat Server.</span></span> <span data-ttu-id="0e112-106">Para obtener información detallada sobre la planeación y los requisitos, vea [los requisitos para su Skype para el entorno empresarial](../../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md) y [Plan for Persistent Chat Server in Skype para Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md).</span><span class="sxs-lookup"><span data-stu-id="0e112-106">For details about planning and requirements, see [Requirements for your Skype for Business environment](../../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md) and [Plan for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md).</span></span> <span data-ttu-id="0e112-107">Para obtener información acerca de cómo actualizar y publicar la topología para incluir el servidor de Chat persistente, vea [Agregar servidor de Chat persistente a su Skype para topología empresarial Server 2015](add-persistent-chat-server.md).</span><span class="sxs-lookup"><span data-stu-id="0e112-107">For information about how to update and publish your topology to include Persistent Chat Server, see [Add Persistent Chat Server to your Skype for Business Server 2015 topology](add-persistent-chat-server.md).</span></span>
  
> [!NOTE] 
> <span data-ttu-id="0e112-108">Chat persistente está disponible en Skype para Business Server 2015, pero ya no se admite en Skype para Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="0e112-108">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="0e112-109">La misma funcionalidad está disponible en los equipos.</span><span class="sxs-lookup"><span data-stu-id="0e112-109">The same functionality is available in Teams.</span></span> <span data-ttu-id="0e112-110">Para obtener más información, vea [viaje de Skype para la empresa a los equipos de Microsoft](/microsoftteams/journey-skypeforbusiness-teams).</span><span class="sxs-lookup"><span data-stu-id="0e112-110">For more information, see [Journey from Skype for Business to Microsoft Teams](/microsoftteams/journey-skypeforbusiness-teams).</span></span> <span data-ttu-id="0e112-111">Si necesita usar chat en grupo, las opciones son para migrar los usuarios que requieren esta funcionalidad a los equipos, o para continuar usando Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="0e112-111">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 

## <a name="install-and-start-services"></a><span data-ttu-id="0e112-112">Instalar e iniciar servicios</span><span class="sxs-lookup"><span data-stu-id="0e112-112">Install and start services</span></span>

<span data-ttu-id="0e112-113">Usa el Skype para el Asistente para la implementación de servidor de negocio, elija instalar o Skype de actualización para el sistema de servidor empresarial para llevar a cabo los siguientes pasos:</span><span class="sxs-lookup"><span data-stu-id="0e112-113">Using the Skype for Business Server Deployment Wizard, choose Install or Update Skype for Business Server System to perform the following steps:</span></span> 
  
1. <span data-ttu-id="0e112-114">Instalar almacén de configuración local</span><span class="sxs-lookup"><span data-stu-id="0e112-114">Install Local Configuration Store</span></span>
    
2. <span data-ttu-id="0e112-115">Instalar o quitar componentes de Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="0e112-115">Setup or Remove Skype for Business Server Components</span></span>
    
3. <span data-ttu-id="0e112-116">Solicitar, instalar o asignar certificados</span><span class="sxs-lookup"><span data-stu-id="0e112-116">Request, Install or Assign Certificates</span></span>
    
4. <span data-ttu-id="0e112-117">Iniciar servicios</span><span class="sxs-lookup"><span data-stu-id="0e112-117">Start services</span></span>
    
<span data-ttu-id="0e112-118">Para obtener información detallada sobre cómo usar al Asistente para la implementación para instalar los componentes, asignar certificados e iniciar servicios, vea [Instalar Skype para Business Server 2015](../../deploy/install/install.md) e [Instalar Skype para Business Server 2015 en servidores de la topología](../../deploy/install/install-skype-for-business-server.md).</span><span class="sxs-lookup"><span data-stu-id="0e112-118">For details on how to use the Deployment Wizard to install components, assign certificates, and start services, see [Install Skype for Business Server 2015](../../deploy/install/install.md) and [Install Skype for Business Server 2015 on servers in the topology](../../deploy/install/install-skype-for-business-server.md).</span></span>
  

