---
title: "Configuración de MS Lync Server 2013 para usar el almacén de contactos unificado"
TOCTitle: "Conf. de Microsoft Lync Server 2013 pour l’util. du magasin de contact unifié"
ms:assetid: 6aa17ae3-764e-4986-a900-85a3cdb8c1fc
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ688083(v=OCS.15)
ms:contentKeyID: 49889217
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuración de Microsoft Lync Server 2013 para usar el almacén de contactos unificado

 

_**Última modificación del tema:** 2014-02-07_

Gracias al almacén de contactos unificados, los usuarios pueden tener una sola lista de contactos que, además. pueden poner disponible en diversas aplicaciones, como Microsoft Lync 2013, Microsoft Outlook 2013 y Microsoft Outlook Web App 2013. Cuando el almacén de contactos unificados de un usuario se habilita, sus contactos no se almacenan en Microsoft Lync Server 2013 y se recuperan mediante el protocolo SIP, sino que se almacenan en Microsoft Exchange Server 2013 y se recuperan mediante los servicios Web Exchange.


> [!NOTE]
> Técnicamente, la información de contacto se almacena en dos carpetas del buzón de Exchange 2013 del usuario. Los contactos en sí se almacenan en una carpeta de contactos de Lync, que está visible para los usuarios finales, mientras que los metadatos sobre los contactos se almacenan en una subcarpeta y no están visibles.



## Habilitar el almacén de contactos unificados de un usuario

Si ha configurado la autenticación de servidor a servidor entre Lync Server 2013 y Exchange 2013, podrá usar el almacén de contactos unificados sin necesidad de más configuraciones de servidor. No obstante, sí que es necesario configurar la cuenta de usuario para mover los contactos de un usuario al almacén de contactos unificados, dado que los contactos de un usuario se conservan de forma predeterminada en Lync Server, no en el almacén de contactos unificados.

El acceso al almacén de contactos unificados se administra mediante directivas de servicios de usuario de Lync Server. Estas directivas poseen únicamente una propiedad (UcsAllowed), que sirve para saber dónde se encuentran los contactos de un usuario. Si un usuario se administra mediante una directiva de servicios de usuario en la que UcsAllowed se ha establecido en True ($True), sus contactos se almacenarán en el almacén de contactos unificados y, si UcsAllowed está establecido en False ($False), estarán en Lync Server.

Cuando Lync Server 2013 se instala, también lo hace una directiva única de servicios de usuario (configurada en el ámbito global). El valor UcsAllowed en esta directiva se define en True, lo que significa que, de manera predeterminada, los contactos de los usuarios se almacenarán en el almacén de contactos unificados (suponiendo que haya sido implementado y configurado). Si desea migrar todos los contactos de usuarios al almacén de contactos unificado, no tiene que hacer nada en absoluto.

Si prefiere no migrar todos los contactos al almacén de contactos unificado, puede deshabilitar el almacén de contactos unificado para todos los usuarios definiendo la propiedad UcsAllowed de la directiva global en False:

    Set-CsUserServicesPolicy -Identity global -UcsAllowed $False

Cuando haya deshabilitado el almacén de contactos unificado en la directiva global, puede crear una directiva para cada usuario que habilite el uso del almacén de contactos unificados. De este modo puede hacer que algunos usuarios mantengan sus contactos en el almacén de contactos unificados y otros continúen manteniendo sus contactos en Lync Server. Puede crear una directiva de servicios de usuario por usuario usando un comando similar al siguiente:

    New-CsUserServicesPolicy -Identity "AllowUnifiedContactStore" -UcsAllowed $True

Una vez creada la directiva, hay que asignarla a los usuarios que deban tener acceso al almacén de contactos unificados. Para ello, se usan comandos parecidos a los siguientes:

    Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName "AllowUnifiedContactStore"

Tras asignar la directiva, Lync Server comenzará a migrar los contactos del usuario al almacén de contactos unificados. Una vez terminada la migración, el usuario tendrá sus contactos guardados en Exchange, en lugar de Lync Server. Si coincidiera que el usuario tuviera la sesión iniciada en Lync 2013 en el momento en que concluye la migración, se mostrará un cuadro de mensaje donde se le pedirá que cierre la sesión de Lync y vuelva a iniciarla para poder finalizar el proceso. Los contactos de los usuarios a los que no se les asigne esta directiva por usuario no se migrarán al almacén de contactos unificados. Esto se debe a que estos usuarios se gestionan mediante la directiva global y el uso de un almacén de contactos unificados se ha deshabilitado en la directiva global.

Para confirmar que los contactos de un usuario se han migrado correctamente al almacén de contactos unificados, hay que ejecutar el cmdlet [Test-CsUnifiedContactStore](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsUnifiedContactStore) desde el Shell de administración de Lync Server:

    Test-CsUnifiedContactStore -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com"

Si Test-CsUnifiedContactStore finaliza correctamente, querrá decir que los contactos del usuario sip:kenmyer@litwareinc.com se han migrado correctamente al almacén de contactos unificados.

## Revertir el almacén de datos unificados

Si necesita quitar los contactos de un usuario del almacén de contactos unificados (porque dicho usuario deba volver a hospedarse en Microsoft Lync Server 2010 y ya no pueda usar el almacén), puede hacer dos cosas. Primero, debe asignar al usuario una nueva directiva de servicios de usuario que prohíba almacenar contactos en el almacén de contactos unificados (en otras palabras, una directiva en la que la propiedad UcsAllowed esté establecida en $False). Si no posee una directiva de estas características, puede crear una con un comando parecido al siguiente:

    New-CsUserServicesPolicy -Identity NoUnifiedContactStore -UcsAllowed $False

Después, puede usar un comando como el siguiente para asignar esta nueva directiva por usuario (NoUnifiedContactStore):

    Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName NoUnifiedContactStore

Con el comando anterior la nueva directiva se asigna al usuario Ken Myer y, asimismo, se impide que los contactos de Ken migren al almacén de contactos unificados.


> [!NOTE]
> Algunas veces, se puede lograr el mismo efecto con tan solo quitar la directiva de servicios de usuario actual que el usuario tiene asignada. Imaginemos, por ejemplo, que Ken Myer tiene una directiva de servicios de usuario por usuario que permite el uso del almacén de contactos unificados, pero la directiva global prohíbe usarlo. En tal caso, se podría quitar la directiva de servicios de usuario que Ken tiene asignada. Al hacerlo, Ken pasará automáticamente a estar administrado por la directiva global y, en consecuencia, dejará de tener acceso al almacén de contactos unificados.<BR>Para quitar la asignación de la directiva por usuario previamente asignada, utilice el mismo comando que antes, pero establezca el parámetro PolicyName esta vez en un valor nulo:<BR>Grant-CsUserServicesPolicy –Identity "Ken Myer" –PolicyName $Null



Al trabajar con el almacén de contactos unificados, es importante tener presente el fragmento "se impide que los contactos de Ken migren al almacén de contactos unificados". Asignar a Ken una nueva directiva de servicios de usuario no basta para que sus contactos se quiten del almacén de contactos unificados. Cuando un usuario inicia sesión en Lync Server 2013, el sistema comprueba su directiva de servicios de usuario para ver si sus contactos deben permanecer en el almacén de contactos unificados. Si la respuesta es afirmativa (es decir, la propiedad UcsAllowed está establecida en $True), los contactos se migrarán al almacén de contactos unificados (siempre y cuando dichos contactos no estén aún ahí). Si la respuesta es negativa, Lync Server simplemente omite los contactos del usuario y avanza a la siguiente tarea, lo que significa que Lync Server no los quitará del almacén de contactos unificados automáticamente, sea cual sea el valor de la propiedad UcsAllowed.

Esto también quiere decir que, después de asignar al usuario una nueva directiva de servicios de usuario, se debe ejecutar el cmdlet [Invoke-CsUcsRollback](https://docs.microsoft.com/en-us/powershell/module/skype/Invoke-CsUcsRollback) para sacar sus contactos de Exchange 2013 y colocarlos de vuelta en Lync Server 2013. Por ejemplo, después de asignar a Ken Myer una nueva directiva de servicios de usuario, sus contactos se pueden sacar del almacén de contactos unificados con el siguiente comando:

    Invoke-CsUcsRollback -Identity "Ken Myer"

Si se cambia la directiva de servicios de usuario, pero no se ejecuta el cmdlet Invoke-CsUcsRollback, los contactos de Ken no se eliminarán del almacén de contactos unificados. ¿Qué ocurriría si se ejecutara Invoke-CsUcsRollback sin modificar la directiva de servicios de usuario de Ken Myer? Pues que los contactos de Ken se eliminarán de manera temporal del almacén de contactos unificados. El hecho de que esta eliminación sea temporal es importante. Después de que los contactos de Ken se quiten del almacén de contactos unificados, Lync Server 2013 esperará siete días para ver qué directiva de servicios de usuario se ha asignado a Ken. Si Ken sigue teniendo asignada una directiva que permite usar el almacén de contactos unificados, sus contactos se colocarán de nuevo en dicho almacén. Para eliminar contactos del almacén de contactos unificados de manera permanente, debe cambiar la directiva de servicios de usuario y, además, ejecutar el cmdlet Invoke-CsUcsRollback.

El número de variables que pueden afectar a la migración es enorme por lo que es difícil calcular cuánto tiempo llevará migrar completamente todas las cuentas al almacén de contactos unificados. Por regla general, la migración no tiene efecto de forma inmediata, aunque se migre un número pequeño de contactos, puede llevar 10 minutos o más completar el traspaso.

