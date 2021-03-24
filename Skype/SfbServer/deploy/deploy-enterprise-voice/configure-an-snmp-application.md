---
title: Configurar una aplicación SNMP en Skype Empresarial Server
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
ms.assetid: c4b4a736-3b2e-45b9-a965-19d22161ad57
description: Configure una aplicación SNMP para que funcione con E9-1-1 en Skype Empresarial Server Telefonía IP empresarial.
ms.openlocfilehash: f8b4c7503524dacdc20e85fc68f0a79286e38c2e
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103636"
---
# <a name="configure-an-snmp-application-in-skype-for-business-server"></a><span data-ttu-id="1fb36-103">Configurar una aplicación SNMP en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="1fb36-103">Configure an SNMP application in Skype for Business Server</span></span>
 
<span data-ttu-id="1fb36-104">Configure una aplicación SNMP para que funcione con E9-1-1 en Skype Empresarial Server Telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="1fb36-104">Configure an SNMP application to work with E9-1-1 in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="1fb36-105">Skype Empresarial Server incluye una interfaz de servicio web estándar que puede usar para conectar el servicio de información de ubicación a aplicaciones del Protocolo simple de administración de red (SNMP) que coinciden con las direcciones MAC con la información de puerto y conmutador.</span><span class="sxs-lookup"><span data-stu-id="1fb36-105">Skype for Business Server includes a standard web service interface that you can use to connect the Location Information service to Simple Network Management Protocol (SNMP) applications that match MAC addresses with port and switch information.</span></span> 
  
<span data-ttu-id="1fb36-106">Si se instala una aplicación SNMP y el servicio de información de ubicación no encuentra una coincidencia en la base de datos de ubicación, el servicio de información de ubicación consulta automáticamente la aplicación mediante la dirección MAC proporcionada por el cliente.</span><span class="sxs-lookup"><span data-stu-id="1fb36-106">If an SNMP application is installed and the Location Information service fails to find a match in the location database, the Location Information service automatically queries the application by using the MAC address provided by the client.</span></span> <span data-ttu-id="1fb36-107">A continuación, el servicio de información de ubicación usa el puerto y la información de cambio devuelta por la aplicación SNMP para consultar de nuevo la base de datos de ubicación.</span><span class="sxs-lookup"><span data-stu-id="1fb36-107">The Location Information service then uses the port and switch information returned by the SNMP application to query the location database again.</span></span>
  
> [!NOTE]
> <span data-ttu-id="1fb36-108">Las direcciones MAC no están disponibles en equipos que ejecutan Windows 8.</span><span class="sxs-lookup"><span data-stu-id="1fb36-108">MAC addresses are not available on computers running Windows 8.</span></span> 
  
### <a name="to-configure-the-snmp-application-url"></a><span data-ttu-id="1fb36-109">Para configurar la dirección URL de la aplicación SNMP:</span><span class="sxs-lookup"><span data-stu-id="1fb36-109">To configure the SNMP application URL</span></span>

1.  <span data-ttu-id="1fb36-110">Inicie el Shell de administración de Skype Empresarial Server: haga clic en Inicio **,** en Todos los programas **,** **en Skype Empresarial 2015** y, a continuación, en Shell de administración **de Skype Empresarial Server**.</span><span class="sxs-lookup"><span data-stu-id="1fb36-110">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="1fb36-111">Ejecute el cmdlet siguiente para configurar la dirección URL para la aplicación SNMP.</span><span class="sxs-lookup"><span data-stu-id="1fb36-111">Run the following cmdlet to configure the URL for the SNMP application.</span></span> 
    
   ```powershell
   Set-CsWebServiceConfiguration -MACResolverUrl "<SNMP application url>" 
   ```

## <a name="see-also"></a><span data-ttu-id="1fb36-112">Ver también</span><span class="sxs-lookup"><span data-stu-id="1fb36-112">See also</span></span>

[<span data-ttu-id="1fb36-113">Set-CsWebServiceConfiguration</span><span class="sxs-lookup"><span data-stu-id="1fb36-113">Set-CsWebServiceConfiguration</span></span>](/powershell/module/skype/set-cswebserviceconfiguration?view=skype-ps)