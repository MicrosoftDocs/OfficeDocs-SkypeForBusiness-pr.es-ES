---
title: Habilitar a usuarios para Enterprise Voice en Skype para Business Server
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f252b23b-9641-4160-aa81-bf06dc2eced3
description: 'Resumen: Obtenga información sobre cómo habilitar a los usuarios realizar y recibir llamadas mediante el uso de Enterprise Voice en Skype para Business Server.'
ms.openlocfilehash: abba652665660299ccb1e3b9a55961ca2248225e
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2018
ms.locfileid: "21025669"
---
# <a name="enable-users-for-enterprise-voice-in-skype-for-business-server"></a>Habilitar a usuarios para Enterprise Voice en Skype para Business Server
 
**Resumen:** Obtenga información sobre cómo habilitar a los usuarios realizar y recibir llamadas mediante el uso de Enterprise Voice en Skype para Business Server.
  
Después de implementar Enterprise Voice o llamar vía trabajo, puede usar los siguientes procedimientos para habilitar a un usuario realizar llamadas mediante el uso de Enterprise Voice:
  
> [!NOTE]
> De los procedimientos siguientes, sólo la primera se puede realizar mediante el uso de Skype para el Panel de Control de servidor empresarial. Para los restantes procedimientos, puede usar Skype sólo para el Shell de administración de servidor empresarial. 
  
- Habilitar la cuenta de usuario para Enterprise Voice.
    
- (Opcional) Asignar a la cuenta de usuario una directiva de voz específica para el usuario.
    
- (Opcional) Asignar a la cuenta de usuario un plan de marcado específico para el usuario.
    
### <a name="to-enable-a-user-account-for-enterprise-voice"></a>Para habilitar una cuenta de usuario para Enterprise Voice

1. Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins, o como miembro del rol administrativo **CsVoiceAdministrator**, **CsServerAdministrator** o **CsAdministrator**.
    
2. Abra Skype para el Panel de Control de servidor empresarial.
    
3. En la barra de navegación izquierda, haga clic en **Usuarios**.
    
4. En el cuadro **Buscar usuarios**, escriba la primera parte del nombre para mostrar, el nombre, los apellidos, el nombre de la cuenta del Administrador de cuentas de seguridad (SAM), la dirección SIP o el identificador uniforme de recursos (URI) de línea de la cuenta de usuario que desee habilitar y, a continuación, haga clic en **Buscar**.
    
5. En la tabla, haga clic en la cuenta de usuario que desea habilitar para Enterprise Voice.
    
6. En el menú **Editar**, haga clic en **Mostrar detalles**.
    
7. En la página **Editar Skype para usuarios del servidor de empresa** , en **telefonía**, haga clic en **Enterprise Voice**.
    
8. Haga clic en **URI de línea** y, a continuación, escriba un número de teléfono exclusivo y normalizado (por ejemplo, tel:+14255550200).
    
9. Haga clic en **Confirmar**.
    
Para terminar de habilitar un usuario para Enterprise Voice, asegúrese de que el usuario tiene asignada una directiva de voz y un plan de marcado, ya sea global (asignado de forma predeterminada) o específica del usuario. De forma predeterminada, todos los usuarios se les asigna una directiva de voz global y plan de marcado. Si ya hubiera una directiva de voz o un plan de marcado a nivel de sitio para el sitio en el que se hospeda la cuenta de usuario, dichas directivas se aplicarán automáticamente al usuario. Para aplicar una directiva de voz por usuario o plan a un usuario de marcado, debe ejecutar los cmdlets **Grant-CsVoicePolicy** y **Grant-CsDialPlan** . Para obtener más información, consulte los siguientes procedimientos de este tema.
## <a name="voice-policy-assignment"></a>Asignación de directivas de voz

Las directivas de voz global y de nivel de sitio se asignan automáticamente a todas las cuentas de usuario que están habilitadas para Enterprise Voice. También puede crear directivas de voz aplicables a usuarios o grupos específicos. Estas directivas por usuario deben estar explícitamente asignadas a los usuarios o grupos. Si desea usar la información global o sitio directiva de voz para todos los usuarios que están habilitados para Enterprise Voice, puede omitir esta sección y continuar con la sección [Asignación de Plan de marcado](enable-users-for-enterprise-voice.md#BKMK_DialPlanAssignment) más adelante en este tema.
  
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

    En este ejemplo, el usuario con el nombre para mostrar Bob Kelly es asignado la directiva de voz con el nombre **VoicePolicyJapan**.
    
## <a name="dial-plan-assignment"></a>Asignación de planes de marcado
<a name="BKMK_DialPlanAssignment"> </a>

Para completar la configuración de la cuenta de usuario para los usuarios de Enterprise Voice o los usuarios de conferencia de acceso telefónico, el usuario debe estar asignado un plan de marcado. Las cuentas de usuario emplearán automáticamente el plan de marcado global o, si existe, el plan de marcado del sitio, en los casos en los que no se asigne explícitamente un plan de marcado creado particularmente para el usuario. Si desea usar la información global o sitio plan de marcado para todos los usuarios que están habilitados para Enterprise Voice, puede omitir esta sección.
  
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

    En este ejemplo, el usuario con el nombre para mostrar Bob Kelly es asignado el plan de marcado de usuario con el nombre **DialPlanJapan**.
    

