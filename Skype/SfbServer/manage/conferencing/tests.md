---
title: Probar la conferencia de acceso telefónico en Skype para Business Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f4ccbfd4-6075-466f-b459-20561318803d
description: 'Resumen: Obtenga información sobre cómo probar la conferencia de acceso telefónico en Skype para Business Server.'
ms.openlocfilehash: 99d91a4d3e9729da7b86f723f4a980a887d88b5f
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32197775"
---
# <a name="test-dial-in-conferencing-in-skype-for-business-server"></a>Probar la conferencia de acceso telefónico en Skype para Business Server
 
**Resumen:** Obtenga información sobre cómo probar la conferencia de acceso telefónico en Skype para Business Server.
  
Como comprobación final de la configuración de las conferencias de acceso telefónico local, puede buscar planes de marcado que tengan una región de conferencia de acceso telefónico local que no sea usada por ningún número de acceso, así como números de acceso que no tengan asignada una región de conferencia de acceso telefónico local. También debe comprobar que la página web Configuración de la conferencia de acceso telefónico local y los números de acceso telefónico local funcionan correctamente.
  
## <a name="find-dial-plans-with-a-dial-in-conferencing-region-that-is-not-used-by-an-access-number"></a>Buscar planes de marcado con una región de conferencia de acceso telefónico local que no sea usada por ningún número de acceso

1. Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins, o bien como miembro del rol Cs-ServerAdministrator o CsAdministrator.
    
2. Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.
    
3. Ejecute los siguientes comandos en símbolo del sistema:
    
   ```
   Get-CsDialinConferencingAccessNumber -EmptyRegion
   ```

    Este cmdlet devuelve todos los planes de marcado que tienen una región de conferencia de acceso telefónico local que no es usada por ningún número de acceso.
    
Para obtener más información, vea [Get-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps).
  
## <a name="find-access-numbers-without-assigned-regions"></a>Buscar números de acceso sin regiones asignadas

1. Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins, o bien como miembro del rol Cs-ServerAdministrator o CsAdministrator.
    
2. Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.
    
3. Ejecute los siguientes comandos en símbolo del sistema:
    
   ```
   Get-CsDialinConferencingAccessNumber -Region NULL
   ```

    Este cmdlet devuelve todos los números de acceso de conferencia de acceso telefónico local que no están asociados a ninguna región.
    
Para obtener más información, vea [Get-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps).
  
## <a name="test-webpage-and-access-numbers"></a>Página web y números de acceso de prueba

Para comprobar que la página web Configuración de la conferencia de acceso telefónico local y los números de acceso telefónico local funcionan correctamente, debe realizar las siguientes acciones:
  
- Pruebe la página web Configuración de la conferencia de acceso telefónico local iniciando sesión en la dirección URL sencilla.
    
- Pruebe que los números de acceso telefónico local funcionan correctamente para un grupo de servidores específico ejecutando el script que se ofrece más adelante en este tema. Este script simula llamadas a números de acceso. Para usar este script necesita la dirección SIP y las credenciales de un cliente de comunicaciones unificadas (UC) que se hospede en el grupo de servidores específico.
    
### <a name="to-test-access-numbers-for-a-specific-pool"></a>Para probar números de acceso para un grupo de servidores específico

1. Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins, o bien como miembro del rol Cs-ServerAdministrator o CsAdministrator.
    
2. Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.
    
3. Ejecute los siguientes comandos en símbolo del sistema:
    
   ```
   $credentials = Get-Credential
   User name:  testuser1@contoso.com
   Password:  ********
   Test-CsDialInConferencing -UserSipAddress sip:testuser1@contoso.com -UserCredential $credentials -TargetFqdn <serverName>.<domainName>.com -Verbose
   ```

    El informe resultante indica si hay errores, junto con la información de diagnóstico específica. -Verbose marca proporciona más información detallan sobre el acceso de cuántas se han encontrado números y detalles acerca de ellos.
    
Para obtener más información, consulte [Test-CsDialInConferencing](https://docs.microsoft.com/powershell/module/skype/test-csdialinconferencing?view=skype-ps).
  

