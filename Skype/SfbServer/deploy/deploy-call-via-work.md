---
title: Implementar Vía trabajo en Skype Empresarial Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 10/31/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: Strat_SB_Admin
ms.assetid: 4802d733-14ef-4509-92b9-07173614e45f
description: 'Resumen: Conozca cómo implementar llamar a través de trabajo en Skype para Business Server 2015 para algunos o todos los usuarios.'
ms.openlocfilehash: 325134bd4e24621bbb223ccc47180274256eaca2
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-call-via-work-in-skype-for-business-server-2015"></a>Implementar Vía trabajo en Skype Empresarial Server 2015
 
**Resumen:** Aprenda a implementar llamar a través de trabajo en Skype para Business Server 2015 para algunos o todos los usuarios.
  
Siga estos pasos para implementar llamar a través de trabajo para los usuarios. Consideraciones de planeación se tratan en el [Plan para llamar a través de trabajo en Skype para Business Server 2015](../plan-your-deployment/enterprise-voice-solution/call-via-work.md). En versiones anteriores de la llamada remota de Lync Server control era una característica que permite a los usuarios controlar sus teléfonos PBX con Lync Server. En Skype para Business Server, esta característica se ha reemplazado con llamar a través de trabajo. 
  
## <a name="prerequisites-for-call-via-work"></a>Requisitos previos para la llamada a través del trabajo

Llamar a través de trabajo utiliza Unified Communications Web API (UCWA), que se instala automáticamente en todos los de Skype para Business Server servidores frontales. Para habilitar a los usuarios para llamar a través de trabajo, también debe tener los siguientes requisitos previos en su lugar: 
  
- Debe tener un servidor de mediación implementado, como parte de un servidor Front-End o como una función independiente. Además, necesita implementar una puerta de enlace IP-PBX.
    
- Todos los usuarios que estarán habilitados para llamar a través de trabajo deben tener un marcado interno directo (DID) en el sistema de teléfono PBX. 
    
- Debe habilitar a todos los usuarios de llamar a través de trabajo para Telefonía IP empresarial. Al hacer esto, debe configurar el Skype para negocios hizo número para cada usuario al número DID correspondiente para el sistema de teléfono PBX correspondiente. 
    
- Todos los usuarios que van a usar llamar a través de trabajo deben tener **La configuración automática** seleccionado en su opción de **Conexiones avanzadas** en su Skype para cliente de empresa. Esto permite al cliente a descubrir las direcciones URL de UCWA. La selección predeterminada es **Configuración automática**.
    
- Para cada usuario llame a través de trabajo, habilitar el reenvío de llamadas y llamadas simultáneas. 
    
- Para cada usuario llame a través de trabajo, asegúrese de que se habilitan marcado en la conferencia y conferencia de acceso telefónico de salida. Esto permite a estos usuarios a conseguir dentro y fuera de Skype para conferencias de empresa.
    
- Asegúrese de que la delegación, llamada de equipo y grupo de respuesta están deshabilitados para todos los usuarios llamar a través de trabajo.
    
## <a name="deploy-call-via-work"></a>Implementar Vía trabajo

Una vez que se cumplan los requisitos previos, haga lo siguiente:
  
- Crear un número de teléfono global para la implementación de Skype para el negocio que se muestra en el identificador de llamadas del PBX de usuarios que realizan llamadas a llamar a través de trabajo. 
    
- Crear una o más directivas de llamar a través de trabajo
    
- Asignar una directiva de llamar a través de trabajo a cada usuario que se habilitará para llamar a través de trabajo
    
### <a name="create-the-call-via-work-global-phone-number"></a>Crear el número de teléfono global de Vía trabajo

- Escriba el siguiente cmdlet
    
  ```
  Set-CsRoutingConfiguration -CallViaWorkCallerId +<PhoneNumber>
  ```

    Por ejemplo, el siguiente cmdlet establece el número de teléfono global en 1-555-123-4567.
    
  ```
  Set-CsRoutingConfiguration -CallViaWorkCallerId +15551234567
  ```

### <a name="create-a-call-via-work-policy"></a>Crear directiva de Vía trabajo

- Escriba el siguiente cmdlet
    
  ```
  New-CsCallViaWorkPolicy [-Identity] <XdsIdentity> [-Tenant <guid>] [-Enabled <bool>] [-UseAdminCallbackNumber
    <bool>] [-AdminCallbackNumber <string>] [-InMemory] [-Force] [-WhatIf] [-Confirm]  [<CommonParameters>]

  ```

    Por ejemplo, el siguiente cmdlet crea una directiva de llamar a través de un trabajo llamada ContosoUser1CvWP, requiere que el usuario a utilizar un número de devolución de llamada de admin y ese número de devolución de llamada establece en 1-555-789-1234.
    
  ```
  New-CsCallViaWorkPolicy -Identity Tag:ContosoUser1CvWP -Enabled $true -UseAdminCallbackNumber $true -AdminCallbackNumber +15557891234
  ```

### <a name="assign-a-call-via-work-policy-to-a-user"></a>Asignar una política de llamar a través de trabajos a un usuario

- Escriba el siguiente cmdlet
    
  ```
  Grant-CsCallViaWorkPolicy -Identity <UserName> -PolicyName Tag:<PolicyName>
  ```

    Por ejemplo, el siguiente cmdlet asigna la política de llamar a través de trabajos "ContosoUser1CvWP" al usuario denominado **ContosoUser1**.
    
  ```
  Grant-CsCallViaWorkPolicy -Identity ContosoUser1 -PolicyName Tag:ContosoUser1CvWP
  ```

## <a name="see-also"></a>Vea también

#### 

[Plan para la llamada a través del trabajo en Skype de Business Server 2015](../plan-your-deployment/enterprise-voice-solution/call-via-work.md)

