---
title: Habilitar a los usuarios para la telefonía IP empresarial en Skype Empresarial Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: f252b23b-9641-4160-aa81-bf06dc2eced3
description: 'Resumen: Conozca cómo habilitar los usuarios realizar y recibir llamadas mediante Telefonía IP empresarial de Skype para Business Server 2015.'
ms.openlocfilehash: d187723b347121400bfbce00d238851f2d0651a9
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="enable-users-for-enterprise-voice-in-skype-for-business-server-2015"></a>Habilitar a los usuarios para la telefonía IP empresarial en Skype Empresarial Server 2015
 
**Resumen:** Aprenda a habilitar los usuarios realizar y recibir llamadas mediante Telefonía IP empresarial de Skype para Business Server 2015.
  
Después de implementar la Telefonía IP empresarial o llamar a través de trabajo, puede utilizar los siguientes procedimientos para habilitar un usuario realizar llamadas mediante Telefonía IP empresarial:
  
> [!NOTE]
> De los procedimientos siguientes, sólo la primera puede realizarse mediante Skype para Panel de Control de servidor de Business. Para los restantes procedimientos, puede utilizar Skype sólo para el Shell de administración de servidor de empresa. 
  
- Habilitar la cuenta de usuario para Telefonía IP empresarial.
    
- (Opcional) Asignar a la cuenta de usuario una directiva de voz específica para el usuario.
    
- (Opcional) Asignar a la cuenta de usuario un plan de marcado específico para el usuario.
    
### <a name="to-enable-a-user-account-for-enterprise-voice"></a>Para habilitar una cuenta de usuario para Telefonía IP empresarial

1. Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins, o como miembro del rol administrativo **CsVoiceAdministrator**, **CsServerAdministrator** o **CsAdministrator**.
    
2. Abre Skype para Panel de Control del servidor de empresa.
    
3. En la barra de navegación izquierda, haga clic en **Usuarios**.
    
4. En el cuadro **Buscar usuarios**, escriba la primera parte del nombre para mostrar, el nombre, los apellidos, el nombre de la cuenta del Administrador de cuentas de seguridad (SAM), la dirección SIP o el identificador uniforme de recursos (URI) de línea de la cuenta de usuario que desee habilitar y, a continuación, haga clic en **Buscar**.
    
5. En la tabla, haga clic en la cuenta de usuario que desea habilitar para Telefonía IP empresarial.
    
6. En el menú **Editar**, haga clic en **Mostrar detalles**.
    
7. En la página **Editar Skype para usuarios del servidor de empresa** , en **telefonía**, haga clic en **Telefonía IP empresarial**.
    
8. Haga clic en **URI de línea** y, a continuación, escriba un número de teléfono exclusivo y normalizado (por ejemplo, tel:+14255550200).
    
9. Haga clic en **Confirmar**.
    
Para terminar la habilitación de un usuario de Telefonía IP empresarial, asegúrese de que el usuario tiene asignada una directiva de voz y un plan de marcado, ya sea global (asignado por defecto) o específicos del usuario. De forma predeterminada, todos los usuarios se asignan a una directiva de voz global y plan de marcado. Si ya hubiera una directiva de voz o un plan de marcado a nivel de sitio para el sitio en el que se hospeda la cuenta de usuario, dichas directivas se aplicarán automáticamente al usuario. Para aplicar una directiva de voz por usuario o plan a un usuario de marcado, debe ejecutar los cmdlets **Grant CsVoicePolicy** y **CsDialPlan de la concesión** . Para obtener más información, consulte los siguientes procedimientos de este tema.
## <a name="voice-policy-assignment"></a>Asignación de directivas de voz

Directivas de voz global y a nivel de sitio se asignan automáticamente a todas las cuentas de usuario habilitadas para Telefonía IP empresarial. También puede crear directivas de voz aplicables a usuarios o grupos específicos. Estas directivas por usuario deben estar explícitamente asignadas a los usuarios o grupos. Si desea utilizar el global o directiva de voz para todos los usuarios que están habilitados para Telefonía IP empresarial del sitio, puede omitir esta sección y continuar a la sección de [Asignación de Plan de marcado](enable-users-for-enterprise-voice.md#BKMK_DialPlanAssignment) más adelante en este tema.
  
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

    En este ejemplo, el usuario con el nombre para mostrar Bob Kelly se asigna la directiva de voz con el nombre **VoicePolicyJapan**.
    
## <a name="dial-plan-assignment"></a>Asignación de planes de marcado
<a name="BKMK_DialPlanAssignment"> </a>

Para completar la configuración de la cuenta de usuario para los usuarios de Telefonía IP empresarial o los usuarios de acceso telefónico de la conferencia, el usuario debe asignarse un plan de marcado. Las cuentas de usuario emplearán automáticamente el plan de marcado global o, si existe, el plan de marcado del sitio, en los casos en los que no se asigne explícitamente un plan de marcado creado particularmente para el usuario. Si desea utilizar el global o plan de marcado para todos los usuarios que están habilitados para Telefonía IP empresarial del sitio, puede omitir esta sección.
  
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

    En este ejemplo, el usuario con el nombre para mostrar Bob Kelly se asigna el plan de marcado del usuario con el nombre **DialPlanJapan**.
    

