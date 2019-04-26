---
title: Implementar vía trabajo en Skype para Business Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4802d733-14ef-4509-92b9-07173614e45f
description: 'Resumen: Obtenga información sobre cómo implementar llamar vía trabajo en Skype para Business Server para algunos o todos los usuarios.'
ms.openlocfilehash: d0cee2cbf3a88514983efd77e2b1728b2df1e792
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32227539"
---
# <a name="deploy-call-via-work-in-skype-for-business-server"></a>Implementar vía trabajo en Skype para Business Server
 
**Resumen:** Obtenga información sobre cómo implementar llamar vía trabajo en Skype para Business Server para algunos o todos los usuarios.
  
Siga estos pasos para implementar llamadas vía trabajo para los usuarios. Se describen las consideraciones de planeación en [Plan para llamar vía trabajo en Skype para Business Server](../plan-your-deployment/enterprise-voice-solution/call-via-work.md). En versiones anteriores de llamada remota de Lync Server control era una característica que habilita a los usuarios controlar sus teléfonos PBX con Lync Server. En Skype para Business Server, esta característica se ha reemplazado con llamar vía trabajo. 
  
## <a name="prerequisites-for-call-via-work"></a>Requisitos previos para la llamada vía trabajo

Llamar vía trabajo usa Unified Communications Web API (UCWA), que se instala automáticamente en Skype todos los servidores Front-End de Business Server. Para habilitar a los usuarios para llamar vía trabajo, también debe tener los siguientes requisitos previos en su lugar: 
  
- Debe tener un servidor de mediación implementados, ya sea como parte de un servidor Front-End o como una función independiente. Además, necesita implementar una puerta de enlace IP-PBX.
    
- Todos los usuarios que va a estar habilitados para llamar vía trabajo deben tener una llamada directa (DID) en el sistema de teléfono PBX. 
    
- Debe habilitar a todos los usuarios de llamar vía trabajo para Enterprise Voice. En este caso, debe configurar el Skype para número DID empresarial para cada usuario al número DID correspondiente para el sistema de teléfono PBX correspondiente. 
    
- Todos los usuarios que van a usar llamar vía trabajo deben tener **La configuración automática** seleccionado en su opción de **Conexiones avanzadas** en su Skype para clientes empresariales. Esto permite que el cliente descubrir las direcciones URL de UCWA. La selección predeterminada es **Configuración automática**.
    
- Para cada usuario llamar vía trabajo, habilitar el desvío de llamadas y llamadas simultáneas. 
    
- Para cada usuario llamar vía trabajo, asegúrese de que estén habilitadas las conferencias telefónicas y salida de conferencia. Esto permite a estos usuarios obtener y desconectarse de Skype para conferencias de empresa.
    
- Asegúrese de que la delegación, llamada de equipo y grupo de respuesta se deshabilitan para todos los usuarios llamar vía trabajo.
    
## <a name="deploy-call-via-work"></a>Implementar Vía trabajo

Una vez que se cumplan los requisitos previos, haga lo siguiente:
  
- Crear un número de teléfono globales para la implementación que Skype para la empresa que se muestra en el identificador de autor de la llamada de la PBX de los usuarios que se va a realizar llamadas de llamar vía trabajo. 
    
- Crear una o varias directivas de llamar vía trabajo
    
- Asignar una directiva de llamada vía trabajo a cada usuario que va a estar habilitada para llamar vía trabajo
    
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
  New-CsCallViaWorkPolicy [-Identity] <XdsIdentity> [-Tenant <guid>] [-Enabled <bool>] [-UseAdminCallbackNumber  <bool>] [-AdminCallbackNumber <string>] [-InMemory] [-Force] [-WhatIf] [-Confirm]  [<CommonParameters>]
  ```

    Por ejemplo, el siguiente cmdlet crea una directiva de llamada vía trabajo denominada ContosoUser1CvWP, requiere que el usuario usar un número de devolución de llamada de administración y establece ese número de devolución de llamada a 1-555-789-1234.
    
  ```
  New-CsCallViaWorkPolicy -Identity Tag:ContosoUser1CvWP -Enabled $true -UseAdminCallbackNumber $true -AdminCallbackNumber +15557891234
  ```

### <a name="assign-a-call-via-work-policy-to-a-user"></a>Asignar una directiva de llamada vía trabajo a un usuario

- Escriba el siguiente cmdlet
    
  ```
  Grant-CsCallViaWorkPolicy -Identity <UserName> -PolicyName Tag:<PolicyName>
  ```

    Por ejemplo, el siguiente cmdlet asigna la directiva de llamada vía trabajo "ContosoUser1CvWP" al usuario denominado **ContosoUser1**.
    
  ```
  Grant-CsCallViaWorkPolicy -Identity ContosoUser1 -PolicyName Tag:ContosoUser1CvWP
  ```

## <a name="see-also"></a>Vea también

[Planeación de la llamada vía trabajo en Skype para Business Server](../plan-your-deployment/enterprise-voice-solution/call-via-work.md)

