---
title: Configurar un servicio de información de ubicación secundario en Skype Empresarial Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 083ffbc6-7c18-4141-85f9-8825b62c3d10
description: Configurar una base de datos de origen (SLS) ubicación secundaria para E9-1-1 en Skype para Business Server Enterprise Voice.
ms.openlocfilehash: 4eaab1b6dfaae9b1298cce3544d89f8b6724733e
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="configure-a-secondary-location-information-service-in-skype-for-business-server-2015"></a>Configurar un servicio de información de ubicación secundario en Skype Empresarial Server 2015
 
Configurar una base de datos de origen (SLS) ubicación secundaria para E9-1-1 en Skype para Business Server Enterprise Voice. 
  
Skype para Business Server proporciona una interfaz de servicio web que se puede usar para apuntar el servicio de información de ubicación a una base de datos de origen de ubicación secundaria (SLS). La interfaz de servicio web que se conecta a la base de datos SLS debe cumplir con el servicio de información de ubicación de WSDL. Si se configuran una base de datos de ubicación y la base de datos de ubicación secundaria, el servicio de información de ubicación de las consultas de la base de datos de ubicación y si se encuentra ninguna coincidencia, envía la solicitud de ubicación desde el cliente a la base de datos SLS. Si la ubicación existe en el SLS, el servicio de información de ubicación envía a continuación, la ubicación de vuelta al cliente. 
  
### <a name="to-configure-a-secondary-location-database"></a>Para configurar la base de datos de ubicación secundaria

1. Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.
    
2. Ejecute el siguiente cmdlet para configurar la URL para la ubicación de la base de datos de ubicación secundaria. 
    
   ```
   Set-CsWebServiceConfiguration -SecondaryLocationSourceURL "<web service url>" 
   ```

## <a name="see-also"></a>Vea también

#### 

[Set-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cswebserviceconfiguration?view=skype-ps)

