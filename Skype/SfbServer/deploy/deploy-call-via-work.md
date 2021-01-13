---
title: Implementar Vía trabajo en Skype Empresarial Server
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
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4802d733-14ef-4509-92b9-07173614e45f
description: 'Resumen: obtenga información sobre cómo implementar Vía trabajo en Skype Empresarial Server para algunos o todos los usuarios.'
ms.openlocfilehash: 41a0ae8462b12cabf735a2501e5b22eac64abe42
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825010"
---
# <a name="deploy-call-via-work-in-skype-for-business-server"></a>Implementar Vía trabajo en Skype Empresarial Server
 
**Resumen:** Obtenga información sobre cómo implementar Vía trabajo en Skype Empresarial Server para algunos o todos los usuarios.
  
Siga estos pasos para implementar Vía trabajo para los usuarios. Las consideraciones de planeación se analizan en [Plan for Call Via Work in Skype for Business Server](../plan-your-deployment/enterprise-voice-solution/call-via-work.md). En versiones anteriores del control remoto de llamadas de Lync Server era una característica que permitía a los usuarios controlar sus teléfonos PBX con Lync Server. En Skype Empresarial Server, esta característica se ha reemplazado por Vía trabajo. 
  
## <a name="prerequisites-for-call-via-work"></a>Requisitos previos para Vía trabajo

Vía trabajo usa la API web de comunicaciones unificadas (UCWA), que se instala automáticamente en todos los servidores front-end de Skype Empresarial Server. Para habilitar a los usuarios para Vía trabajo, también debe tener los siguientes requisitos previos: 
  
- Debe tener implementado un servidor de mediación, ya sea como parte de un servidor front-end o como un rol independiente. También debe implementar una puerta de enlace IP-PBX.
    
- Todos los usuarios que se habilitarán para Vía trabajo deben tener una llamada directa a la extensión (DID) en el sistema telefónico PBX. 
    
- Debe habilitar todos los usuarios de Vía trabajo para Telefonía IP empresarial. Al hacerlo, debe configurar el número DID de Skype Empresarial para cada usuario en el número DID correspondiente para el sistema telefónico PBX correspondiente. 
    
- Todos los usuarios que usarán  Vía trabajo deben tener la configuración automática seleccionada en su opción De **conexiones** avanzadas en su cliente de Skype Empresarial. Esto permite al cliente detectar las direcciones URL de UCWA. **La configuración** automática es la selección predeterminada.
    
- Para cada usuario de Vía trabajo, habilite el reenvío de llamadas y las llamadas simultáneas. 
    
- Para cada usuario de Vía trabajo, asegúrese de que las conferencias de acceso telefónico local y la conferencia de acceso telefónico local estén habilitadas. Esto permite a estos usuarios entrar y salir de las conferencias de Skype Empresarial.
    
- Asegúrese de que la delegación, la llamada de equipo y el grupo de respuesta están deshabilitados para cada usuario de Vía trabajo.
    
## <a name="deploy-call-via-work"></a>Implementar llamada a través del trabajo

Una vez que se cumplan los requisitos previos, haga lo siguiente:
  
- Cree un número de teléfono global para su implementación que Skype Empresarial muestre en el identificador de llamada de PBX de los usuarios que están realizando llamadas vía trabajo. 
    
- Crear una o varias directivas vía trabajo
    
- Asignar una directiva vía trabajo a cada usuario que se habilitará para Vía trabajo
    
### <a name="create-the-call-via-work-global-phone-number"></a>Crear el número de teléfono global Vía trabajo

- Escriba el siguiente cmdlet
    
  ```powershell
  Set-CsRoutingConfiguration -CallViaWorkCallerId +<PhoneNumber>
  ```

    Por ejemplo, el siguiente cmdlet establece el número de teléfono global en 1-555-123-4567.
    
  ```powershell
  Set-CsRoutingConfiguration -CallViaWorkCallerId +15551234567
  ```

### <a name="create-a-call-via-work-policy"></a>Crear una directiva vía trabajo

- Escriba el siguiente cmdlet
    
  ```powershell
  New-CsCallViaWorkPolicy [-Identity] <XdsIdentity> [-Tenant <guid>] [-Enabled <bool>] [-UseAdminCallbackNumber  <bool>] [-AdminCallbackNumber <string>] [-InMemory] [-Force] [-WhatIf] [-Confirm]  [<CommonParameters>]
  ```

    Por ejemplo, el siguiente cmdlet crea una directiva vía trabajo llamada ContosoUser1CvWP, requiere que el usuario use un número de devolución de llamada de administrador y establece ese número de devolución de llamada en 1-555-789-1234.
    
  ```powershell
  New-CsCallViaWorkPolicy -Identity Tag:ContosoUser1CvWP -Enabled $true -UseAdminCallbackNumber $true -AdminCallbackNumber +15557891234
  ```

### <a name="assign-a-call-via-work-policy-to-a-user"></a>Asignar una directiva vía trabajo a un usuario

- Escriba el siguiente cmdlet
    
  ```powershell
  Grant-CsCallViaWorkPolicy -Identity <UserName> -PolicyName Tag:<PolicyName>
  ```

    Por ejemplo, el siguiente cmdlet asigna la directiva vía trabajo "ContosoUser1CvWP" al usuario llamado **ContosoUser1**.
    
  ```powershell
  Grant-CsCallViaWorkPolicy -Identity ContosoUser1 -PolicyName Tag:ContosoUser1CvWP
  ```

## <a name="see-also"></a>Vea también

[Plan for Call Via Work in Skype for Business Server](../plan-your-deployment/enterprise-voice-solution/call-via-work.md)

