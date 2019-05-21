---
title: Configurar Skype Empresarial Server para usar el almacenamiento de contactos unificado
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/7/2018
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 6aa17ae3-764e-4986-a900-85a3cdb8c1fc
description: 'Resumen: configure el almacén de contactos unificado para Exchange Server y Skype empresarial Server.'
ms.openlocfilehash: fd70c4b0b3d94ba26b76847ff053bf33d5902799
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34278045"
---
# <a name="configure-skype-for-business-server-to-use-the-unified-contact-store"></a>Configurar Skype Empresarial Server para usar el almacenamiento de contactos unificado
 
**Resumen:** Configure el almacén de contactos unificado para Exchange Server 2016 o Exchange Server 2013 y Skype empresarial Server.
  
Con el almacén de contactos unificado, los usuarios mantienen una única lista de contactos y, después, tienen esos contactos disponibles en varias aplicaciones, entre las que se incluyen Skype empresarial, Microsoft Outlook 2013 y Microsoft Outlook Web App 2013. Al habilitar el almacén de contactos unificado para un usuario, los contactos de ese usuario no se almacenan en Skype empresarial Server y se recuperan según sea necesario. En su lugar, sus contactos se almacenan en Exchange Server 2016 o Exchange Server 2013 y se recuperan mediante servicios Web de Exchange.
  
> [!NOTE]
> Técnicamente, la información de contacto se almacena en un par de carpetas que se encuentran en el buzón de Exchange del usuario. Los contactos en sí se almacenan en una carpeta llamada contactos de Skype para empresas, que es visible para los usuarios finales. los metadatos sobre los contactos se almacenan en una subcarpeta que no es visible para los usuarios finales. 
  
## <a name="enabling-the-unified-contact-store-for-a-user"></a>Habilitar el almacén de contactos unificados de un usuario

Si la autenticación de servidor a servidor entre Skype empresarial Server y Exchange Server ya está configurada, también habrá habilitado el almacén de contactos unificado. no es necesaria ninguna configuración adicional del servidor. Sin embargo, se requiere una configuración de cuenta de usuario adicional para mover los contactos de un usuario al almacén de contactos unificado. De forma predeterminada, los contactos de usuario se guardan en Skype empresarial Server y no en el almacén de contactos unificado.
  
El acceso al almacén de contactos unificado se administra mediante las directivas de servicios de usuario de Skype empresarial Server. Las directivas de servidor de usuario solo tienen una única propiedad (UcsAllowed); Esta propiedad se usa para determinar la ubicación en la que se almacenan los contactos de un usuario. Si un usuario es administrado por una directiva de servicios de usuario donde UcsAllowed se ha establecido en verdadero ($True), los contactos del usuario se almacenarán en el almacén de contactos unificado. Si el usuario es administrado por una directiva de servicios de usuario donde UcsAllowed se ha configurado como falso ($False), sus contactos se almacenarán en Skype empresarial Server.
  
Al instalar Skype empresarial Server, también se instala una única directiva de servicios de usuario (configurada en el ámbito global). El valor UcsAllowed en esta directiva se define en True, lo que significa que, de manera predeterminada, los contactos de los usuarios se almacenarán en el almacén de contactos unificados (suponiendo que haya sido implementado y configurado). Si desea migrar todos los contactos de usuarios al almacén de contactos unificado, no tiene que hacer nada en absoluto. 
  
Si prefiere no migrar todos los contactos al almacén de contactos unificado, puede deshabilitar el almacén de contactos unificado para todos los usuarios definiendo la propiedad UcsAllowed de la directiva global en False:
  
```
Set-CsUserServicesPolicy -Identity global -UcsAllowed $False
```

Después de deshabilitar el almacén de contactos unificado en la directiva global, puede crear una directiva por usuario que permita el uso del almacenamiento de contactos unificado. Esto le permite a algunos usuarios mantener sus contactos en el almacén de contactos unificado mientras otros usuarios continúan manteniendo sus contactos en Skype empresarial Server. Puede crear una directiva de servicios de usuario por usuario usando un comando similar a este:
  
```
New-CsUserServicesPolicy -Identity "AllowUnifiedContactStore" -UcsAllowed $True
```

Una vez creada la directiva, hay que asignarla a los usuarios que deban tener acceso al almacén de contactos unificados. Para ello, se usan comandos parecidos a los siguientes:
  
```
Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName "AllowUnifiedContactStore"
```

Después de asignar la Directiva, Skype empresarial Server comenzará a migrar los contactos del usuario al almacén de contactos unificado. Una vez completada la migración, el usuario tendrá sus contactos almacenados en Exchange en lugar de en Skype empresarial Server. Si el usuario ha iniciado sesión en Lync 2013 en el momento en que se completa la migración, aparecerá un cuadro de mensaje y se le solicitará que cierre sesión en Skype empresarial y, a continuación, inicie sesión de nuevo para finalizar el proceso. Los contactos de los usuarios a los que no se les asigne esta directiva por usuario no se migrarán al almacén de contactos unificados. Esto se debe a que los usuarios están siendo administrados por la directiva global y el uso del almacén de contactos unificado se ha deshabilitado en la directiva global.
  
Puede comprobar que los contactos de un usuario se han migrado correctamente al almacén de contactos unificado ejecutando el cmdlet [Test-CsUnifiedContactStore](https://docs.microsoft.com/powershell/module/skype/test-csunifiedcontactstore?view=skype-ps) desde el shell de administración de Skype empresarial Server:
  
```
Test-CsUnifiedContactStore -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com"
```

Si prueba-CsUnifiedContactStore se ejecuta correctamente, significa que los contactos para el SIP del usuario:<span></span>kenmyer<span></span>@ litwareinc. com se han migrado al almacén de contactos unificado.
  
## <a name="rolling-back-the-unified-contact-store"></a>Revertir el almacén de datos unificados

Si necesita quitar los contactos de un usuario del almacén de contactos unificado (por ejemplo, si el usuario necesita volver a usarse en Microsoft Lync Server 2010 y, por lo tanto, ya no puede usar el almacén de contactos unificado), debe hacer dos cosas. En primer lugar, debe asignar al usuario una nueva Directiva de servicios de usuario, una que prohíba almacenar contactos en el almacén de contactos unificado. (Es decir, una directiva en la que la propiedad UcsAllowed se ha establecido en $False). Si no tiene una directiva de ese tipo, puede crear una usando un comando similar a este:
  
```
New-CsUserServicesPolicy -Identity NoUnifiedContactStore -UcsAllowed $False
```

Después, puede usar un comando como el siguiente para asignar esta nueva directiva por usuario (NoUnifiedContactStore):
  
```
Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName NoUnifiedContactStore
```

Con el comando anterior la nueva directiva se asigna al usuario Ken Myer y, asimismo, se impide que los contactos de Ken migren al almacén de contactos unificados.
  
> [!NOTE]
> Algunas veces, se puede lograr el mismo efecto con tan solo quitar la directiva de servicios de usuario actual que el usuario tiene asignada. Imaginemos, por ejemplo, que Ken Myer tiene una directiva de servicios de usuario por usuario que permite el uso del almacén de contactos unificados, pero la directiva global prohíbe usarlo. En tal caso, se podría quitar la directiva de servicios de usuario que Ken tiene asignada. Al hacerlo, Ken pasará automáticamente a estar administrado por la directiva global y, en consecuencia, dejará de tener acceso al almacén de contactos unificados. Para cancelar la asignación de una directiva por usuario asignada anteriormente, use el mismo comando que se mostró anteriormente, pero esta vez establezca el parámetro PolicyName en un valor nulo: Grant-CsUserServicesPolicy-Identity "Ken Myer"-PolicyName $Null 
  
La terminología "impide que los contactos de Ken se migren al almacén de contactos unificado" es importante para tener en cuenta al trabajar con el almacenamiento de contactos unificado. Simplemente asignar a Ken una nueva Directiva de servicios de usuario no moverá a sus contactos del almacén de contactos unificado. Cuando un usuario inicia sesión en Skype empresarial Server, el sistema comprueba la Directiva de servicios de usuario del usuario para ver si sus contactos deben conservarse en el almacén de contactos unificado. Si la respuesta es afirmativa (es decir, si la propiedad UcsAllowed se establece en $True), esos contactos se migrarán al almacén de contactos unificado (suponiendo que esos contactos aún no estén en el almacén de contactos unificado). Si la respuesta es no, Skype empresarial Server simplemente pasa por alto los contactos del usuario y pasa a la siguiente tarea. Eso significa que Skype empresarial Server no moverá automáticamente los contactos de un usuario del almacén de contactos unificado, independientemente del valor de la propiedad UcsAllowed.
  
Eso también significa que, después de asignar al usuario una nueva Directiva de servicios de usuario, debe ejecutar el cmdlet [Invoke-CsUcsRollback](https://docs.microsoft.com/powershell/module/skype/invoke-csucsrollback?view=skype-ps) para mover los contactos del usuario fuera de Exchange Server y volver a Skype empresarial Server. Por ejemplo, después de asignar a Ken Myer una nueva directiva de servicios de usuario, sus contactos se pueden sacar del almacén de contactos unificados con el siguiente comando:
  
```
Invoke-CsUcsRollback -Identity "Ken Myer"
```

Si se cambia la directiva de servicios de usuario, pero no se ejecuta el cmdlet Invoke-CsUcsRollback, los contactos de Ken no se eliminarán del almacén de contactos unificados. ¿Qué ocurriría si se ejecutara Invoke-CsUcsRollback sin modificar la directiva de servicios de usuario de Ken Myer? Pues que los contactos de Ken se eliminarán de manera temporal del almacén de contactos unificados. El hecho de que esta eliminación sea temporal es importante. Una vez que los contactos de Ken hayan sido eliminados del almacén de contactos unificado, Skype empresarial Server esperará 7 días y, a continuación, verificará qué política de servicios de usuario ha sido asignada a Ken. Si Ken sigue teniendo asignada una directiva que permite usar el almacén de contactos unificados, sus contactos se colocarán de nuevo en dicho almacén. Para eliminar contactos del almacén de contactos unificados de manera permanente, debe cambiar la directiva de servicios de usuario y, además, ejecutar el cmdlet Invoke-CsUcsRollback.
  
El número de variables que pueden afectar a la migración es enorme por lo que es difícil calcular cuánto tiempo llevará migrar completamente todas las cuentas al almacén de contactos unificados. Por regla general, la migración no tiene efecto de forma inmediata, aunque se migre un número pequeño de contactos, puede llevar 10 minutos o más completar el traspaso.
  

