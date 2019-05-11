---
title: Configurar la integración con el almacenamiento de Exchange de Skype para Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8f48b87f-a57f-4ed8-8c79-5c75b316b696
description: 'Resumen: Lea este tema para obtener información sobre cómo configurar la integración con el almacenamiento de Exchange en Skype para Business Server.'
ms.openlocfilehash: 4b9d689ef5315c58b2fb6d78c01366ce2377a00e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33893549"
---
# <a name="configure-integration-with-exchange-storage-for-skype-for-business-server"></a><span data-ttu-id="a4581-103">Configurar la integración con el almacenamiento de Exchange de Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="a4581-103">Configure integration with Exchange storage for Skype for Business Server</span></span>
 
<span data-ttu-id="a4581-104">**Resumen:** Lea este tema para obtener información sobre cómo configurar la integración con el almacenamiento de Exchange en Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="a4581-104">**Summary:** Read this topic to learn how to configure integration with Exchange storage in Skype for Business Server.</span></span>
  
<span data-ttu-id="a4581-105">Si utiliza la integración de Microsoft Exchange para todos los usuarios de la implementación, no es necesario configurar Skype para las directivas de archivado para los usuarios de Business Server.</span><span class="sxs-lookup"><span data-stu-id="a4581-105">If you use Microsoft Exchange integration for all users in your deployment, you don't need to configure Skype for Business Server archiving policies for your users.</span></span> <span data-ttu-id="a4581-106">En su lugar, configure las directivas de retención de Exchange local para admitir el archivado para los usuarios alojados en Exchange, con sus buzones poner en suspensión en contexto.</span><span class="sxs-lookup"><span data-stu-id="a4581-106">Instead, you configure Exchange In-Place Hold policies to support archiving for users homed on Exchange, with their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="a4581-107">Antes de configurar la integración con el almacenamiento de Exchange, lea [Plan for archiving en Skype para Business Server](../../plan-your-deployment/archiving/archiving.md).</span><span class="sxs-lookup"><span data-stu-id="a4581-107">Before you configure integration with Exchange storage, read [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md).</span></span> <span data-ttu-id="a4581-108">Para obtener información detallada sobre las directivas de retención de Exchange local, consulte la documentación de producto de Exchange.</span><span class="sxs-lookup"><span data-stu-id="a4581-108">For details about Exchange In-Place Hold policies, see the Exchange product documentation.</span></span> 
  
## <a name="configure-integration-with-microsoft-exchange-storage"></a><span data-ttu-id="a4581-109">Configurar la integración con el almacenamiento de información de Microsoft Exchange</span><span class="sxs-lookup"><span data-stu-id="a4581-109">Configure integration with Microsoft Exchange storage</span></span>

1. <span data-ttu-id="a4581-110">Desde una cuenta de usuario que se asigne al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="a4581-110">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="a4581-111">Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Skype para el Panel de Control de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="a4581-111">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="a4581-112">En la barra de navegación izquierda, haga clic en **Supervisión y archivado** y, después, en **Configuración de archivado**.</span><span class="sxs-lookup"><span data-stu-id="a4581-112">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="a4581-113">Haga clic en el nombre de la configuración global, de sitio o de grupo adecuada en la lista de configuraciones de archivado; haga clic en **Editar**, en **Mostrar detalles** y, luego, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="a4581-113">Click the name of the appropriate global, site, or pool configuration in the list of archiving configurations, click **Edit**, click **Show details**, and then do the following:</span></span>
    
   - <span data-ttu-id="a4581-114">Para habilitar la integración con el almacenamiento de Exchange, active la casilla de verificación de la **integración de Microsoft Exchange** .</span><span class="sxs-lookup"><span data-stu-id="a4581-114">To enable integration with Exchange storage, select the **Microsoft Exchange integration** check box.</span></span>
    
   - <span data-ttu-id="a4581-115">Para deshabilitar la integración con el almacenamiento de Exchange, desactive la casilla de verificación de la **integración de Microsoft Exchange** .</span><span class="sxs-lookup"><span data-stu-id="a4581-115">To disable integration with Exchange storage, clear the **Microsoft Exchange integration** check box.</span></span>
    
5. <span data-ttu-id="a4581-116">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="a4581-116">Click **Commit**.</span></span>
    
## <a name="when-skype-for-business-server-and-microsoft-exchange-are-deployed-in-different-forests"></a><span data-ttu-id="a4581-117">Cuando se implementan Skype para Business Server y Microsoft Exchange en bosques diferentes</span><span class="sxs-lookup"><span data-stu-id="a4581-117">When Skype for Business Server and Microsoft Exchange are deployed in different forests</span></span>

<span data-ttu-id="a4581-118">Si utiliza la integración de Microsoft Exchange y Microsoft Exchange Server no se ha implementado en el mismo bosque que Skype para Business Server, debe asegurarse de que se sincronizan los siguientes atributos de Active Directory de Exchange en el bosque donde Skype para Se implementa Business Server:</span><span class="sxs-lookup"><span data-stu-id="a4581-118">If you use Microsoft Exchange integration and Microsoft Exchange Server is not deployed in the same forest as Skype for Business Server, you must make sure that the following Exchange Active Directory attributes are synchronized to the forest where Skype for Business Server is deployed:</span></span>
  
- <span data-ttu-id="a4581-119">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="a4581-119">msExchUserHoldPolicies</span></span>
    
- <span data-ttu-id="a4581-120">proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="a4581-120">proxyAddresses</span></span>
    
<span data-ttu-id="a4581-p102">Este es un atributo de varios valores. Al sincronizarlo, los valores se necesitan combinar, no reemplazar, para garantizar que no se pierdan los valores existentes.</span><span class="sxs-lookup"><span data-stu-id="a4581-p102">This is a multi-value attribute. When synchronizing this attribute, you need to merge the values, not replace them to ensure the existing values are not lost.</span></span>
  

