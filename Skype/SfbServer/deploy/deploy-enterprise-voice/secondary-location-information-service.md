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
# <a name="configure-a-secondary-location-information-service-in-skype-for-business-server-2015"></a>Configurar un servicio de información de ubicación secundario en Skype Empresarial Server 2015
 
Configurar una base de datos de origen (SLS) ubicación secundaria para E9-1-1 en Skype para Telefonía IP empresarial de Business Server. 
  
Skype para Business Server proporciona una interfaz de servicio web que puede utilizar para señalar el servicio de información de ubicación a una base de datos de origen de ubicación secundaria (SLS). La interfaz del servicio web que se conecta a la base de datos SLS debe ajustarse al servicio de información de ubicación de WSDL. Si se configuran tanto una base de datos de ubicación y ubicación secundaria, el servicio de información de ubicación consulta la base de datos de ubicación y si se encuentra ninguna coincidencia, envía la solicitud de ubicación desde el cliente a la base de datos SLS. Si existe la ubicación en el SLS, el servicio de información de ubicación envía la ubicación al cliente. 
  
### <a name="to-configure-a-secondary-location-database"></a>Para configurar la base de datos de ubicación secundaria

1. Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.
    
2. Ejecute el siguiente cmdlet para configurar la URL para la ubicación de la base de datos de ubicación secundaria. 
    
   ```
   Set-CsWebServiceConfiguration -SecondaryLocationSourceURL "<web service url>" 
   ```

## <a name="see-also"></a>Vea también

#### 

[Conjunto de CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cswebserviceconfiguration?view=skype-ps)

