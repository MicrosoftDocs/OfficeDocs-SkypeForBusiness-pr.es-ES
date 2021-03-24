---
title: Configurar Skype Empresarial Server para usar el almacén de contactos unificado
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/7/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 6aa17ae3-764e-4986-a900-85a3cdb8c1fc
description: 'Resumen: configure el almacén de contactos unificado para Exchange Server y Skype Empresarial Server.'
ms.openlocfilehash: 9d9601e7a060b6d93a27e872bf05f798d470aa85
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095994"
---
# <a name="configure-skype-for-business-server-to-use-the-unified-contact-store"></a>Configurar Skype Empresarial Server para usar el almacén de contactos unificado
 
**Resumen:** Configure el almacén de contactos unificado para Exchange Server 2016 o Exchange Server 2013 y Skype Empresarial Server.
  
Con el almacén de contactos unificado, los usuarios mantienen una única lista de contactos y, a continuación, tienen esos contactos disponibles en varias aplicaciones, como Skype Empresarial, Microsoft Outlook 2013 y Microsoft Outlook Web App 2013. Cuando habilita el almacén de contactos unificado para un usuario, los contactos de ese usuario no se almacenan en Skype Empresarial Server y se recuperan según sea necesario. En su lugar, sus contactos se almacenan en Exchange Server 2016 o Exchange Server 2013 y se recuperan mediante servicios web de Exchange.
  
> [!NOTE]
> Técnicamente, la información de contacto se almacena en un par de carpetas que se encuentran en el buzón de Exchange del usuario. Los propios contactos se almacenan en una carpeta denominada Contactos de Skype Empresarial que es visible para los usuarios finales; los metadatos sobre los contactos se almacenan en una subcarpeta que no es visible para los usuarios finales. 
  
## <a name="enabling-the-unified-contact-store-for-a-user"></a>Habilitar el almacén de contactos unificados de un usuario

Si la autenticación de servidor a servidor entre Skype Empresarial Server y Exchange Server ya está configurada, también ha habilitado el almacén de contactos unificado; no se requiere ninguna configuración de servidor adicional. Sin embargo, se requiere una configuración de cuenta de usuario adicional para mover los contactos de un usuario al almacén de contactos unificado. De forma predeterminada, los contactos de usuario se mantienen en Skype Empresarial Server y no en el almacén de contactos unificado.
  
El acceso al almacén de contactos unificado se administra mediante directivas de servicios de usuario de Skype Empresarial Server. Las directivas de servidor de usuario solo tienen una sola propiedad (UcsAllowed); esta propiedad se usa para determinar la ubicación donde se almacenan los contactos de un usuario. Si un usuario está administrado por una directiva de servicios de usuario donde UcsAllowed se ha establecido en True ($True), los contactos del usuario se almacenarán en el almacén de contactos unificado. Si el usuario está administrado por una directiva de servicios de usuario donde UcsAllowed se ha establecido en False ($False), sus contactos se almacenarán en Skype Empresarial Server.
  
Al instalar Skype Empresarial Server, también se instala una directiva de servicios de usuario único (configurada en el ámbito global). El valor UcsAllowed de esta directiva se establece en True, lo que significa que, de forma predeterminada, los contactos de usuario se almacenarán en el almacén de contactos unificado (suponiendo que se haya implementado y configurado). Si quieres migrar todos los contactos de usuario al almacén de contactos unificado, no tienes que hacer nada en absoluto. 
  
Si prefiere no migrar todos los contactos al almacén de contactos unificado, puede deshabilitar el almacén de contactos unificado para todos los usuarios estableciendo la propiedad UcsAllowed en la directiva global en False:
  
```powershell
Set-CsUserServicesPolicy -Identity global -UcsAllowed $False
```

Después de deshabilitar el almacén de contactos unificado en la directiva global, puede crear una directiva por usuario que permita el uso del almacén de contactos unificado; esto permite que algunos usuarios conserven sus contactos en el almacén de contactos unificado, mientras que otros usuarios siguen manteniendo sus contactos en Skype Empresarial Server. Para crear una directiva de servicios de usuario por usuario se usa un comando parecido al siguiente:
  
```powershell
New-CsUserServicesPolicy -Identity "AllowUnifiedContactStore" -UcsAllowed $True
```

Una vez creada la directiva, hay que asignarla a los usuarios que deban tener acceso al almacén de contactos unificados. Para ello, se usan comandos parecidos a los siguientes:
  
```powershell
Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName "AllowUnifiedContactStore"
```

Una vez asignada la directiva, Skype Empresarial Server empezará a migrar los contactos del usuario al almacén de contactos unificado. Una vez completada la migración, el usuario tendrá sus contactos almacenados en Exchange en lugar de Skype Empresarial Server. Si el usuario inicia sesión en Lync 2013 al finalizar la migración, aparecerá un cuadro de mensaje y se le pedirá que cierre sesión en Skype Empresarial y vuelva a iniciar sesión para finalizar el proceso. Los usuarios que no hayan sido asignados a esta directiva por usuario no tendrán sus contactos migrados al almacén de contactos unificado. Esto se debe a que la directiva global administra a esos usuarios y el uso del almacén de contactos unificado se ha deshabilitado en la directiva global.
  
Puede comprobar que los contactos de un usuario se han migrado correctamente al almacén de contactos unificado ejecutando el cmdlet [Test-CsUnifiedContactStore](/powershell/module/skype/test-csunifiedcontactstore?view=skype-ps) desde el Shell de administración de Skype Empresarial Server:
  
```powershell
Test-CsUnifiedContactStore -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com"
```

Si Test-CsUnifiedContactStore correctamente, significa que los contactos del usuario sip:kenmyer@ litwareinc .com se han migrado al almacén de <span></span> <span></span> contactos unificado.
  
## <a name="rolling-back-the-unified-contact-store"></a>Revertir el almacén de datos unificados

Si necesita quitar los contactos de un usuario del almacén de contactos unificado (por ejemplo, si el usuario necesita volver a instalarse en Microsoft Lync Server 2010 y, por lo tanto, ya no puede usar el almacén de contactos unificado), debe hacer dos cosas. En primer lugar, debe asignar al usuario una nueva directiva de servicios de usuario, una que prohíba almacenar contactos en el almacén de contactos unificado. (Es decir, una directiva donde la propiedad UcsAllowed se ha establecido en $False). Si no tiene una directiva de este tipo, puede crear una con un comando similar a este:
  
```powershell
New-CsUserServicesPolicy -Identity NoUnifiedContactStore -UcsAllowed $False
```

Después, puede usar un comando como el siguiente para asignar esta nueva directiva por usuario (NoUnifiedContactStore):
  
```powershell
Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName NoUnifiedContactStore
```

Con el comando anterior la nueva directiva se asigna al usuario Ken Myer y, asimismo, se impide que los contactos de Ken migren al almacén de contactos unificados.
  
> [!NOTE]
> En algunos casos, puede lograr el mismo efecto neto simplemente desasignando la directiva de servicios de usuario actual del usuario. Imaginemos, por ejemplo, que Ken Myer tiene una directiva de servicios de usuario por usuario que permite el uso del almacén de contactos unificados, pero la directiva global prohíbe usarlo. En ese caso, podría deshacer la asignación de la directiva de servicios por usuario de Ken. Al hacerlo, Ken pasará automáticamente a estar administrado por la directiva global y, en consecuencia, dejará de tener acceso al almacén de contactos unificados. Para anular la asignación de una directiva por usuario asignada anteriormente, use el mismo comando que se muestra anteriormente, pero esta vez establezca el parámetro PolicyName en un valor nulo: Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName $Null 
  
La terminología "impide que los contactos de Ken se migren al almacén de contactos unificado" es importante tener en cuenta al trabajar con el almacén de contactos unificado. Simplemente asignar a Ken una nueva directiva de servicios de usuario no moverá sus contactos fuera del almacén de contactos unificado. Cuando un usuario inicia sesión en Skype Empresarial Server, el sistema comprueba la directiva de servicios de usuario del usuario para ver si sus contactos deben mantenerse en el almacén de contactos unificado. Si la respuesta es sí (es decir, si la propiedad UcsAllowed está establecida en $True), esos contactos se migrarán al almacén de contactos unificado (suponiendo que esos contactos no estén ya en el almacén de contactos unificado). Si la respuesta es no, Skype Empresarial Server simplemente omite los contactos del usuario y pasa a su siguiente tarea. Esto significa que Skype Empresarial Server no moverá automáticamente los contactos de un usuario desde fuera del almacén de contactos unificado, independientemente del valor de la propiedad UcsAllowed.
  
Esto también significa que, después de asignar al usuario una nueva directiva de servicios de usuario, debe ejecutar el cmdlet [Invoke-CsUcsRollback](/powershell/module/skype/invoke-csucsrollback?view=skype-ps) para mover los contactos del usuario fuera de Exchange Server y volver a Skype Empresarial Server. Por ejemplo, después de asignar a Ken Myer una nueva directiva de servicios de usuario, sus contactos se pueden sacar del almacén de contactos unificados con el siguiente comando:
  
```powershell
Invoke-CsUcsRollback -Identity "Ken Myer"
```

Si se cambia la directiva de servicios de usuario, pero no se ejecuta el cmdlet Invoke-CsUcsRollback, los contactos de Ken no se eliminarán del almacén de contactos unificados. ¿Qué ocurriría si se ejecutara Invoke-CsUcsRollback sin modificar la directiva de servicios de usuario de Ken Myer? Pues que los contactos de Ken se eliminarán de manera temporal del almacén de contactos unificados. El hecho de que esta eliminación sea temporal es importante. Después de quitar los contactos de Ken del almacén de contactos unificado, Skype Empresarial Server esperará 7 días y, a continuación, comprobará qué directiva de servicios de usuario se asignó a Ken. Si Ken sigue teniendo asignada una directiva que permite usar el almacén de contactos unificados, sus contactos se colocarán de nuevo en dicho almacén. Para eliminar contactos del almacén de contactos unificados de manera permanente, debe cambiar la directiva de servicios de usuario y, además, ejecutar el cmdlet Invoke-CsUcsRollback.
  
Debido al gran número de variables que pueden afectar a la migración, es difícil calcular cuánto tiempo llevará antes de que las cuentas se migren completamente al almacén de contactos unificado. Sin embargo, como regla general, la migración no tiene efecto inmediatamente: incluso cuando se migra un número reducido de contactos, puede tardar 10 minutos o más antes de que se complete el movimiento.
