---
title: Probar conferencias de acceso telefónico local en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: f4ccbfd4-6075-466f-b459-20561318803d
description: 'Summary: Learn how to test dial-in conferencing in Skype for Business Server.'
ms.openlocfilehash: be1cf5bba5a5bec2076f78880343582be19eda70
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096736"
---
# <a name="test-dial-in-conferencing-in-skype-for-business-server"></a>Probar conferencias de acceso telefónico local en Skype Empresarial Server
 
**Resumen:** Obtenga información sobre cómo probar las conferencias de acceso telefónico local en Skype Empresarial Server.
  
Para realizar una comprobación final de la configuración de conferencia de acceso telefónico local, busque planes de marcado que tengan una región de conferencia de acceso telefónico local que no sea usada por ningún número de acceso, así como números de acceso que no tengan asignada ninguna región de conferencia de acceso telefónico local. También debe comprobar que la página web Configuración de conferencia de acceso telefónico local y los números de acceso telefónico local funcionan correctamente.
  
## <a name="find-dial-plans-with-a-dial-in-conferencing-region-that-is-not-used-by-an-access-number"></a>Buscar planes de marcado con una región de conferencia de acceso telefónico local que no se usa con un número de acceso

1. Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro del rol Cs-ServerAdministrator o CsAdministrator.
    
2. Inicie el Shell de administración de Skype Empresarial Server: haga clic en Inicio **,** en Todos los programas **,** **en Skype Empresarial 2015** y, a continuación, en Shell de administración **de Skype Empresarial Server**.
    
3. Ejecute los siguientes comandos en símbolo del sistema:
    
   ```PowerShell
   Get-CsDialinConferencingAccessNumber -EmptyRegion
   ```

    Este cmdlet devuelve todos los planes de marcado que tienen una región de conferencia de acceso telefónico local que no es usada por ningún número de acceso.
    
Para obtener más información, [vea Get-CsDialInConferencingAccessNumber](/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps).
  
## <a name="find-access-numbers-without-assigned-regions"></a>Buscar números de acceso sin regiones asignadas

1. Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro del rol Cs-ServerAdministrator o CsAdministrator.
    
2. Inicie el Shell de administración de Skype Empresarial Server: haga clic en Inicio **,** en Todos los programas **,** **en Skype Empresarial 2015** y, a continuación, en Shell de administración **de Skype Empresarial Server**.
    
3. Ejecute los siguientes comandos en símbolo del sistema:
    
   ```PowerShell
   Get-CsDialinConferencingAccessNumber -Region NULL
   ```

    Este cmdlet devuelve todos los números de acceso de conferencia de acceso telefónico local que no están asociados a ninguna región.
    
Para obtener más información, [vea Get-CsDialInConferencingAccessNumber](/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps).
  
## <a name="test-webpage-and-access-numbers"></a>Página web de prueba y números de acceso

Para comprobar que la página web Configuración de la conferencia de acceso telefónico local y los números de acceso telefónico local funcionan correctamente, debe realizar las siguientes acciones:
  
- Pruebe la página web Configuración de la conferencia de acceso telefónico local iniciando sesión en la dirección URL sencilla.
    
- Pruebe que los números de acceso telefónico local funcionan correctamente para un grupo de servidores específico ejecutando el script que se ofrece más adelante en este tema. Este script simula llamadas a números de acceso. Para usar este script necesita la dirección SIP y las credenciales de un cliente de comunicaciones unificadas (UC) que se hospede en el grupo de servidores específico.
    
### <a name="to-test-access-numbers-for-a-specific-pool"></a>Para probar números de acceso para un grupo de servidores específico

1. Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro del rol Cs-ServerAdministrator o CsAdministrator.
    
2. Inicie el Shell de administración de Skype Empresarial Server: haga clic en Inicio **,** en Todos los programas **,** **en Skype Empresarial 2015** y, a continuación, en Shell de administración **de Skype Empresarial Server**.
    
3. Ejecute los siguientes comandos en símbolo del sistema:
    
   ```PowerShell
   $credentials = Get-Credential
   User name:  testuser1@contoso.com
   Password:  ********
   Test-CsDialInConferencing -UserSipAddress sip:testuser1@contoso.com -UserCredential $credentials -TargetFqdn <serverName>.<domainName>.com -Verbose
   ```

    El informe resultante indica si hay errores, junto con la información de diagnóstico específica. La marca -Verbose proporciona información más detallada sobre cuántos números de acceso se encontraron y detalles sobre ellos.
    
Para obtener más información, [vea Test-CsDialInConferencing](/powershell/module/skype/test-csdialinconferencing?view=skype-ps).
