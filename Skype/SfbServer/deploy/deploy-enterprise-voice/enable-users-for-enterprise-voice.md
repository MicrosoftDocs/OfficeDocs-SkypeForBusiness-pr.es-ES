---
title: Habilitar usuarios para Telefonía IP empresarial en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f252b23b-9641-4160-aa81-bf06dc2eced3
description: 'Resumen: aprenda a permitir que los usuarios realicen y reciban llamadas mediante Telefonía IP empresarial en Skype Empresarial Server.'
ms.openlocfilehash: 3dab9488b1d184f5d3dd215f4012933de1ca0245
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/08/2021
ms.locfileid: "60864347"
---
# <a name="enable-users-for-enterprise-voice-in-skype-for-business-server"></a>Habilitar usuarios para Telefonía IP empresarial en Skype Empresarial Server
 
**Resumen:** Obtenga información sobre cómo permitir que los usuarios realicen y reciban llamadas mediante Telefonía IP empresarial en Skype Empresarial Server.
  
Después de implementar Telefonía IP empresarial o Llamar a través del trabajo, puede usar los siguientes procedimientos para permitir que un usuario realice llamadas mediante Telefonía IP empresarial:
  
> [!NOTE]
> De los siguientes procedimientos, solo el primero se puede realizar mediante el Skype Empresarial Server panel de control. Para los procedimientos restantes, solo puede usar Skype Empresarial Server Shell de administración. 
  
- Habilite la cuenta de usuario para Telefonía IP empresarial.
    
- (Opcional) Asignar a la cuenta de usuario una directiva de voz específica para el usuario.
    
- (Opcional) Asignar a la cuenta de usuario un plan de marcado específico para el usuario.
    
### <a name="to-enable-a-user-account-for-enterprise-voice"></a>Para habilitar una cuenta de usuario para Telefonía IP empresarial

1. Inicie sesión en el equipo como un miembro del grupo RTCUniversalServerAdmins o bien, como un miembro de la función administrativa **CsVoiceAdministrator**, **CsServerAdministrator** o **CsAdministrator**.
    
2. Abra Skype Empresarial Server Panel de control.
    
3. En la barra de navegación izquierda, haga clic en **Usuarios**.
    
4. En el cuadro **Buscar usuarios**, escriba la primera parte del nombre para mostrar, el nombre, los apellidos, el nombre de la cuenta del Administrador de cuentas de seguridad (SAM), la dirección SIP o el identificador uniforme de recursos (URI) de línea de la cuenta de usuario que desee habilitar y, a continuación, haga clic en **Buscar**.
    
5. En la tabla, haga clic en la cuenta de usuario que desea habilitar para Telefonía IP empresarial.
    
6. En el menú **Editar**, haga clic en **Mostrar detalles**.
    
7. En la **página Editar Skype Empresarial Server usuario,** en **Telefonía**, haga clic **en Telefonía IP empresarial**.
    
8. Haga **clic en URI** de línea y, a continuación, escriba un número de teléfono único normalizado (por ejemplo, `tel:+14255550200` ).
    
9. Haga clic en **Confirmar**.
    
Para finalizar la habilitación de un usuario para Telefonía IP empresarial, asegúrese de que al usuario se le asigna una directiva de voz y un plan de marcado, ya sea global (asignado de forma predeterminada) o específico del usuario. De forma predeterminada, a todos los usuarios se les asigna una directiva de voz global y un plan de marcado. Si ya hubiera una directiva de voz o un plan de marcado a nivel de sitio para el sitio en el que se hospeda la cuenta de usuario, se aplicarán automáticamente al usuario. Para aplicar una directiva de voz o plan de marcado por usuario a un usuario, deberá ejecutar los cmdlets **Grant-CsVoicePolicy** y **Grant-CsDialPlan**. Para obtener más información, consulte los siguientes procedimientos en este tema.
## <a name="voice-policy-assignment"></a>Asignación de directivas de voz

Las directivas de voz globales y de nivel de sitio se asignan automáticamente a todas las cuentas de usuario habilitadas para Telefonía IP empresarial. También puede crear directivas de voz aplicables a usuarios o grupos específicos. Estas directivas por usuario deben estar explícitamente asignadas a los usuarios o grupos. Si desea usar la directiva de voz global o de sitio para todos los usuarios que están habilitados para Telefonía IP empresarial, puede omitir esta sección y continuar con la sección [Asignación](enable-users-for-enterprise-voice.md#BKMK_DialPlanAssignment) de plan de marcado más adelante en este tema.
  
### <a name="to-assign-a-user-specific-voice-policy"></a>Para asignar una directiva de voz específica del usuario

1. Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.
    
2. Inicie el Shell Skype Empresarial Server administración: haga clic en Inicio **,** todos los programas **,** haga clic en **Skype Empresarial 2015** y, a continuación, haga clic **Skype Empresarial Server Shell de administración**.
    
3. Para asignar una directiva de voz de usuario existente a un usuario, ejecute lo siguiente en el símbolo del sistema:
    
   ```powershell
   Grant-CsVoicePolicy -Identity <UserIdParameter> -PolicyName <String>
   ```

    Por ejemplo:
    
   ```powershell
   Grant-CsVoicePolicy -Identity "Bob Kelly" -PolicyName VoicePolicyJapan
   ```

    En este ejemplo, al usuario con el nombre para mostrar Bob Kelly se le asigna la directiva de voz con el nombre **VoicePolicyJapan**.
    
## <a name="dial-plan-assignment"></a>Asignación de planes de marcado
<a name="BKMK_DialPlanAssignment"> </a>

Para completar la configuración de cuentas de usuario para los usuarios de Telefonía IP empresarial o para los usuarios de conferencias de acceso telefónico local, asigne un plan de marcado. Las cuentas de usuario emplearán automáticamente el plan de marcado global o, si existe, el plan de marcado del sitio, en los casos en los que no se asigne explícitamente un plan de marcado creado particularmente para el usuario. Si desea usar el plan de marcado global o de sitio para todos los usuarios que están habilitados para Telefonía IP empresarial, puede omitir esta sección.
  
### <a name="to-assign-a-user-specific-dial-plan"></a>Para asignar un plan de marcado específico del usuario

1. Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.
    
2. Inicie el Shell Skype Empresarial Server administración: haga clic en Inicio **,** todos los programas **,** haga clic en **Skype Empresarial 2015** y, a continuación, haga clic **Skype Empresarial Server Shell de administración**.
    
3. Para asignar un plan de marcado específico del usuario, ejecute lo siguiente en el símbolo del sistema:
    
   ```powershell
   Grant-CsDialPlan -Identity <UserIdParameter> -PolicyName <String>
   ```

    Por ejemplo:
    
   ```powershell
   Grant-CsDialPlan -Identity "Bob Kelly" -PolicyName DialPlanJapan
   ```

    En este ejemplo, al usuario con el nombre para mostrar Bob Kelly se le asigna el plan de marcado de usuario con el nombre **DialPlanJapan**.
    

