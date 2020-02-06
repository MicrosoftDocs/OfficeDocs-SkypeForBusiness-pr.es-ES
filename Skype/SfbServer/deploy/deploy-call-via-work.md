---
title: Implementación de llamadas mediante el trabajo en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4802d733-14ef-4509-92b9-07173614e45f
description: 'Resumen: Aprenda a implementar llamadas mediante el trabajo en Skype empresarial Server para algunos o todos los usuarios.'
ms.openlocfilehash: 9b77207d6618e4a869ae369697bc8395aba81673
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41791088"
---
# <a name="deploy-call-via-work-in-skype-for-business-server"></a>Implementación de llamadas mediante el trabajo en Skype empresarial Server
 
**Resumen:** Aprenda a implementar llamadas mediante el trabajo en Skype empresarial Server para algunos o todos los usuarios.
  
Siga estos pasos para implementar llamadas por trabajo para sus usuarios. Las consideraciones de planeación se tratan en [plan para llamar mediante el trabajo en Skype empresarial Server](../plan-your-deployment/enterprise-voice-solution/call-via-work.md). En versiones anteriores de Lync Server, el control remoto de llamadas era una característica que permitía a los usuarios controlar sus teléfonos PBX con Lync Server. En Skype empresarial Server, esta característica se ha sustituido por una llamada por trabajo. 
  
## <a name="prerequisites-for-call-via-work"></a>Requisitos previos para llamar por trabajo

La llamada a través del trabajo usa la API Web de comunicaciones unificadas (UCWA), que se instala automáticamente en todos los servidores front-end de Skype empresarial Server. Para habilitar a los usuarios para que realicen llamadas por trabajo, también debe disponer de los siguientes requisitos previos: 
  
- Debe tener un servidor de mediación implementado, ya sea como parte de un servidor front-end o como un rol independiente. Además, necesita implementar una puerta de enlace IP-PBX.
    
- Todos los usuarios que vayan a estar habilitados para realizar llamadas a través del trabajo deben tener un marcado directo (en el sistema telefónico PBX). 
    
- Debe habilitar todas las llamadas a través de usuarios del trabajo para telefonía IP empresarial. Al hacerlo, debe configurar el número de Skype empresarial realizado para cada usuario en el número de ha correspondiente al sistema telefónico PBX correspondiente. 
    
- Todos los usuarios que vayan a usar las llamadas a través del trabajo deben tener la **configuración automática** seleccionada en la opción **conexiones avanzadas** en el cliente de Skype empresarial. Esto permite al cliente descubrir las direcciones URL de UCWA. La selección predeterminada es **Configuración automática**.
    
- Para cada llamada a través de usuario del trabajo, habilitar el desvío de llamadas y las llamadas simultáneas. 
    
- Para cada llamada a través de usuario del trabajo, asegúrese de que la opción de conferencia de acceso telefónico local está habilitada. Esto permite a estos usuarios entrar y salir de las conferencias de Skype empresarial.
    
- Asegúrese de que la delegación, la llamada de equipo y el grupo de respuesta estén deshabilitadas para cada llamada por usuario del trabajo.
    
## <a name="deploy-call-via-work"></a>Implementar Vía trabajo

Una vez que se cumplan los requisitos previos, haga lo siguiente:
  
- Cree un número de teléfono global para su implementación en el que se muestra Skype empresarial en la identificación de llamadas de PBX de los usuarios que hacen llamadas a través del trabajo. 
    
- Crear una o más llamadas a través de directivas de trabajo
    
- Asignar una llamada a través de la Directiva de trabajo a cada usuario que se habilitará para realizar llamadas por trabajo
    
### <a name="create-the-call-via-work-global-phone-number"></a>Crear el número de teléfono global de Vía trabajo

- Escriba el siguiente cmdlet
    
  ```powershell
  Set-CsRoutingConfiguration -CallViaWorkCallerId +<PhoneNumber>
  ```

    Por ejemplo, el siguiente cmdlet establece el número de teléfono global en 1-555-123-4567.
    
  ```powershell
  Set-CsRoutingConfiguration -CallViaWorkCallerId +15551234567
  ```

### <a name="create-a-call-via-work-policy"></a>Crear directiva de Vía trabajo

- Escriba el siguiente cmdlet
    
  ```powershell
  New-CsCallViaWorkPolicy [-Identity] <XdsIdentity> [-Tenant <guid>] [-Enabled <bool>] [-UseAdminCallbackNumber  <bool>] [-AdminCallbackNumber <string>] [-InMemory] [-Force] [-WhatIf] [-Confirm]  [<CommonParameters>]
  ```

    Por ejemplo, el siguiente cmdlet crea una llamada a través de la Directiva de trabajo denominada ContosoUser1CvWP, requiere que el usuario Use un número de devolución de llamada de administrador y establece ese número de devolución de llamada en 1-555-789-1234.
    
  ```powershell
  New-CsCallViaWorkPolicy -Identity Tag:ContosoUser1CvWP -Enabled $true -UseAdminCallbackNumber $true -AdminCallbackNumber +15557891234
  ```

### <a name="assign-a-call-via-work-policy-to-a-user"></a>Asignar una llamada a través de la Directiva de trabajo a un usuario

- Escriba el siguiente cmdlet
    
  ```powershell
  Grant-CsCallViaWorkPolicy -Identity <UserName> -PolicyName Tag:<PolicyName>
  ```

    Por ejemplo, el siguiente cmdlet asigna la llamada a través de la Directiva de trabajo "ContosoUser1CvWP" al usuario denominado **ContosoUser1**.
    
  ```powershell
  Grant-CsCallViaWorkPolicy -Identity ContosoUser1 -PolicyName Tag:ContosoUser1CvWP
  ```

## <a name="see-also"></a>Vea también

[Plan de llamadas por trabajo en Skype empresarial Server](../plan-your-deployment/enterprise-voice-solution/call-via-work.md)

