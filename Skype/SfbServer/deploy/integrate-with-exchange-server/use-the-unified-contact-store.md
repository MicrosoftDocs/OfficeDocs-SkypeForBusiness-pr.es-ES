---
title: Configurar Skype Empresarial Server para usar el almacenamiento de contactos unificado
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 6aa17ae3-764e-4986-a900-85a3cdb8c1fc
description: 'Resumen: Configurar el almacén de contactos unificado para Exchange Server y Skype para Business Server.'
ms.openlocfilehash: fd58c0cfd86092bb1a6004ac4d70c98c51062ea1
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32216616"
---
# <a name="configure-skype-for-business-server-to-use-the-unified-contact-store"></a>Configurar Skype Empresarial Server para usar el almacenamiento de contactos unificado
 
**Resumen:** Configurar el almacén de contactos unificado para Exchange Server 2016 o Exchange Server 2013 y Skype para Business Server.
  
Con el almacén de contactos unificados, los usuarios mantienen una lista de contactos único y, a continuación, tienen los contactos disponibles en múltiples aplicaciones, incluidas Skype para la empresa, Microsoft Outlook 2013 y Microsoft Outlook Web App 2013. Al habilitar el almacén de contactos unificados para un usuario, que los contactos del usuario no se almacenan en Skype para Business Server y se recuperan según sea necesario. En su lugar, sus contactos se almacenan en Exchange Server 2016 o Exchange Server 2013 y se recuperan mediante el uso de servicios Web de Exchange.
  
> [!NOTE]
> Técnicamente, información de contacto se almacena en un par de carpetas que se encuentran en el buzón de Exchange del usuario. Los contactos a sí mismos se almacenan en una carpeta denominada Skype para contactos profesionales que es visible a los usuarios finales; metadatos sobre los contactos se almacenan en una subcarpeta que no es visible para los usuarios finales. 
  
## <a name="enabling-the-unified-contact-store-for-a-user"></a>Habilitar el almacén de contactos unificados de un usuario

Si ya está configurada la autenticación de servidor a servidor entre Skype para Business Server y Exchange Server, a continuación, también ha habilitado el almacén de contactos unificados; no se requiere ninguna configuración adicional del servidor. Sin embargo, se requiere configuración de la cuenta de usuario adicionales con el fin de mover los contactos de un usuario en el almacén de contactos unificados. De forma predeterminada, los contactos del usuario se conservan en Skype para Business Server y no en el almacén de contactos unificados.
  
Acceso al almacén de contactos unificados se administra mediante Skype para directivas de servicios del usuario de Business Server. Las directivas de servidor de usuario tienen una sola propiedad (UcsAllowed); Esta propiedad se utiliza para determinar la ubicación donde se almacenan los contactos del usuario. Si un usuario está administrado por una directiva de servicios de usuario donde UcsAllowed se ha establecido en True ($True), a continuación, los contactos del usuario se almacenará en el almacén de contactos unificados. Si el usuario está administrado por un usuario de servicios de directiva donde UcsAllowed se ha establecido en False ($False), a continuación, sus contactos se almacenará en Skype para Business Server.
  
Al instalar Skype para Business Server, se instala también una directiva de servicios de usuario único (configurada en el ámbito global). El valor UcsAllowed en esta directiva se define en True, lo que significa que, de manera predeterminada, los contactos de los usuarios se almacenarán en el almacén de contactos unificados (suponiendo que haya sido implementado y configurado). Si desea migrar todos los contactos de usuarios al almacén de contactos unificado, no tiene que hacer nada en absoluto. 
  
Si prefiere no migrar todos los contactos al almacén de contactos unificado, puede deshabilitar el almacén de contactos unificado para todos los usuarios definiendo la propiedad UcsAllowed de la directiva global en False:
  
```
Set-CsUserServicesPolicy -Identity global -UcsAllowed $False
```

Después de deshabilitar el almacén de contactos unificados en la directiva global, a continuación, puede crear una directiva por usuario que permite el uso del almacén de contactos unificados; Esto le permite tener algunos usuarios mantener sus contactos en el almacén de contactos unificados, mientras que otros usuarios continuarán mantener sus contactos en Skype para Business Server. Puede crear una directiva de servicios de usuario por usuario mediante el uso de un comando similar al siguiente:
  
```
New-CsUserServicesPolicy -Identity "AllowUnifiedContactStore" -UcsAllowed $True
```

Una vez creada la directiva, hay que asignarla a los usuarios que deban tener acceso al almacén de contactos unificados. Para ello, se usan comandos parecidos a los siguientes:
  
```
Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName "AllowUnifiedContactStore"
```

Después de que se ha asignado la directiva, Skype para Business Server va a comenzar a migrar los contactos del usuario al almacén de contactos unificado. Una vez finalizada la migración, el usuario tendrá sus contactos almacenados en Exchange, en lugar de Skype para Business Server. Si el usuario que ocurre con haber iniciado sesión en Lync 2013 en la migración de tiempo se complete, aparecerá un cuadro de mensaje y navegará le pedirá que cierre la sesión en Skype para la empresa y, a continuación, vuelva a iniciar sesión para poder finalizar el proceso. Los contactos de los usuarios a los que no se les asigne esta directiva por usuario no se migrarán al almacén de contactos unificados. Que es debido a que los usuarios se están administrando por la directiva global y uso del almacén de contactos unificados se ha deshabilitado en la directiva global.
  
Puede comprobar que los contactos de un usuario correctamente se han migrado al almacén de contactos unificado ejecutando el cmdlet [Test-CsUnifiedContactStore](https://docs.microsoft.com/powershell/module/skype/test-csunifiedcontactstore?view=skype-ps) desde dentro de la Skype para Shell de administración de servidor empresarial:
  
```
Test-CsUnifiedContactStore -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com"
```

Si Test-CsUnifiedContactStore se realiza correctamente que significa que los contactos para el usuario sip: kenmyer @<span></span>litwareinc<span></span>.com se han migrado al almacén de contactos unificados.
  
## <a name="rolling-back-the-unified-contact-store"></a>Revertir el almacén de datos unificados

Si necesita quitar contactos de un usuario desde el almacén de contactos unificados (por ejemplo, si el usuario necesita se vuelven a ubicar en Microsoft Lync Server 2010 y, por tanto, ya no puede usar el almacén de contactos unificados) debe hacer dos cosas. En primer lugar, debe asignar al usuario una nueva directiva de servicios de usuario, uno que prohíbe almacenar los contactos en el almacén de contactos unificados. (Es decir, una directiva donde la propiedad UcsAllowed ha sido establecido en $False.) Si no tiene una directiva de este tipo puede crear uno con un comando similar al siguiente:
  
```
New-CsUserServicesPolicy -Identity NoUnifiedContactStore -UcsAllowed $False
```

Después, puede usar un comando como el siguiente para asignar esta nueva directiva por usuario (NoUnifiedContactStore):
  
```
Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName NoUnifiedContactStore
```

Con el comando anterior la nueva directiva se asigna al usuario Ken Myer y, asimismo, se impide que los contactos de Ken migren al almacén de contactos unificados.
  
> [!NOTE]
> Algunas veces, se puede lograr el mismo efecto con tan solo quitar la directiva de servicios de usuario actual que el usuario tiene asignada. Imaginemos, por ejemplo, que Ken Myer tiene una directiva de servicios de usuario por usuario que permite el uso del almacén de contactos unificados, pero la directiva global prohíbe usarlo. En tal caso, se podría quitar la directiva de servicios de usuario que Ken tiene asignada. Al hacerlo, Ken pasará automáticamente a estar administrado por la directiva global y, en consecuencia, dejará de tener acceso al almacén de contactos unificados. Directiva de desasignar una le ha asignado previamente por usuario, use el mismo comando tal como se muestra antes de, pero esta vez establezca el parámetro PolicyName en un valor nulo: Grant-CsUserServicesPolicy-Identity "Ken Myer" - PolicyName $Null 
  
La terminología "impide que los contactos de Ken se migran al almacén de contactos unificado" es importante tener en cuenta al trabajar con el almacén de contactos unificados. Simplemente asignar Ken una nueva directiva de servicios de usuario no mover sus contactos fuera del almacén de contactos unificados. Cuando un usuario inicia sesión en Skype para Business Server, el sistema comprueba la directiva de servicios de usuario del usuario para ver si se deben conservar sus contactos en el almacén de contactos unificados. Si la respuesta es Sí (es decir, si la propiedad UcsAllowed está establecida en $True), a continuación, los contactos que se van a migrar al almacén de contactos unificado (suponiendo que los contactos no estén ya en el almacén de contactos unificados). Si la respuesta es no, a continuación, Skype para Business Server simplemente pasa por alto los contactos del usuario y se mueve en su siguiente tarea. Esto significa que Skype para Business Server no moverá automáticamente los contactos de un usuario fuera de almacén de contactos unificados, independientemente del valor de la propiedad UcsAllowed.
  
También significa que, después de asignar al usuario de una nueva directiva de servicios de usuario, debe, a continuación, ejecute el cmdlet [Invoke-CsUcsRollback](https://docs.microsoft.com/powershell/module/skype/invoke-csucsrollback?view=skype-ps) para mover los contactos del usuario fuera del servidor de Exchange y volver a Skype para Business Server. Por ejemplo, después de asignar a Ken Myer una nueva directiva de servicios de usuario, sus contactos se pueden sacar del almacén de contactos unificados con el siguiente comando:
  
```
Invoke-CsUcsRollback -Identity "Ken Myer"
```

Si se cambia la directiva de servicios de usuario, pero no se ejecuta el cmdlet Invoke-CsUcsRollback, los contactos de Ken no se eliminarán del almacén de contactos unificados. ¿Qué ocurriría si se ejecutara Invoke-CsUcsRollback sin modificar la directiva de servicios de usuario de Ken Myer? Pues que los contactos de Ken se eliminarán de manera temporal del almacén de contactos unificados. El hecho de que esta eliminación sea temporal es importante. Después de que se han quitado los contactos de Ken desde el almacén de contactos unificados, Skype para Business Server va a esperar 7 días y, a continuación, compruebe qué directiva de servicios de usuario se ha asignado a Ken. Si Ken sigue teniendo asignada una directiva que permite usar el almacén de contactos unificados, sus contactos se colocarán de nuevo en dicho almacén. Para eliminar contactos del almacén de contactos unificados de manera permanente, debe cambiar la directiva de servicios de usuario y, además, ejecutar el cmdlet Invoke-CsUcsRollback.
  
El número de variables que pueden afectar a la migración es enorme por lo que es difícil calcular cuánto tiempo llevará migrar completamente todas las cuentas al almacén de contactos unificados. Por regla general, la migración no tiene efecto de forma inmediata, aunque se migre un número pequeño de contactos, puede llevar 10 minutos o más completar el traspaso.
  

