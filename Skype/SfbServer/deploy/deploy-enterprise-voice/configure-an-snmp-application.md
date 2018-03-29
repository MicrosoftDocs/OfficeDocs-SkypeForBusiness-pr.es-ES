---
title: Configurar una aplicación SNMP en Skype Empresarial Server 2015
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
ms.assetid: c4b4a736-3b2e-45b9-a965-19d22161ad57
description: Configurar una aplicación SNMP para E9-1-1 en Skype para Telefonía IP empresarial de Business Server.
ms.openlocfilehash: 5c10d00e05979c2a3e0efff015da61e5ff2c6ee9
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="configure-an-snmp-application-in-skype-for-business-server-2015"></a><span data-ttu-id="45c03-103">Configurar una aplicación SNMP en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="45c03-103">Configure an SNMP application in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="45c03-104">Configurar una aplicación SNMP para E9-1-1 en Skype para Telefonía IP empresarial de Business Server.</span><span class="sxs-lookup"><span data-stu-id="45c03-104">Configure an SNMP application to work with E9-1-1 in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="45c03-105">Skype para Business Server incluye una interfaz de servicios web estándar que puede utilizar para conectar el servicio de información de ubicación a las aplicaciones de Simple Network Management Protocol (SNMP) que coincidan con las direcciones MAC con puerto y cambie la información.</span><span class="sxs-lookup"><span data-stu-id="45c03-105">Skype for Business Server includes a standard web service interface that you can use to connect the Location Information service to Simple Network Management Protocol (SNMP) applications that match MAC addresses with port and switch information.</span></span> 
  
<span data-ttu-id="45c03-106">Si se instala una aplicación SNMP y se produce un error en el servicio de información de ubicación encontrar a una coincidencia en la base de datos de ubicación, el servicio de información de ubicación consulta automáticamente la aplicación mediante la dirección MAC proporcionada por el cliente.</span><span class="sxs-lookup"><span data-stu-id="45c03-106">If an SNMP application is installed and the Location Information service fails to find a match in the location database, the Location Information service automatically queries the application by using the MAC address provided by the client.</span></span> <span data-ttu-id="45c03-107">El servicio de información de ubicación, a continuación, utiliza la información de puerto y switch devuelve la aplicación SNMP para volver a consultar la base de datos de ubicación.</span><span class="sxs-lookup"><span data-stu-id="45c03-107">The Location Information service then uses the port and switch information returned by the SNMP application to query the location database again.</span></span>
  
> [!NOTE]
> <span data-ttu-id="45c03-108">Las direcciones MAC no están disponibles en equipos que ejecutan Windows 8.</span><span class="sxs-lookup"><span data-stu-id="45c03-108">MAC addresses are not available on computers running Windows 8.</span></span> 
  
### <a name="to-configure-the-snmp-application-url"></a><span data-ttu-id="45c03-109">Para configurar la dirección URL de la aplicación SNMP:</span><span class="sxs-lookup"><span data-stu-id="45c03-109">To configure the SNMP application URL</span></span>

1.  <span data-ttu-id="45c03-110">Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.</span><span class="sxs-lookup"><span data-stu-id="45c03-110">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="45c03-111">Ejecute el cmdlet siguiente para configurar la dirección URL para la aplicación SNMP.</span><span class="sxs-lookup"><span data-stu-id="45c03-111">Run the following cmdlet to configure the URL for the SNMP application.</span></span> 
    
   ```
   Set-CsWebServiceConfiguration -MACResolverUrl "<SNMP application url>" 
   ```

## <a name="see-also"></a><span data-ttu-id="45c03-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="45c03-112">See also</span></span>

#### 

[<span data-ttu-id="45c03-113">Conjunto de CsWebServiceConfiguration</span><span class="sxs-lookup"><span data-stu-id="45c03-113">Set-CsWebServiceConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-cswebserviceconfiguration?view=skype-ps)

