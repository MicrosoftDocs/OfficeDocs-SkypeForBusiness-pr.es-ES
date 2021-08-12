---
title: Implementar llamadas a través del trabajo en Skype Empresarial Server
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
description: 'Summary: Learn how to deploy Call Via Work in Skype Empresarial Server for some or all of your users.'
ms.openlocfilehash: ce4c49a1ba8766dbec6efbfe2b04ea91702eadf40c91cb6108f027765609cac4
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54303164"
---
# <a name="deploy-call-via-work-in-skype-for-business-server"></a>Implementar llamadas a través del trabajo en Skype Empresarial Server
 
**Resumen:** Obtenga información sobre cómo implementar Call Via Work en Skype Empresarial Server para algunos o todos los usuarios.
  
Siga estos pasos para implementar Call Via Work para los usuarios. Las consideraciones de planeación se analizan en [Plan for Call Via Work in Skype Empresarial Server](../plan-your-deployment/enterprise-voice-solution/call-via-work.md). En versiones anteriores del control remoto de llamadas de Lync Server era una característica que permitía a los usuarios controlar sus teléfonos PBX con Lync Server. En Skype Empresarial Server, esta característica se ha reemplazado por Llamar a través del trabajo. 
  
## <a name="prerequisites-for-call-via-work"></a>Requisitos previos para llamar a través del trabajo

La llamada a través del trabajo usa la API web de comunicaciones unificadas (UCWA), que se instala automáticamente en todos los Skype Empresarial Server front-end. Para habilitar a los usuarios para llamar a través del trabajo, también debe tener los siguientes requisitos previos: 
  
- Debe tener implementado un servidor de mediación, ya sea como parte de un servidor front-end o como un rol independiente. También debe implementar una puerta de enlace IP-PBX.
    
- Todos los usuarios que se habilitarán para llamar a través del trabajo deben tener un marcado directo interno (DID) en el sistema telefónico PBX. 
    
- Debe habilitar todos los usuarios de Llamadas a través del trabajo para Telefonía IP empresarial. Al hacerlo, debe configurar el número DID Skype Empresarial para cada usuario en el número DID correspondiente para el sistema telefónico PBX correspondiente. 
    
- Todos los usuarios que van a  usar Llamar  a través del trabajo deben tener la configuración automática seleccionada en su opción Conexiones avanzadas en su Skype Empresarial cliente. Esto permite al cliente detectar las direcciones URL de UCWA. **Configuración automática** es la selección predeterminada.
    
- Para cada usuario de Llamada a través del trabajo, habilite el reenvío de llamadas y la llamada simultánea. 
    
- Para cada usuario de llamada a través del trabajo, asegúrese de que las conferencias de acceso telefónico local y la salida de conferencia están habilitadas. Esto permite a estos usuarios entrar y salir de Skype Empresarial conferencias.
    
- Asegúrese de que la delegación, la llamada de equipo y el grupo de respuesta están deshabilitados para cada usuario de Llamada a través del trabajo.
    
## <a name="deploy-call-via-work"></a>Implementar llamada a través del trabajo

Una vez que se cumplan los requisitos previos, haga lo siguiente:
  
- Cree un número de teléfono global para la implementación que Skype Empresarial muestra en el identificador de llamada PBX de los usuarios que están realizando llamadas a través del trabajo. 
    
- Crear una o varias directivas de llamada a través del trabajo
    
- Asignar una directiva de llamada a través del trabajo a cada usuario que se habilitará para llamar a través del trabajo
    
### <a name="create-the-call-via-work-global-phone-number"></a>Crear el número de teléfono global De llamadas a través del trabajo

- Escriba el siguiente cmdlet
    
  ```powershell
  Set-CsRoutingConfiguration -CallViaWorkCallerId +<PhoneNumber>
  ```

    Por ejemplo, el siguiente cmdlet establece el número de teléfono global en 1-555-123-4567.
    
  ```powershell
  Set-CsRoutingConfiguration -CallViaWorkCallerId +15551234567
  ```

### <a name="create-a-call-via-work-policy"></a>Crear una directiva de llamada a través del trabajo

- Escriba el siguiente cmdlet
    
  ```powershell
  New-CsCallViaWorkPolicy [-Identity] <XdsIdentity> [-Tenant <guid>] [-Enabled <bool>] [-UseAdminCallbackNumber  <bool>] [-AdminCallbackNumber <string>] [-InMemory] [-Force] [-WhatIf] [-Confirm]  [<CommonParameters>]
  ```

    Por ejemplo, el siguiente cmdlet crea una directiva de llamada a través del trabajo denominada ContosoUser1CvWP, requiere que el usuario use un número de devolución de llamada de administrador y establece ese número de devolución de llamada en 1-555-789-1234.
    
  ```powershell
  New-CsCallViaWorkPolicy -Identity Tag:ContosoUser1CvWP -Enabled $true -UseAdminCallbackNumber $true -AdminCallbackNumber +15557891234
  ```

### <a name="assign-a-call-via-work-policy-to-a-user"></a>Asignar una directiva de llamada a través del trabajo a un usuario

- Escriba el siguiente cmdlet
    
  ```powershell
  Grant-CsCallViaWorkPolicy -Identity <UserName> -PolicyName Tag:<PolicyName>
  ```

    Por ejemplo, el siguiente cmdlet asigna la directiva de llamada a través del trabajo "ContosoUser1CvWP" al usuario denominado **ContosoUser1**.
    
  ```powershell
  Grant-CsCallViaWorkPolicy -Identity ContosoUser1 -PolicyName Tag:ContosoUser1CvWP
  ```

## <a name="see-also"></a>Consulte también

[Plan for Call Via Work in Skype Empresarial Server](../plan-your-deployment/enterprise-voice-solution/call-via-work.md)

