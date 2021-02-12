---
title: Configurar la integración con el almacenamiento de Exchange para Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8f48b87f-a57f-4ed8-8c79-5c75b316b696
description: 'Resumen: lea este tema para obtener información sobre cómo configurar la integración con el almacenamiento de Exchange en Skype Empresarial Server.'
ms.openlocfilehash: 05a0c65aaca54e469f30dd5e732565f6ec0bbb4b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825070"
---
# <a name="configure-integration-with-exchange-storage-for-skype-for-business-server"></a><span data-ttu-id="0ba1a-103">Configurar la integración con el almacenamiento de Exchange para Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="0ba1a-103">Configure integration with Exchange storage for Skype for Business Server</span></span>
 
<span data-ttu-id="0ba1a-104">**Resumen:** Lea este tema para obtener información sobre cómo configurar la integración con el almacenamiento de Exchange en Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="0ba1a-104">**Summary:** Read this topic to learn how to configure integration with Exchange storage in Skype for Business Server.</span></span>
  
<span data-ttu-id="0ba1a-105">Si usa la integración de Microsoft Exchange para todos los usuarios de su implementación, no es necesario configurar las directivas de archivado de Skype Empresarial Server para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="0ba1a-105">If you use Microsoft Exchange integration for all users in your deployment, you don't need to configure Skype for Business Server archiving policies for your users.</span></span> <span data-ttu-id="0ba1a-106">En su lugar, configure las directivas de retención de exchange In-Place para admitir el archivado para los usuarios que están en Exchange, con sus buzones de correo en In-Place retención.</span><span class="sxs-lookup"><span data-stu-id="0ba1a-106">Instead, you configure Exchange In-Place Hold policies to support archiving for users homed on Exchange, with their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="0ba1a-107">Antes de configurar la integración con el almacenamiento de Exchange, lea [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md).</span><span class="sxs-lookup"><span data-stu-id="0ba1a-107">Before you configure integration with Exchange storage, read [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md).</span></span> <span data-ttu-id="0ba1a-108">Para obtener más información sobre las directivas In-Place de retención de exchange, consulte la documentación del producto de Exchange.</span><span class="sxs-lookup"><span data-stu-id="0ba1a-108">For details about Exchange In-Place Hold policies, see the Exchange product documentation.</span></span> 
  
## <a name="configure-integration-with-microsoft-exchange-storage"></a><span data-ttu-id="0ba1a-109">Configurar la integración con el almacenamiento de Microsoft Exchange</span><span class="sxs-lookup"><span data-stu-id="0ba1a-109">Configure integration with Microsoft Exchange storage</span></span>

1. <span data-ttu-id="0ba1a-110">Desde una cuenta de usuario asignada al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="0ba1a-110">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="0ba1a-111">Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de control de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="0ba1a-111">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="0ba1a-112">En la barra de navegación izquierda, haga clic en **Supervisión y archivado** y, a continuación, haga clic en **Configuración de archivado**.</span><span class="sxs-lookup"><span data-stu-id="0ba1a-112">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="0ba1a-113">Haga clic en el nombre de la configuración global, de sitio o de grupo adecuada de la lista de configuraciones de archivado, en **Editar** y en **Mostrar detalles**. A continuación, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="0ba1a-113">Click the name of the appropriate global, site, or pool configuration in the list of archiving configurations, click **Edit**, click **Show details**, and then do the following:</span></span>
    
   - <span data-ttu-id="0ba1a-114">Para habilitar la integración con el almacenamiento de Exchange, active la casilla **de verificación de integración** de Microsoft Exchange.</span><span class="sxs-lookup"><span data-stu-id="0ba1a-114">To enable integration with Exchange storage, select the **Microsoft Exchange integration** check box.</span></span>
    
   - <span data-ttu-id="0ba1a-115">Para deshabilitar la integración con el almacenamiento de Exchange, desactive la casilla **de verificación de integración** de Microsoft Exchange.</span><span class="sxs-lookup"><span data-stu-id="0ba1a-115">To disable integration with Exchange storage, clear the **Microsoft Exchange integration** check box.</span></span>
    
5. <span data-ttu-id="0ba1a-116">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="0ba1a-116">Click **Commit**.</span></span>
    
## <a name="when-skype-for-business-server-and-microsoft-exchange-are-deployed-in-different-forests"></a><span data-ttu-id="0ba1a-117">Cuando Skype Empresarial Server y Microsoft Exchange se implementan en bosques diferentes</span><span class="sxs-lookup"><span data-stu-id="0ba1a-117">When Skype for Business Server and Microsoft Exchange are deployed in different forests</span></span>

<span data-ttu-id="0ba1a-118">Si usa la integración de Microsoft Exchange y Microsoft Exchange Server no se implementa en el mismo bosque que Skype Empresarial Server, debe asegurarse de que los siguientes atributos de Exchange Active Directory se sincronizan con el bosque donde se implementa Skype Empresarial Server:</span><span class="sxs-lookup"><span data-stu-id="0ba1a-118">If you use Microsoft Exchange integration and Microsoft Exchange Server is not deployed in the same forest as Skype for Business Server, you must make sure that the following Exchange Active Directory attributes are synchronized to the forest where Skype for Business Server is deployed:</span></span>
  
- <span data-ttu-id="0ba1a-119">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="0ba1a-119">msExchUserHoldPolicies</span></span>
    
- <span data-ttu-id="0ba1a-120">proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="0ba1a-120">proxyAddresses</span></span>
    
<span data-ttu-id="0ba1a-121">Este es un atributo de varios valores.</span><span class="sxs-lookup"><span data-stu-id="0ba1a-121">This is a multi-value attribute.</span></span> <span data-ttu-id="0ba1a-122">Al sincronizar este atributo, debe combinar los valores, no reemplazarlos para asegurarse de que no se pierdan los valores existentes.</span><span class="sxs-lookup"><span data-stu-id="0ba1a-122">When synchronizing this attribute, you need to merge the values, not replace them to ensure the existing values are not lost.</span></span>
  

