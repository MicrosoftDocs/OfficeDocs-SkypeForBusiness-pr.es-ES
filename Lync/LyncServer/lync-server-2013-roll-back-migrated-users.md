---
title: 'Lync Server 2013: revertir usuarios migrados'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Roll back migrated users
ms:assetid: bfabaf0b-9a42-4057-b729-a7ab9eee8c72
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205224(v=OCS.15)
ms:contentKeyID: 48185286
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 05678690718563dac9187ee275d3809016b78d33
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42208496"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="roll-back-migrated-users-in-lync-server-2013"></a>Revertir usuarios migrados en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-07_

Si necesita revertir la característica de almacén de contactos unificado, revierta los contactos solo si vuelve a colocar al usuario en Exchange 2010 o Lync Server 2010. Para hacer la reversión, deshabilite la directiva del usuario y ejecute el cmdlet **Invoke-CsUcsRollback**. Ejecutar solo **Invoke-CsUcsRollback** no es suficiente para que la reversión sea permanente, porque la migración del almacén de contactos unificado se iniciará de nuevo si la directiva no se deshabilita. Por ejemplo, si un usuario se deshace porque Exchange 2013 se revierte a Exchange 2010 y, a continuación, el buzón del usuario se mueve a Exchange 2013, la migración del almacén de contactos unificado se iniciará siete días después de la reversión, siempre que el almacén de contactos unificado todavía está habilitada para el usuario en la Directiva de servicios de usuario.

<div>


> [!IMPORTANT]  
> El cmdlet <STRONG>Move-CsUser</STRONG> revierte automáticamente el almacén de contactos del usuario de Exchange 2013 a Lync Server 2013 en las siguientes situaciones: 
> <UL>
> <LI>
> <P>Cuando los usuarios se mueven de Lync Server 2013 a Lync Server 2010.</P>
> <LI>
> <P>Cuando se migran usuarios entre instalaciones locales, como cuando se mueve un usuario de Lync Online a Lync Server 2013 local, o viceversa.</P></LI></UL>



</div>

<div>


> [!IMPORTANT]  
> La importación de datos del almacén de contactos unificado desde una base de datos de copia de seguridad puede dañar los datos del almacén de contactos unificado y del usuario si el modo de almacén de contactos unificado cambia entre la exportación y la importación. Por ejemplo: 
> <UL>
> <LI>
> <P>Si exporta listas de contactos antes de migrar los contactos de los usuarios a Exchange 2013 y, después de la migración, importa los mismos datos, los datos del almacén de contactos unificado y las listas de contactos se dañarán.</P>
> <LI>
> <P>Si exporta los datos de usuario después de migrar los usuarios a Exchange 2013, revierte la migración y, por algún motivo, importa los datos de después de la migración, los datos del almacén de contactos unificado y las listas de contactos se dañarán.</P></LI></UL>



</div>

<div>


> [!IMPORTANT]  
> Antes de mover un buzón de Exchange de Exchange 2013 a Exchange 2010, el administrador de Exchange debe asegurarse de que el administrador de Lync Server haya revertido primero los contactos de usuario de Lync Server de Exchange 2013 a Lync Server. Para revertir los contactos del almacén de contactos unificado a Lync Server, consulte procedimiento "para revertir los contactos del almacén de contactos unificados de Exchange 2013 a Lync Server 2013", más adelante en esta sección.



</div>

El procedimiento siguiente describe cómo revertir los contactos del usuario. Si usa el cmdlet **Move-CsUser** para mover usuarios entre lync Server 2013 y lync Server 2010, puede omitir estos pasos, ya que el cmdlet **Move-CsUser** revierte automáticamente unifed almacén de contactos cuando mueve usuarios de Lync Server 2013 a Lync Server 2010. **Move-CsUser** no deshabilita la Directiva del almacén de contactos unificado, por lo que la migración al almacén de contactos unificado se repetirá si el usuario se vuelve a colocar en Lync Server 2013.

<div>

## <a name="to-roll-back-user-contacts-from-lync-server-2013-to-lync-server-2010"></a>Para revertir contactos de usuario de Lync Server 2013 a Lync Server 2010

1.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.

2.  Deshabilite el almacén de contactos unificado para revertir los usuarios de manera que no se vuelvan a migrar tras la reversión. Siga este paso solo si desea asegurarse de que los usuarios no volverán a migrarse en el futuro. Para deshabilitar el almacén de contactos unificado para usuarios individuales, en la línea de comandos, escriba:
    
        Set-CsUserServicesPolicy -Identity "<policy name>" -UcsAllowed $False
    
    Por ejemplo:
    
        Set-CsUserServicesPolicy -Identity "UCS Enabled Users" -UcsAllowed $False

3.  Antes de mover un usuario de Lync Server 2013 a Lync Server 2010, revierta la lista de conocidos para los usuarios especificados en Lync Server.
    
    <div>
    

    > [!IMPORTANT]  
    > Si se omite este paso, se perderá la lista de conocidos.

    
    </div>

4.  Revierta los usuarios especificados. En la línea de comandos, escriba:
    
        Invoke-CsUcsRollback -Identity "<user display name>"
    
    Por ejemplo:
    
        Invoke-CsUcsRollback -Identity "Ken Myer"
    
    <div>
    

    > [!IMPORTANT]  
    > No se recomienda usar la opción –Force para forzar la reversión. Si usa esta opción, los contactos de los usuarios se perderán.

    
    </div>

</div>

<div>

## <a name="to-roll-back-unified-contact-store-contacts-from-exchange-2013-to-lync-server-2013"></a>Para revertir los contactos del almacén de contactos unificados de Exchange 2013 a Lync Server 2013

1.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.

2.  Deshabilite el almacén de contactos unificado para revertir los usuarios de manera que no se vuelvan a migrar tras la reversión. Para deshabilitar el almacén de contactos unificado para usuarios individuales, en la línea de comandos, escriba:
    
        Set-CsUserServicesPolicy -Identity "<policy name>" -UcsAllowed $False
    
    Por ejemplo:
    
        Set-CsUserServicesPolicy -Identity "UCS Enabled Users" -UcsAllowed $False

3.  Revierta los usuarios especificados. En la línea de comandos, escriba:
    
        Invoke-CsUcsRollback -Identity "<user display name>"
    
    Por ejemplo:
    
        Invoke-CsUcsRollback -Identity "Ken Myer"
    
    <div>
    

    > [!IMPORTANT]  
    > Primero debe volver al usuario de Lync Server y, a continuación, mover el buzón de Exchange 2013. El administrador de Exchange no pudo revertir Exchange hasta que se complete el reversión de Lync Server. No se recomienda usar la opción -Force para forzar la reversión. Si lo hace, los contactos de los usuarios se perderán.

    
    </div>

4.  Después de revertir al usuario a Lync Server, el administrador de Exchange puede revertir al usuario de Exchange de Exchange 2013 a Exchange 2010.

</div>

</div>

<span> </span>

</div>

</div>

</div>

