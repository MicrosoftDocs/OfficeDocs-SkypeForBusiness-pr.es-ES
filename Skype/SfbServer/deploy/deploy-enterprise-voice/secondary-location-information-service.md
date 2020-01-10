---
title: Configurar un servicio de información de ubicación secundaria en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 083ffbc6-7c18-4141-85f9-8825b62c3d10
description: Configurar una base de datos de origen de ubicación secundaria (SLS) para E9-1-1 en Skype empresarial Server Enterprise Voice.
ms.openlocfilehash: 1743a4c5f49fcc01fe2f0878c596e0d1bb530621
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/09/2020
ms.locfileid: "41002001"
---
# <a name="configure-a-secondary-location-information-service-in-skype-for-business-server"></a><span data-ttu-id="991f4-103">Configurar un servicio de información de ubicación secundaria en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="991f4-103">Configure a secondary Location Information service in Skype for Business Server</span></span>
 
<span data-ttu-id="991f4-104">Configurar una base de datos de origen de ubicación secundaria (SLS) para E9-1-1 en Skype empresarial Server Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="991f4-104">Configure a secondary location source (SLS) database for E9-1-1 in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="991f4-105">Skype empresarial Server proporciona una interfaz de servicio Web que puede usar para señalar el servicio de información de ubicación a una base de datos de origen de ubicación secundaria (SLS).</span><span class="sxs-lookup"><span data-stu-id="991f4-105">Skype for Business Server provides a web service interface that you can use to point the Location Information service to a Secondary Location Source (SLS) database.</span></span> <span data-ttu-id="991f4-106">La interfaz de servicio Web que se conecta a la base de datos de SLS debe cumplir con el servicio de información de ubicación WSDL.</span><span class="sxs-lookup"><span data-stu-id="991f4-106">The web service interface that connects to the SLS database must conform to Location Information service WSDL.</span></span> <span data-ttu-id="991f4-107">Si se configuran una base de datos de ubicación y una de ubicación secundaria, el servicio de información de ubicación primero consulta la base de datos de ubicación y, si no se encuentra ninguna coincidencia, envía la solicitud de ubicación desde el cliente a la base de datos de SLS.</span><span class="sxs-lookup"><span data-stu-id="991f4-107">If both a location database and secondary location database are configured, the Location Information service first queries the location database, and if no match is found, sends the location request from the client to the SLS database.</span></span> <span data-ttu-id="991f4-108">Si la ubicación existe en el SLS, el servicio de información de ubicación entonces envía la ubicación de vuelta al cliente.</span><span class="sxs-lookup"><span data-stu-id="991f4-108">If the location exists in the SLS, the Location Information service then sends the location back to the client.</span></span> 
  
### <a name="to-configure-a-secondary-location-database"></a><span data-ttu-id="991f4-109">Para configurar la base de datos de ubicación secundaria</span><span class="sxs-lookup"><span data-stu-id="991f4-109">To configure a Secondary Location database</span></span>

1. <span data-ttu-id="991f4-110">Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.</span><span class="sxs-lookup"><span data-stu-id="991f4-110">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="991f4-111">Ejecute el siguiente cmdlet para configurar la URL para la ubicación de la base de datos de ubicación secundaria.</span><span class="sxs-lookup"><span data-stu-id="991f4-111">Run the following cmdlet to configure the URL for the location of the secondary location database.</span></span> 
    
   ```powershell
   Set-CsWebServiceConfiguration -SecondaryLocationSourceURL "<web service url>" 
   ```

## <a name="see-also"></a><span data-ttu-id="991f4-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="991f4-112">See also</span></span>

[<span data-ttu-id="991f4-113">Set-CsWebServiceConfiguration</span><span class="sxs-lookup"><span data-stu-id="991f4-113">Set-CsWebServiceConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-cswebserviceconfiguration?view=skype-ps)

