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
# <a name="configure-a-secondary-location-information-service-in-skype-for-business-server"></a>Configurar un servicio secundario de información de ubicación en Skype Empresarial Server
 
Configure una base de datos de origen de ubicación secundaria (SLS) para E9-1-1 en Skype Empresarial Server Telefonía IP empresarial. 
  
Skype Empresarial Server proporciona una interfaz de servicio web que puede usar para apuntar el servicio de información de ubicación a una base de datos de origen de ubicación secundario (SLS). La interfaz de servicio web que se conecta a la base de datos SLS debe cumplir con el WSDL del servicio de información de ubicación. Si se configuran una base de datos de ubicación y una base de datos de ubicación secundaria, el servicio de información de ubicación consulta primero la base de datos de ubicación y, si no se encuentra ninguna coincidencia, envía la solicitud de ubicación del cliente a la base de datos SLS. Si la ubicación existe en el SLS, el servicio de información de ubicación envía la ubicación de vuelta al cliente. 
  
### <a name="to-configure-a-secondary-location-database"></a>Para configurar una base de datos de ubicación secundaria

1. Inicie el Shell de administración de Skype Empresarial Server: Haga clic en **Inicio,** en Todos los **programas,** **en Skype Empresarial 2015** y, a continuación, en Shell de administración de Skype Empresarial **Server.**
    
2. Ejecute el siguiente cmdlet para configurar la URL para la ubicación de la base de datos de ubicación secundaria. 
    
   ```powershell
   Set-CsWebServiceConfiguration -SecondaryLocationSourceURL "<web service url>" 
   ```

## <a name="see-also"></a>Vea también

[Set-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cswebserviceconfiguration?view=skype-ps)

