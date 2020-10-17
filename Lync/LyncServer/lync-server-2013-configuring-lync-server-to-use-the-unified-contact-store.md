---
title: 'Lync Server 2013: configuración de Lync Server para usar el almacén de contactos unificado'
description: 'Lync Server 2013: configurar Lync Server para usar el almacén de contactos unificado.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Lync Server 2013 to use the unified contact store
ms:assetid: 6aa17ae3-764e-4986-a900-85a3cdb8c1fc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688083(v=OCS.15)
ms:contentKeyID: 49733680
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6905d2e393fec36fe5db3e40ee20087c0cca0991
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48570796"
---
# <a name="configuring-microsoft-lync-server-2013-to-use-the-unified-contact-store"></a>Configuración de Microsoft Lync Server 2013 para usar el almacén de contactos unificados

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-02-07_

El almacén de contactos unificados permite a los usuarios mantener una única lista de contactos y hacer que dichos contactos estén disponibles en varias aplicaciones, como Microsoft Lync 2013, Microsoft Outlook 2013 y Microsoft Outlook Web App 2013. Cuando habilita el almacén de contactos unificado para un usuario, los contactos de ese usuario no se almacenan en Microsoft Lync Server 2013 y, a continuación, se recuperan mediante el protocolo SIP. En su lugar, sus contactos se almacenan en Microsoft Exchange Server 2013 y se recuperan mediante los servicios Web de Exchange.

<div>


> [!NOTE]  
> Técnicamente, la información de contacto se almacena en un par de carpetas que se encuentran en el buzón de Exchange 2013 del usuario. Los propios contactos se almacenan en una carpeta llamada contactos de Lync que es visible para los usuarios finales; los metadatos de los contactos se almacenan en una subcarpeta que no es visible para los usuarios finales.



</div>

<div>

## <a name="enabling-the-unified-contact-store-for-a-user"></a>Habilitar el almacén de contactos unificados de un usuario

Si ya ha configurado la autenticación de servidor a servidor entre Lync Server 2013 y Exchange 2013, también habrá habilitado el uso del almacén de contactos unificados; no se necesita ninguna configuración adicional del servidor. Sin embargo, se requiere la configuración de cuentas de usuario adicionales para mover los contactos de un usuario al almacén de contactos unificado. De forma predeterminada, los contactos de usuario se conservan en Lync Server y no en el almacén de contactos unificado.

El acceso al almacén de contactos unificado se administra mediante las directivas de servicios de usuario de Lync Server. Las directivas de servidor de usuario solo tienen una propiedad (Ucsallowed configurado); Esta propiedad se usa para determinar la ubicación en la que se almacenan los contactos de un usuario. Si un usuario se administra mediante una directiva de servicios de usuario donde Ucsallowed configurado se ha establecido en true ($True), los contactos del usuario se almacenarán en el almacén de contactos unificado. Si el usuario se administra mediante una directiva de servicios de usuario donde Ucsallowed configurado se ha establecido en false ($False), sus contactos se almacenarán en Lync Server.

Al instalar Lync Server 2013, también se instala una única directiva de servicios de usuario (configurada en el ámbito global). El valor Ucsallowed configurado de esta Directiva se establece en true, lo que significa que, de forma predeterminada, los contactos de usuario se almacenarán en el almacén de contactos unificados (suponiendo que se ha implementado y configurado). Si desea migrar todos los contactos de los usuarios al almacén de contactos unificado, no tiene que hacer nada.

Si prefiere no migrar todos los contactos al almacén de contactos unificado, puede deshabilitar el almacén de contactos unificados para todos los usuarios si establece la propiedad Ucsallowed configurado de la directiva global en false:

    Set-CsUserServicesPolicy -Identity global -UcsAllowed $False

Después de deshabilitar el almacén de contactos unificados en la directiva global, puede crear una directiva por usuario que permita el uso del almacén de contactos unificados; Esto le permite a algunos usuarios mantener sus contactos en el almacén de contactos unificado mientras otros usuarios continúan manteniendo sus contactos en Lync Server. Para crear una directiva de servicios de usuario por usuario se usa un comando parecido al siguiente:

    New-CsUserServicesPolicy -Identity "AllowUnifiedContactStore" -UcsAllowed $True

Una vez creada la directiva, hay que asignarla a los usuarios que deban tener acceso al almacén de contactos unificados. Para ello, se usan comandos parecidos a los siguientes:

    Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName "AllowUnifiedContactStore"

Una vez que se ha asignado la Directiva, Lync Server comenzará a migrar los contactos del usuario al almacén de contactos unificado. Una vez completada la migración, el usuario tendrá sus contactos almacenados en Exchange en lugar de Lync Server. Si el usuario ha iniciado sesión en Lync 2013 en el momento de completar la migración, aparecerá un cuadro de mensaje y se le pedirá que cierre sesión en Lync y que vuelva a iniciarla para finalizar el proceso. Los usuarios a los que no se haya asignado esta Directiva por usuario no tendrán sus contactos migrados al almacén de contactos unificado. Esto se debe a que los usuarios están siendo administrados por la directiva global y el uso del almacén de contactos unificado se ha deshabilitado en la directiva global.

Puede comprobar que los contactos de un usuario se han migrado correctamente al almacén de contactos unificado ejecutando el cmdlet [Test-CsUnifiedContactStore](https://docs.microsoft.com/powershell/module/skype/Test-CsUnifiedContactStore) desde el shell de administración de Lync Server:

    Test-CsUnifiedContactStore -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com"

Si Test-CsUnifiedContactStore finaliza correctamente, querrá decir que los contactos del usuario sip:kenmyer@litwareinc.com se han migrado correctamente al almacén de contactos unificados.

</div>

<div>

## <a name="rolling-back-the-unified-contact-store"></a>Revertir el almacén de datos unificados

Si necesita quitar los contactos de un usuario del almacén de contactos unificados (por ejemplo, si el usuario necesita volver a alojarse en Microsoft Lync Server 2010 y, por lo tanto, ya no puede usar el almacén de contactos unificado), debe hacer dos cosas. En primer lugar, debe asignar al usuario una nueva Directiva de servicios de usuario, que prohíbe almacenar contactos en el almacén de contactos unificados. (Es decir, una directiva en la que la propiedad Ucsallowed configurado se ha establecido en $False). Si no tiene dicha Directiva, puede crear una con un comando similar a este:

    New-CsUserServicesPolicy -Identity NoUnifiedContactStore -UcsAllowed $False

Después, puede usar un comando como el siguiente para asignar esta nueva directiva por usuario (NoUnifiedContactStore):

    Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName NoUnifiedContactStore

Con el comando anterior la nueva directiva se asigna al usuario Ken Myer y, asimismo, se impide que los contactos de Ken migren al almacén de contactos unificados.

<div>


> [!NOTE]  
> Algunas veces, se puede lograr el mismo efecto con tan solo quitar la directiva de servicios de usuario actual que el usuario tiene asignada. Imaginemos, por ejemplo, que Ken Myer tiene una directiva de servicios de usuario por usuario que permite el uso del almacén de contactos unificados, pero la directiva global prohíbe usarlo. En tal caso, se podría quitar la directiva de servicios de usuario que Ken tiene asignada. Al hacerlo, Ken pasará automáticamente a estar administrado por la directiva global y, en consecuencia, dejará de tener acceso al almacén de contactos unificados.<BR>Para quitar la asignación de la directiva por usuario previamente asignada, utilice el mismo comando que antes, pero establezca el parámetro PolicyName esta vez en un valor nulo:<BR>Grant-CsUserServicesPolicy –Identity "Ken Myer" –PolicyName $Null



</div>

La terminología "impide que los contactos de Ken se migren al almacén de contactos unificados" es importante tener en cuenta al trabajar con el almacén de contactos unificados. Simplemente asignar a Ken una nueva Directiva de servicios de usuario no moverá a sus contactos del almacén de contactos unificado. Cuando un usuario inicia sesión en Lync Server 2013, el sistema comprueba la Directiva de servicios de usuario del usuario para ver si sus contactos deben conservarse en el almacén de contactos unificado. Si la respuesta es afirmativa (es decir, si la propiedad Ucsallowed configurado está establecida en $True), esos contactos se migrarán al almacén de contactos unificado (suponiendo que dichos contactos no se encuentren en el almacén de contactos unificado). Si la respuesta es no, Lync Server simplemente ignora los contactos del usuario y pasa a la siguiente tarea. Esto significa que Lync Server no moverá automáticamente los contactos de un usuario de fuera del almacén de contactos unificado, independientemente del valor de la propiedad Ucsallowed configurado.

Eso también significa que, después de asignar al usuario una nueva Directiva de servicios de usuario, debe ejecutar el cmdlet [Invoke-CsUcsRollback](https://docs.microsoft.com/powershell/module/skype/Invoke-CsUcsRollback) para mover los contactos del usuario fuera de Exchange 2013 y volver a Lync Server 2013. Por ejemplo, después de asignar a Ken Myer una nueva directiva de servicios de usuario, sus contactos se pueden sacar del almacén de contactos unificados con el siguiente comando:

    Invoke-CsUcsRollback -Identity "Ken Myer"

Si se cambia la directiva de servicios de usuario, pero no se ejecuta el cmdlet Invoke-CsUcsRollback, los contactos de Ken no se eliminarán del almacén de contactos unificados. ¿Qué ocurriría si se ejecutara Invoke-CsUcsRollback sin modificar la directiva de servicios de usuario de Ken Myer? Pues que los contactos de Ken se eliminarán de manera temporal del almacén de contactos unificados. El hecho de que esta eliminación sea temporal es importante. Una vez que los contactos de Ken se han quitado del almacén de contactos unificado, Lync Server 2013 esperará 7 días y, a continuación, comprobará qué directiva de servicios de usuario se ha asignado a Ken. Si Ken sigue teniendo asignada una directiva que permite usar el almacén de contactos unificados, sus contactos se colocarán de nuevo en dicho almacén. Para eliminar contactos del almacén de contactos unificados de manera permanente, debe cambiar la directiva de servicios de usuario y, además, ejecutar el cmdlet Invoke-CsUcsRollback.

Debido al gran número de variables que pueden afectar a la migración, es difícil calcular cuánto tiempo tardará antes de que las cuentas se migren completamente al almacén de contactos unificado. Como regla general, sin embargo, la migración no surte efecto inmediatamente: incluso cuando se migra un número reducido de contactos, puede tardar 10 minutos o más antes de que se complete el traslado.

</div>

</div>

<span> </span>

</div>

</div>

</div>

