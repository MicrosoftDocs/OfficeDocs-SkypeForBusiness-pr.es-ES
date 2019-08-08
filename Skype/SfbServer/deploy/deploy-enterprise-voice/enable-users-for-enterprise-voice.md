---
title: Habilitar usuarios para telefonía IP empresarial en Skype empresarial Server
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
ms.assetid: f252b23b-9641-4160-aa81-bf06dc2eced3
description: 'Resumen: Obtenga información sobre cómo permitir que los usuarios realicen y reciban llamadas mediante la telefonía IP empresarial en Skype empresarial Server.'
ms.openlocfilehash: cf9aab0f104582c57e745c95ae5cf8f24f07b3a5
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2019
ms.locfileid: "36240334"
---
# <a name="enable-users-for-enterprise-voice-in-skype-for-business-server"></a>Habilitar usuarios para telefonía IP empresarial en Skype empresarial Server
 
**Resumen:** Obtenga información sobre cómo permitir que los usuarios realicen y reciban llamadas mediante la telefonía IP empresarial en Skype empresarial Server.
  
Después de implementar la telefonía IP o las llamadas a través del trabajo, puede usar los siguientes procedimientos para permitir que un usuario realice llamadas mediante la telefonía IP empresarial:
  
> [!NOTE]
> De los procedimientos siguientes, solo el primero se puede realizar con el panel de control de Skype empresarial Server. Para el resto de los procedimientos, solo puede usar el shell de administración de Skype empresarial Server. 
  
- Habilite la cuenta de usuario de telefonía IP empresarial.
    
- (Opcional) Asignar a la cuenta de usuario una directiva de voz específica para el usuario.
    
- (Opcional) Asignar a la cuenta de usuario un plan de marcado específico para el usuario.
    
### <a name="to-enable-a-user-account-for-enterprise-voice"></a>Para habilitar una cuenta de usuario de telefonía IP empresarial

1. Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins, o como miembro del rol administrativo **CsVoiceAdministrator**, **CsServerAdministrator** o **CsAdministrator**.
    
2. Abra el panel de control de Skype empresarial Server.
    
3. En la barra de navegación izquierda, haga clic en **Usuarios**.
    
4. En el cuadro **Buscar usuarios**, escriba la primera parte del nombre para mostrar, el nombre, los apellidos, el nombre de la cuenta del Administrador de cuentas de seguridad (SAM), la dirección SIP o el identificador uniforme de recursos (URI) de línea de la cuenta de usuario que desee habilitar y, a continuación, haga clic en **Buscar**.
    
5. En la tabla, haga clic en la cuenta de usuario que desea habilitar para la telefonía IP empresarial.
    
6. En el menú **Editar**, haga clic en **Mostrar detalles**.
    
7. En la página **Editar usuario de Skype empresarial Server** , en **telefonía**, haga clic en telefonía **IP empresarial**.
    
8. Haga clic en **URI de línea** y, a continuación, escriba un número de teléfono exclusivo y normalizado (por ejemplo, tel:+14255550200).
    
9. Haga clic en **Confirmar**.
    
Para finalizar la habilitación de un usuario para telefonía IP empresarial, asegúrese de que el usuario tiene asignada una directiva de voz y un plan de marcado, ya sea global (asignada de forma predeterminada) o específica del usuario. De forma predeterminada, a todos los usuarios se les asigna una directiva de voz global y un plan de marcado. Si ya hubiera una directiva de voz o un plan de marcado a nivel de sitio para el sitio en el que se hospeda la cuenta de usuario, dichas directivas se aplicarán automáticamente al usuario. Para aplicar una directiva de voz o plan de marcado por usuario a un usuario, deberá ejecutar los cmdlets **Grant-CsVoicePolicy** y **Grant-CsDialPlan**. Para obtener más información, consulte los siguientes procedimientos de este tema.
## <a name="voice-policy-assignment"></a>Asignación de directivas de voz

Las directivas de voz globales y de nivel de sitio se asignan automáticamente a todas las cuentas de usuario habilitadas para telefonía IP empresarial. También puede crear directivas de voz aplicables a usuarios o grupos específicos. Estas directivas por usuario deben estar explícitamente asignadas a los usuarios o grupos. Si desea usar la Directiva de voz global o de sitio para todos los usuarios habilitados para telefonía IP empresarial, puede omitir esta sección y seguir marcando la sección [asignación de plan](enable-users-for-enterprise-voice.md#BKMK_DialPlanAssignment) en más adelante en este tema.
  
### <a name="to-assign-a-user-specific-voice-policy"></a>Para asignar una directiva de voz específica del usuario

1. Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.
    
2. Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.
    
3. Para asignar una directiva de voz de usuario existente a un usuario, ejecute lo siguiente en el símbolo del sistema:
    
   ```
   Grant-CsVoicePolicy -Identity <UserIdParameter> -PolicyName <String>
   ```

    Por ejemplo:
    
   ```
   Grant-CsVoicePolicy -Identity "Bob Kelly" -PolicyName VoicePolicyJapan
   ```

    En este ejemplo, se asigna al usuario con el nombre para mostrar Bob Kelly la Directiva de voz con el nombre **VoicePolicyJapan**.
    
## <a name="dial-plan-assignment"></a>Asignación de planes de marcado
<a name="BKMK_DialPlanAssignment"> </a>

Para completar la configuración de la cuenta de usuario para los usuarios de telefonía IP empresarial o para usuarios de conferencias de acceso telefónico local, el usuario debe tener asignado un plan de marcado. Las cuentas de usuario emplearán automáticamente el plan de marcado global o, si existe, el plan de marcado del sitio, en los casos en los que no se asigne explícitamente un plan de marcado creado particularmente para el usuario. Si desea usar el plan de marcado global o de sitio para todos los usuarios habilitados para telefonía IP empresarial, puede omitir esta sección.
  
### <a name="to-assign-a-user-specific-dial-plan"></a>Asignar un plan de marcado específico de usuario

1. Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.
    
2. Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.
    
3. Para asignar un plan de marcado específico del usuario, ejecute lo siguiente en el símbolo del sistema:
    
   ```
   Grant-CsDialPlan -Identity <UserIdParameter> -PolicyName <String>
   ```

    Por ejemplo:
    
   ```
   Grant-CsDialPlan -Identity "Bob Kelly" -PolicyName DialPlanJapan
   ```

    En este ejemplo, se asigna al usuario con el nombre para mostrar Bob Kelly el plan de marcado del usuario con el nombre **DialPlanJapan**.
    

