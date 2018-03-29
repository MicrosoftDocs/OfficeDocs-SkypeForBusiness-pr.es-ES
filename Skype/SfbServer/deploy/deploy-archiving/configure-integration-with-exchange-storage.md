---
title: Configurar la integración con el almacenamiento de Exchange para Skype Empresarial Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8f48b87f-a57f-4ed8-8c79-5c75b316b696
description: 'Resumen: Leer este tema para obtener información sobre cómo configurar la integración con almacenamiento de información de Exchange en Skype para Business Server 2015.'
ms.openlocfilehash: 2d814bb297999062aaf93160286031afec51c3a9
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="configure-integration-with-exchange-storage-for-skype-for-business-server-2015"></a><span data-ttu-id="03ac6-103">Configurar la integración con el almacenamiento de Exchange para Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="03ac6-103">Configure integration with Exchange storage for Skype for Business Server 2015</span></span>
 
<span data-ttu-id="03ac6-104">**Resumen:** Lea este tema para aprender a configurar la integración con almacenamiento de información de Exchange en Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="03ac6-104">**Summary:** Read this topic to learn how to configure integration with Exchange storage in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="03ac6-105">Si utiliza la integración de Microsoft Exchange para todos los usuarios en la implementación, no es necesario configurar Skype para políticas de archiving Business Server para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="03ac6-105">If you use Microsoft Exchange integration for all users in your deployment, you don't need to configure Skype for Business Server archiving policies for your users.</span></span> <span data-ttu-id="03ac6-106">En su lugar, configurar directivas de Exchange en el mismo lugar mantenga para soportar archiving para usuarios alojados en Exchange, con sus buzones poner en posesión en el lugar.</span><span class="sxs-lookup"><span data-stu-id="03ac6-106">Instead, you configure Exchange In-Place Hold policies to support archiving for users homed on Exchange, with their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="03ac6-107">Antes de configurar la integración con el almacenamiento de información de Exchange, lea el [Plan para archiving en Skype para Business Server 2015](../../plan-your-deployment/archiving/archiving.md).</span><span class="sxs-lookup"><span data-stu-id="03ac6-107">Before you configure integration with Exchange storage, read [Plan for archiving in Skype for Business Server 2015](../../plan-your-deployment/archiving/archiving.md).</span></span> <span data-ttu-id="03ac6-108">Para obtener más información acerca de las directivas en colocar espera de Exchange, consulte la documentación del producto Exchange.</span><span class="sxs-lookup"><span data-stu-id="03ac6-108">For details about Exchange In-Place Hold policies, see the Exchange product documentation.</span></span> 
  
## <a name="configure-integration-with-microsoft-exchange-storage"></a><span data-ttu-id="03ac6-109">Configurar la integración con el almacenamiento de información de Microsoft Exchange</span><span class="sxs-lookup"><span data-stu-id="03ac6-109">Configure integration with Microsoft Exchange storage</span></span>

1. <span data-ttu-id="03ac6-110">Desde una cuenta de usuario que se asigne al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="03ac6-110">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="03ac6-111">Abra una ventana del explorador y, a continuación, escriba la dirección URL de Admin para abrir el Skype para Panel de Control de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="03ac6-111">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="03ac6-112">En la barra de navegación izquierda, haga clic en **Supervisión y archivado** y, después, en **Configuración de archivado**.</span><span class="sxs-lookup"><span data-stu-id="03ac6-112">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="03ac6-113">Haga clic en el nombre de la configuración global, de sitio o de grupo adecuada en la lista de configuraciones de archivado; haga clic en **Editar**, en **Mostrar detalles** y, luego, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="03ac6-113">Click the name of the appropriate global, site, or pool configuration in the list of archiving configurations, click **Edit**, click **Show details**, and then do the following:</span></span>
    
  - <span data-ttu-id="03ac6-114">Para habilitar la integración con el almacenamiento de información de Exchange, active la casilla de verificación de **integración de Microsoft Exchange** .</span><span class="sxs-lookup"><span data-stu-id="03ac6-114">To enable integration with Exchange storage, select the **Microsoft Exchange integration** check box.</span></span>
    
  - <span data-ttu-id="03ac6-115">Para deshabilitar la integración con el almacenamiento de información de Exchange, desactive la casilla de verificación de la **integración de Microsoft Exchange** .</span><span class="sxs-lookup"><span data-stu-id="03ac6-115">To disable integration with Exchange storage, clear the **Microsoft Exchange integration** check box.</span></span>
    
5. <span data-ttu-id="03ac6-116">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="03ac6-116">Click **Commit**.</span></span>
    
## <a name="when-skype-for-business-server-and-microsoft-exchange-are-deployed-in-different-forests"></a><span data-ttu-id="03ac6-117">Cuando se implementan Skype para Business Server y Microsoft Exchange en bosques diferentes</span><span class="sxs-lookup"><span data-stu-id="03ac6-117">When Skype for Business Server and Microsoft Exchange are deployed in different forests</span></span>

<span data-ttu-id="03ac6-118">Si utiliza la integración de Microsoft Exchange y Microsoft Exchange Server no se implementa en el mismo bosque que Skype para Business Server, debe asegurarse de que los siguientes atributos de Active Directory de Exchange están sincronizados con el bosque donde Skype para Business Server está implementado:</span><span class="sxs-lookup"><span data-stu-id="03ac6-118">If you use Microsoft Exchange integration and Microsoft Exchange Server is not deployed in the same forest as Skype for Business Server, you must make sure that the following Exchange Active Directory attributes are synchronized to the forest where Skype for Business Server is deployed:</span></span>
  
- <span data-ttu-id="03ac6-119">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="03ac6-119">msExchUserHoldPolicies</span></span>
    
- <span data-ttu-id="03ac6-120">proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="03ac6-120">proxyAddresses</span></span>
    
<span data-ttu-id="03ac6-p102">Este es un atributo de varios valores. Al sincronizarlo, los valores se necesitan combinar, no reemplazar, para garantizar que no se pierdan los valores existentes.</span><span class="sxs-lookup"><span data-stu-id="03ac6-p102">This is a multi-value attribute. When synchronizing this attribute, you need to merge the values, not replace them to ensure the existing values are not lost.</span></span>
  

