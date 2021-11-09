---
title: Configurar un servicio de información de ubicación secundario en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 083ffbc6-7c18-4141-85f9-8825b62c3d10
description: Configure una base de datos de origen de ubicación secundaria (SLS) para E9-1-1 en Skype Empresarial Server Telefonía IP empresarial.
ms.openlocfilehash: 7c41debb07ab8d1aece05b24f515f159f5be0dae
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/08/2021
ms.locfileid: "60860807"
---
# <a name="configure-a-secondary-location-information-service-in-skype-for-business-server"></a>Configurar un servicio de información de ubicación secundario en Skype Empresarial Server
 
Configure una base de datos de origen de ubicación secundaria (SLS) para E9-1-1 en Skype Empresarial Server Telefonía IP empresarial. 
  
Skype Empresarial Server proporciona una interfaz de servicio web que puede usar para apuntar el servicio de información de ubicación a una base de datos de origen de ubicación secundario (SLS). La interfaz de servicio web que se conecta a la base de datos SLS debe cumplir con WSDL del servicio de información de ubicación. Si se configuran una base de datos de ubicación y una base de datos de ubicación secundaria, el servicio de información de ubicación primero consulta la base de datos de ubicación y, si no se encuentra ninguna coincidencia, envía la solicitud de ubicación del cliente a la base de datos sls. Si la ubicación existe en el SLS, el servicio de información de ubicación envía la ubicación de vuelta al cliente. 
  
### <a name="to-configure-a-secondary-location-database"></a>Para configurar una base de datos de ubicación secundaria

1. Inicie el Shell Skype Empresarial Server administración: haga clic en Inicio **,** todos los programas **,** haga clic en **Skype Empresarial 2015** y, a continuación, haga clic **Skype Empresarial Server Shell de administración**.
    
2. Ejecute el siguiente cmdlet para configurar la URL para la ubicación de la base de datos de ubicación secundaria. 
    
   ```powershell
   Set-CsWebServiceConfiguration -SecondaryLocationSourceURL "<web service url>" 
   ```

## <a name="see-also"></a>Consulte también

[Set-CsWebServiceConfiguration](/powershell/module/skype/set-cswebserviceconfiguration?view=skype-ps)