---
title: Configuración de un servicio de información de ubicación secundario en Skype para Business Server
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 083ffbc6-7c18-4141-85f9-8825b62c3d10
description: Configurar una base de datos de origen (SLS) ubicación secundaria para E9-1-1 en Skype para Business Server Enterprise Voice.
ms.openlocfilehash: e811062bbec9e3b6caf368e010b751e496c1b305
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "23885125"
---
# <a name="configure-a-secondary-location-information-service-in-skype-for-business-server"></a><span data-ttu-id="d06d7-103">Configuración de un servicio de información de ubicación secundario en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="d06d7-103">Configure a secondary Location Information service in Skype for Business Server</span></span>
 
<span data-ttu-id="d06d7-104">Configurar una base de datos de origen (SLS) ubicación secundaria para E9-1-1 en Skype para Business Server Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="d06d7-104">Configure a secondary location source (SLS) database for E9-1-1 in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="d06d7-105">Skype para Business Server proporciona una interfaz de servicio web que se puede usar para apuntar el servicio de información de ubicación a una base de datos de origen de ubicación secundaria (SLS).</span><span class="sxs-lookup"><span data-stu-id="d06d7-105">Skype for Business Server provides a web service interface that you can use to point the Location Information service to a Secondary Location Source (SLS) database.</span></span> <span data-ttu-id="d06d7-106">La interfaz de servicio web que se conecta a la base de datos SLS debe cumplir con el servicio de información de ubicación de WSDL.</span><span class="sxs-lookup"><span data-stu-id="d06d7-106">The web service interface that connects to the SLS database must conform to Location Information service WSDL.</span></span> <span data-ttu-id="d06d7-107">Si se configuran una base de datos de ubicación y la base de datos de ubicación secundaria, el servicio de información de ubicación de las consultas de la base de datos de ubicación y si se encuentra ninguna coincidencia, envía la solicitud de ubicación desde el cliente a la base de datos SLS.</span><span class="sxs-lookup"><span data-stu-id="d06d7-107">If both a location database and secondary location database are configured, the Location Information service first queries the location database, and if no match is found, sends the location request from the client to the SLS database.</span></span> <span data-ttu-id="d06d7-108">Si la ubicación existe en el SLS, el servicio de información de ubicación envía a continuación, la ubicación de vuelta al cliente.</span><span class="sxs-lookup"><span data-stu-id="d06d7-108">If the location exists in the SLS, the Location Information service then sends the location back to the client.</span></span> 
  
### <a name="to-configure-a-secondary-location-database"></a><span data-ttu-id="d06d7-109">Para configurar la base de datos de ubicación secundaria</span><span class="sxs-lookup"><span data-stu-id="d06d7-109">To configure a Secondary Location database</span></span>

1. <span data-ttu-id="d06d7-110">Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.</span><span class="sxs-lookup"><span data-stu-id="d06d7-110">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="d06d7-111">Ejecute el siguiente cmdlet para configurar la URL para la ubicación de la base de datos de ubicación secundaria.</span><span class="sxs-lookup"><span data-stu-id="d06d7-111">Run the following cmdlet to configure the URL for the location of the secondary location database.</span></span> 
    
   ```
   Set-CsWebServiceConfiguration -SecondaryLocationSourceURL "<web service url>" 
   ```

## <a name="see-also"></a><span data-ttu-id="d06d7-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="d06d7-112">See also</span></span>

[<span data-ttu-id="d06d7-113">Set-CsWebServiceConfiguration</span><span class="sxs-lookup"><span data-stu-id="d06d7-113">Set-CsWebServiceConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-cswebserviceconfiguration?view=skype-ps)

