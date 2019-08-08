---
title: Configurar la integración con almacenamiento de Exchange para Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8f48b87f-a57f-4ed8-8c79-5c75b316b696
description: 'Resumen: Lea este tema para obtener información sobre cómo configurar la integración con el almacenamiento de Exchange en Skype empresarial Server.'
ms.openlocfilehash: 72caf77c81dae538f793afe6f0a94ad6b61d0fa5
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2019
ms.locfileid: "36234334"
---
# <a name="configure-integration-with-exchange-storage-for-skype-for-business-server"></a><span data-ttu-id="51552-103">Configurar la integración con almacenamiento de Exchange para Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="51552-103">Configure integration with Exchange storage for Skype for Business Server</span></span>
 
<span data-ttu-id="51552-104">**Resumen:** Lea este tema para obtener información sobre cómo configurar la integración con el almacenamiento de Exchange en Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="51552-104">**Summary:** Read this topic to learn how to configure integration with Exchange storage in Skype for Business Server.</span></span>
  
<span data-ttu-id="51552-105">Si usa la integración de Microsoft Exchange para todos los usuarios de su implementación, no es necesario que configure las directivas de archivado de Skype empresarial Server para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="51552-105">If you use Microsoft Exchange integration for all users in your deployment, you don't need to configure Skype for Business Server archiving policies for your users.</span></span> <span data-ttu-id="51552-106">En su lugar, puede configurar directivas de retención local de Exchange para admitir el archivado de usuarios alojados en Exchange, con sus buzones en conservación local.</span><span class="sxs-lookup"><span data-stu-id="51552-106">Instead, you configure Exchange In-Place Hold policies to support archiving for users homed on Exchange, with their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="51552-107">Antes de configurar la integración con el almacenamiento de Exchange, lea [Plan for archiving in Skype empresarial Server](../../plan-your-deployment/archiving/archiving.md).</span><span class="sxs-lookup"><span data-stu-id="51552-107">Before you configure integration with Exchange storage, read [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md).</span></span> <span data-ttu-id="51552-108">Para obtener más información sobre las directivas de retención local de Exchange, consulte la documentación del producto de Exchange.</span><span class="sxs-lookup"><span data-stu-id="51552-108">For details about Exchange In-Place Hold policies, see the Exchange product documentation.</span></span> 
  
## <a name="configure-integration-with-microsoft-exchange-storage"></a><span data-ttu-id="51552-109">Configurar la integración con el almacenamiento de Microsoft Exchange</span><span class="sxs-lookup"><span data-stu-id="51552-109">Configure integration with Microsoft Exchange storage</span></span>

1. <span data-ttu-id="51552-110">Desde una cuenta de usuario que se asigne al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="51552-110">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="51552-111">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="51552-111">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="51552-112">En la barra de navegación izquierda, haga clic en **Supervisión y archivado** y, después, en **Configuración de archivado**.</span><span class="sxs-lookup"><span data-stu-id="51552-112">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="51552-113">Haga clic en el nombre de la configuración global, de sitio o de grupo adecuada en la lista de configuraciones de archivado; haga clic en **Editar**, en **Mostrar detalles** y, luego, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="51552-113">Click the name of the appropriate global, site, or pool configuration in the list of archiving configurations, click **Edit**, click **Show details**, and then do the following:</span></span>
    
   - <span data-ttu-id="51552-114">Para habilitar la integración con el almacenamiento de Exchange, active la casilla **integración con Microsoft Exchange** .</span><span class="sxs-lookup"><span data-stu-id="51552-114">To enable integration with Exchange storage, select the **Microsoft Exchange integration** check box.</span></span>
    
   - <span data-ttu-id="51552-115">Para deshabilitar la integración con el almacenamiento de Exchange, desactive la casilla **integración con Microsoft Exchange** .</span><span class="sxs-lookup"><span data-stu-id="51552-115">To disable integration with Exchange storage, clear the **Microsoft Exchange integration** check box.</span></span>
    
5. <span data-ttu-id="51552-116">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="51552-116">Click **Commit**.</span></span>
    
## <a name="when-skype-for-business-server-and-microsoft-exchange-are-deployed-in-different-forests"></a><span data-ttu-id="51552-117">Cuando Skype empresarial Server y Microsoft Exchange se implementan en diferentes bosques</span><span class="sxs-lookup"><span data-stu-id="51552-117">When Skype for Business Server and Microsoft Exchange are deployed in different forests</span></span>

<span data-ttu-id="51552-118">Si usa la integración de Microsoft Exchange y Microsoft Exchange Server no está implementado en el mismo bosque que Skype empresarial Server, debe asegurarse de que los siguientes atributos de Exchange Active Directory se sincronicen con el bosque en el que Skype para Se ha implementado Business Server:</span><span class="sxs-lookup"><span data-stu-id="51552-118">If you use Microsoft Exchange integration and Microsoft Exchange Server is not deployed in the same forest as Skype for Business Server, you must make sure that the following Exchange Active Directory attributes are synchronized to the forest where Skype for Business Server is deployed:</span></span>
  
- <span data-ttu-id="51552-119">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="51552-119">msExchUserHoldPolicies</span></span>
    
- <span data-ttu-id="51552-120">proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="51552-120">proxyAddresses</span></span>
    
<span data-ttu-id="51552-p102">Este es un atributo de varios valores. Al sincronizarlo, los valores se necesitan combinar, no reemplazar, para garantizar que no se pierdan los valores existentes.</span><span class="sxs-lookup"><span data-stu-id="51552-p102">This is a multi-value attribute. When synchronizing this attribute, you need to merge the values, not replace them to ensure the existing values are not lost.</span></span>
  

