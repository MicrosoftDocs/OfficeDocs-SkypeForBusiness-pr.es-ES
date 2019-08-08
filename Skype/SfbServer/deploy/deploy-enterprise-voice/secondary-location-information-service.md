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
ms.openlocfilehash: 47dd4015cde79536323cee3edc04ed546459a3f0
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2019
ms.locfileid: "36240168"
---
# <a name="configure-a-secondary-location-information-service-in-skype-for-business-server"></a>Configurar un servicio de información de ubicación secundaria en Skype empresarial Server
 
Configurar una base de datos de origen de ubicación secundaria (SLS) para E9-1-1 en Skype empresarial Server Enterprise Voice. 
  
Skype empresarial Server proporciona una interfaz de servicio Web que puede usar para señalar el servicio de información de ubicación a una base de datos de origen de ubicación secundaria (SLS). La interfaz de servicio Web que se conecta a la base de datos de SLS debe cumplir con el servicio de información de ubicación WSDL. Si se configuran una base de datos de ubicación y una de ubicación secundaria, el servicio de información de ubicación primero consulta la base de datos de ubicación y, si no se encuentra ninguna coincidencia, envía la solicitud de ubicación desde el cliente a la base de datos de SLS. Si la ubicación existe en el SLS, el servicio de información de ubicación entonces envía la ubicación de vuelta al cliente. 
  
### <a name="to-configure-a-secondary-location-database"></a>Para configurar la base de datos de ubicación secundaria

1. Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.
    
2. Ejecute el siguiente cmdlet para configurar la URL para la ubicación de la base de datos de ubicación secundaria. 
    
   ```
   Set-CsWebServiceConfiguration -SecondaryLocationSourceURL "<web service url>" 
   ```

## <a name="see-also"></a>Vea también

[Set-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cswebserviceconfiguration?view=skype-ps)

