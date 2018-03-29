---
title: Configurar un servicio de información de ubicación secundario en Skype Empresarial Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 083ffbc6-7c18-4141-85f9-8825b62c3d10
description: Configurar una base de datos de origen (SLS) ubicación secundaria para E9-1-1 en Skype para Telefonía IP empresarial de Business Server.
ms.openlocfilehash: 03de4369b8473142e7a76e3698bb9fe7f129d546
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="configure-a-secondary-location-information-service-in-skype-for-business-server-2015"></a><span data-ttu-id="7c194-103">Configurar un servicio de información de ubicación secundario en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="7c194-103">Configure a secondary Location Information service in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="7c194-104">Configurar una base de datos de origen (SLS) ubicación secundaria para E9-1-1 en Skype para Telefonía IP empresarial de Business Server.</span><span class="sxs-lookup"><span data-stu-id="7c194-104">Configure a secondary location source (SLS) database for E9-1-1 in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="7c194-105">Skype para Business Server proporciona una interfaz de servicio web que puede utilizar para señalar el servicio de información de ubicación a una base de datos de origen de ubicación secundaria (SLS).</span><span class="sxs-lookup"><span data-stu-id="7c194-105">Skype for Business Server provides a web service interface that you can use to point the Location Information service to a Secondary Location Source (SLS) database.</span></span> <span data-ttu-id="7c194-106">La interfaz del servicio web que se conecta a la base de datos SLS debe ajustarse al servicio de información de ubicación de WSDL.</span><span class="sxs-lookup"><span data-stu-id="7c194-106">The web service interface that connects to the SLS database must conform to Location Information service WSDL.</span></span> <span data-ttu-id="7c194-107">Si se configuran tanto una base de datos de ubicación y ubicación secundaria, el servicio de información de ubicación consulta la base de datos de ubicación y si se encuentra ninguna coincidencia, envía la solicitud de ubicación desde el cliente a la base de datos SLS.</span><span class="sxs-lookup"><span data-stu-id="7c194-107">If both a location database and secondary location database are configured, the Location Information service first queries the location database, and if no match is found, sends the location request from the client to the SLS database.</span></span> <span data-ttu-id="7c194-108">Si existe la ubicación en el SLS, el servicio de información de ubicación envía la ubicación al cliente.</span><span class="sxs-lookup"><span data-stu-id="7c194-108">If the location exists in the SLS, the Location Information service then sends the location back to the client.</span></span> 
  
### <a name="to-configure-a-secondary-location-database"></a><span data-ttu-id="7c194-109">Para configurar la base de datos de ubicación secundaria</span><span class="sxs-lookup"><span data-stu-id="7c194-109">To configure a Secondary Location database</span></span>

1. <span data-ttu-id="7c194-110">Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.</span><span class="sxs-lookup"><span data-stu-id="7c194-110">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="7c194-111">Ejecute el siguiente cmdlet para configurar la URL para la ubicación de la base de datos de ubicación secundaria.</span><span class="sxs-lookup"><span data-stu-id="7c194-111">Run the following cmdlet to configure the URL for the location of the secondary location database.</span></span> 
    
   ```
   Set-CsWebServiceConfiguration -SecondaryLocationSourceURL "<web service url>" 
   ```

## <a name="see-also"></a><span data-ttu-id="7c194-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="7c194-112">See also</span></span>

#### 

[<span data-ttu-id="7c194-113">Conjunto de CsWebServiceConfiguration</span><span class="sxs-lookup"><span data-stu-id="7c194-113">Set-CsWebServiceConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-cswebserviceconfiguration?view=skype-ps)

