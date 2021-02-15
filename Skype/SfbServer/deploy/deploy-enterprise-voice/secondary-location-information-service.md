---
title: Configurar un servicio secundario de información de ubicación en Skype Empresarial Server
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
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 083ffbc6-7c18-4141-85f9-8825b62c3d10
description: Configure una base de datos de origen de ubicación secundaria (SLS) para E9-1-1 en Skype Empresarial Server Telefonía IP empresarial.
ms.openlocfilehash: fd70957526d193951b56211c0d5a6623a26419e2
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830650"
---
# <a name="configure-a-secondary-location-information-service-in-skype-for-business-server"></a><span data-ttu-id="a1fb8-103">Configurar un servicio secundario de información de ubicación en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="a1fb8-103">Configure a secondary Location Information service in Skype for Business Server</span></span>
 
<span data-ttu-id="a1fb8-104">Configure una base de datos de origen de ubicación secundaria (SLS) para E9-1-1 en Skype Empresarial Server Telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="a1fb8-104">Configure a secondary location source (SLS) database for E9-1-1 in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="a1fb8-105">Skype Empresarial Server proporciona una interfaz de servicio web que puede usar para apuntar el servicio de información de ubicación a una base de datos de origen de ubicación secundario (SLS).</span><span class="sxs-lookup"><span data-stu-id="a1fb8-105">Skype for Business Server provides a web service interface that you can use to point the Location Information service to a Secondary Location Source (SLS) database.</span></span> <span data-ttu-id="a1fb8-106">La interfaz de servicio web que se conecta a la base de datos SLS debe cumplir con el WSDL del servicio de información de ubicación.</span><span class="sxs-lookup"><span data-stu-id="a1fb8-106">The web service interface that connects to the SLS database must conform to Location Information service WSDL.</span></span> <span data-ttu-id="a1fb8-107">Si se configuran una base de datos de ubicación y una base de datos de ubicación secundaria, el servicio de información de ubicación consulta primero la base de datos de ubicación y, si no se encuentra ninguna coincidencia, envía la solicitud de ubicación del cliente a la base de datos SLS.</span><span class="sxs-lookup"><span data-stu-id="a1fb8-107">If both a location database and secondary location database are configured, the Location Information service first queries the location database, and if no match is found, sends the location request from the client to the SLS database.</span></span> <span data-ttu-id="a1fb8-108">Si la ubicación existe en el SLS, el servicio de información de ubicación envía la ubicación de vuelta al cliente.</span><span class="sxs-lookup"><span data-stu-id="a1fb8-108">If the location exists in the SLS, the Location Information service then sends the location back to the client.</span></span> 
  
### <a name="to-configure-a-secondary-location-database"></a><span data-ttu-id="a1fb8-109">Para configurar una base de datos de ubicación secundaria</span><span class="sxs-lookup"><span data-stu-id="a1fb8-109">To configure a Secondary Location database</span></span>

1. <span data-ttu-id="a1fb8-110">Inicie el Shell de administración de Skype Empresarial Server: Haga clic en **Inicio,** en Todos los **programas,** **en Skype Empresarial 2015** y, a continuación, en Shell de administración de Skype Empresarial **Server.**</span><span class="sxs-lookup"><span data-stu-id="a1fb8-110">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="a1fb8-111">Ejecute el siguiente cmdlet para configurar la URL para la ubicación de la base de datos de ubicación secundaria.</span><span class="sxs-lookup"><span data-stu-id="a1fb8-111">Run the following cmdlet to configure the URL for the location of the secondary location database.</span></span> 
    
   ```powershell
   Set-CsWebServiceConfiguration -SecondaryLocationSourceURL "<web service url>" 
   ```

## <a name="see-also"></a><span data-ttu-id="a1fb8-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="a1fb8-112">See also</span></span>

[<span data-ttu-id="a1fb8-113">Set-CsWebServiceConfiguration</span><span class="sxs-lookup"><span data-stu-id="a1fb8-113">Set-CsWebServiceConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-cswebserviceconfiguration?view=skype-ps)

