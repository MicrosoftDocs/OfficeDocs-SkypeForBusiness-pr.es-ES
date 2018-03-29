---
title: Configurar Skype para Business Server 2015 utilizar el almacén de contactos unificado
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
description: 'Resumen: Configurar el almacén de contactos unificado para 2016 de Exchange Server o Exchange Server 2013 y Skype para Business Server 2015.'
ms.openlocfilehash: 479032425c8a3d2d66bd341f54908a071dd5480d
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="configure-skype-for-business-server-2015-to-use-the-unified-contact-store"></a>Configurar Skype para Business Server 2015 utilizar el almacén de contactos unificado
 
**Resumen:** Configurar el almacén de contactos unificado para 2016 de Exchange Server o Exchange Server 2013 y Skype para Business Server 2015.
  
Utiliza el almacén de contactos unificado, los usuarios mantienen una lista única de contactos y hacer que esos contactos disponibles en varias aplicaciones, incluyendo Skype para negocios, 2013 de Microsoft Outlook y Microsoft Outlook Web App 2013. Al habilitar el almacén de contactos unificado para un usuario, que los contactos del usuario no almacenados en Skype para Business Server 2015 y obtenidos según sea necesario. En su lugar, sus contactos se almacenan en 2016 de Exchange Server o Exchange Server 2013 y se recuperan mediante los servicios Web Exchange.
  
> [!NOTE]
> Técnicamente, la información de contacto se almacena en un par de carpetas que se encuentran en el buzón de Exchange del usuario. Los contactos sí se almacenan en una carpeta denominada Skype para contactos de negocios que es visible para los usuarios finales; metadatos sobre los contactos se almacenan en una subcarpeta que no es visible para los usuarios finales. 
  
## <a name="enabling-the-unified-contact-store-for-a-user"></a>Habilitar el almacén de contactos unificados de un usuario

Si ya está configurada la autenticación de servidor a servidor entre Skype para Business Server 2015 y 2016 de Exchange Server o Exchange Server 2013, entonces también ha habilitado el almacén de contactos unificado; no se requiere ninguna configuración adicional del servidor. Sin embargo, configuración de la cuenta de usuario adicional es necesario para mover los contactos de un usuario en el almacén de contactos unificado. De forma predeterminada, los contactos de los usuarios se mantienen en Skype para Business Server y no en el almacén de contactos unificado.
  
Acceso al almacén de contactos unificado se administra mediante Skype para directivas de servicios del usuario de Business Server. Las directivas de servidor de usuario tienen una sola propiedad (UcsAllowed); Esta propiedad se utiliza para determinar la ubicación donde se almacenan los contactos de un usuario. Si un usuario es administrado por una directiva de servicios de usuario donde UcsAllowed está establecido en True ($True) se almacenarán los contactos del usuario en el almacén de contactos unificado. Si el usuario es administrado por un usuario de servicios de directiva donde UcsAllowed se ha establecido en False ($False) entonces sus contactos se almacenará en Skype para Business Server.
  
Al instalar Skype para Business Server, se instala también una directiva de servicios de usuario (configurada en el ámbito global). El valor UcsAllowed en esta directiva se define en True, lo que significa que, de manera predeterminada, los contactos de los usuarios se almacenarán en el almacén de contactos unificados (suponiendo que haya sido implementado y configurado). Si desea migrar todos los contactos de usuarios al almacén de contactos unificado, no tiene que hacer nada en absoluto. 
  
Si prefiere no migrar todos los contactos al almacén de contactos unificado, puede deshabilitar el almacén de contactos unificado para todos los usuarios definiendo la propiedad UcsAllowed de la directiva global en False:
  
```
Set-CsUserServicesPolicy -Identity global -UcsAllowed $False
```

Después de deshabilitar el almacén de contactos unificado en la directiva global, a continuación, puede crear una directiva por usuario que permite el uso del almacén de contactos unificado; Esto le permite tener algunos usuarios mantener sus contactos en el almacén de contactos unificado mientras otros usuarios continuarán manteniendo sus contactos en Skype para Business Server. Puede crear una directiva de servicios de usuario por usuario con un comando similar al siguiente:
  
```
New-CsUserServicesPolicy -Identity "AllowUnifiedContactStore" -UcsAllowed $True
```

Una vez creada la directiva, hay que asignarla a los usuarios que deban tener acceso al almacén de contactos unificados. Para ello, se usan comandos parecidos a los siguientes:
  
```
Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName "AllowUnifiedContactStore"
```

Una vez que se ha asignado la directiva, Skype para Business Server empezará a migrar los contactos del usuario al almacén de contactos unificado. Una vez completada la migración, el usuario tendrá sus contactos almacenados en Exchange en lugar de Skype para Business Server. Si da la casualidad de que el usuario inició la sesión en Lync en 2013 en la migración de tiempo finalice, aparecerá un cuadro de mensaje y él o ella le pedirá que cierre la sesión en Skype para el negocio y, a continuación, vuelva a iniciar sesión para poder finalizar el proceso. Los contactos de los usuarios a los que no se les asigne esta directiva por usuario no se migrarán al almacén de contactos unificados. Eso es porque la directiva global administra los usuarios y el uso del almacén de contactos unificado se ha deshabilitado en la directiva global.
  
Puede comprobar que los contactos de un usuario correctamente han migrado al almacén de contactos unificado ejecutando el cmdlet [Test-CsUnifiedContactStore](https://docs.microsoft.com/powershell/module/skype/test-csunifiedcontactstore?view=skype-ps) desde dentro el Skype para el Shell de administración de servidor empresarial:
  
```
Test-CsUnifiedContactStore -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com"
```

Si Test-CsUnifiedContactStore finaliza correctamente, querrá decir que los contactos del usuario sip:kenmyer@litwareinc.com se han migrado correctamente al almacén de contactos unificados.
  
## <a name="rolling-back-the-unified-contact-store"></a>Revertir el almacén de datos unificados

Si necesita quitar contactos de un usuario desde el almacén de contactos unificado (por ejemplo, si el usuario necesita se vuelven a ubicar en Microsoft Lync Server 2010 y, por tanto, ya no puede utilizar el almacén de contactos unificado) debe hacer dos cosas. En primer lugar, debe asignar al usuario una nueva directiva de servicios de usuario, que prohíbe almacenar contactos en el almacén de contactos unificado. (Es decir, una directiva donde la propiedad UcsAllowed ha sido establecido en $False.) Si no tiene esa política puede crear uno mediante un comando similar al siguiente:
  
```
New-CsUserServicesPolicy -Identity NoUnifiedContactStore -UcsAllowed $False
```

Después, puede usar un comando como el siguiente para asignar esta nueva directiva por usuario (NoUnifiedContactStore):
  
```
Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName NoUnifiedContactStore
```

Con el comando anterior la nueva directiva se asigna al usuario Ken Myer y, asimismo, se impide que los contactos de Ken migren al almacén de contactos unificados.
  
> [!NOTE]
> Algunas veces, se puede lograr el mismo efecto con tan solo quitar la directiva de servicios de usuario actual que el usuario tiene asignada. Imaginemos, por ejemplo, que Ken Myer tiene una directiva de servicios de usuario por usuario que permite el uso del almacén de contactos unificados, pero la directiva global prohíbe usarlo. En tal caso, se podría quitar la directiva de servicios de usuario que Ken tiene asignada. Al hacerlo, Ken pasará automáticamente a estar administrado por la directiva global y, en consecuencia, dejará de tener acceso al almacén de contactos unificados. Directiva de desasignar asignado previamente por usuario, utilice el mismo comando, como se muestra antes, pero esta vez establece el parámetro PolicyName en un valor nulo: Grant CsUserServicesPolicy-identidad "Ken Myer" - PolicyName $Null 
  
Es importante tener en cuenta al trabajar con el almacén de contactos unificado la terminología "impide que los contactos de Ken migran al almacén de contactos unificado". Simplemente asignando Ken una nueva directiva de servicios de usuario no moverá sus contactos fuera del almacén de contactos unificado. Cuando un usuario inicia sesión en Skype para Business Server, el sistema comprueba la directiva de servicios de usuario del usuario para ver si sus contactos deben conservarse en el almacén de contactos unificado. Si la respuesta es Sí (es decir, si la propiedad UcsAllowed se establece en $True) esos contactos se migrarán al almacén de contactos unificado (suponiendo que los contactos no estén ya en el almacén de contactos unificado). Si la respuesta es no, entonces Skype para Business Server simplemente omite los contactos del usuario y pasa a su siguiente tarea. Esto significa que Skype para Business Server no moverá automáticamente los contactos de un usuario fuera el almacén de contactos unificado, independientemente del valor de la propiedad UcsAllowed.
  
Eso también significa que, después de asignar al usuario una nueva directiva de servicios de usuario, debe, a continuación, ejecutar el cmdlet [Invoke-CsUcsRollback](https://docs.microsoft.com/powershell/module/skype/invoke-csucsrollback?view=skype-ps) para mover los contactos del usuario de Exchange Server y volver a Skype para Business Server. Por ejemplo, después de asignar a Ken Myer una nueva directiva de servicios de usuario, sus contactos se pueden sacar del almacén de contactos unificados con el siguiente comando:
  
```
Invoke-CsUcsRollback -Identity "Ken Myer"
```

Si se cambia la directiva de servicios de usuario, pero no se ejecuta el cmdlet Invoke-CsUcsRollback, los contactos de Ken no se eliminarán del almacén de contactos unificados. ¿Qué ocurriría si se ejecutara Invoke-CsUcsRollback sin modificar la directiva de servicios de usuario de Ken Myer? Pues que los contactos de Ken se eliminarán de manera temporal del almacén de contactos unificados. El hecho de que esta eliminación sea temporal es importante. Después de que se han quitado los contactos de Ken desde el almacén de contactos unificado, Skype para Business Server esperará 7 días y a continuación, compruebe la directiva de servicios de usuario ha sido asignada a Ken. Si Ken sigue teniendo asignada una directiva que permite usar el almacén de contactos unificados, sus contactos se colocarán de nuevo en dicho almacén. Para eliminar contactos del almacén de contactos unificados de manera permanente, debe cambiar la directiva de servicios de usuario y, además, ejecutar el cmdlet Invoke-CsUcsRollback.
  
El número de variables que pueden afectar a la migración es enorme por lo que es difícil calcular cuánto tiempo llevará migrar completamente todas las cuentas al almacén de contactos unificados. Por regla general, la migración no tiene efecto de forma inmediata, aunque se migre un número pequeño de contactos, puede llevar 10 minutos o más completar el traspaso.
  

