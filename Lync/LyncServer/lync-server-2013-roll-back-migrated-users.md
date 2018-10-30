---
title: 'Lync Server 2013: Revertir usuarios migrados'
TOCTitle: Revertir usuarios migrados
ms:assetid: bfabaf0b-9a42-4057-b729-a7ab9eee8c72
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ205224(v=OCS.15)
ms:contentKeyID: 48276550
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Revertir usuarios migrados en Lync Server 2013

 

_**Última modificación del tema:** 2012-10-07_

Si tiene que revertir la característica de almacén de contactos unificado, revierta los contactos solo si va a mover al usuario de nuevo a Exchange 2010 o Lync Server 2010. Para hacer la reversión, deshabilite la directiva del usuario y ejecute el cmdlet **Invoke-CsUcsRollback**. Ejecutar solo **Invoke-CsUcsRollback** no es suficiente para que la reversión sea permanente, porque la migración del almacén de contactos unificado se iniciará de nuevo si la directiva no se deshabilita. Por ejemplo, si un usuario se revierte porque Exchange 2013 se revierte a Exchange 2010, y el buzón del usuario se mueve a Exchange 2013, la migración del almacén de contactos unificado se volverá a iniciar siete días después de la reversión, si el almacén de contactos unificado sigue habilitado para el usuario en la directiva de servicios del usuario.

> [!IMPORTANT]  
> El cmdlet <strong>Move-CsUser</strong> revierte automáticamente el almacén de contactos del usuario de Exchange 2013 a Lync Server 2013 en los casos siguientes:
> <ul>
> <li><p>Cuando se mueven usuarios de Lync Server 2013 a Lync Server 2010.</p></li>
> <li><p>Cuando se migran usuarios entre instalaciones locales, como cuando se mueve un usuario de Skype Empresarial Online a la instalación local de Lync Server 2013, o viceversa.</p></li>
> </ul>


> [!IMPORTANT]  
> La importación de datos del almacén de contactos unificado desde una base de datos de copia de seguridad puede dañar los datos del almacén de contactos unificado y del usuario si el modo de almacén de contactos unificado cambia entre la exportación y la importación. Por ejemplo:
> <ul>
> <li><p>Si exporta las listas de contactos antes de migrar los contactos del usuario a Exchange 2013 y, tras la migración, importa los mismos datos, los datos del almacén de contactos unificado y las listas de contactos se dañarán.</p></li>
> <li><p>Si exporta los datos de usuario después de migrar los usuarios a Exchange 2013, revierte la migración y, por algún motivo, importa los datos después de la migración, los datos del almacén de contactos unificado y las listas de contactos se dañarán.</p></li>
> </ul>


> [!IMPORTANT]  
> Antes de mover un buzón de Exchange de Exchange 2013 a Exchange 2010, el administrador de Exchange debe asegurarse de que el administrador de Lync Server ha revertido primero los contactos del usuario de Lync Server de Exchange 2013 a Lync Server. Para revertir los contactos del almacén de contactos unificado a Lync Server, consulte el procedimiento &quot;Para revertir los contactos del almacén de contactos unificado de Exchange 2013 a Lync Server 2013&quot; que aparece más adelante en esta sección.



El procedimiento siguiente describe cómo revertir los contactos del usuario. Si usa el cmdlet **Move-CsUser** para mover usuarios entre Lync Server 2013 y Lync Server 2010, puede omitir estos pasos porque el cmdlet **Move-CsUser** revierte automáticamente el almacén de contactos unificado cuando mueve usuarios de Lync Server 2013 a Lync Server 2010. **Move-CsUser** no deshabilita la directiva del almacén de contactos unificado, de modo que la migración al almacén de contactos unificado se repetirá si el usuario se devuelve a Lync Server 2013.

## Para revertir los contactos de los usuarios de Lync Server 2013 a Lync Server 2010:

1.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Shell de administración de Lync Server**.

2.  Deshabilite el almacén de contactos unificado para revertir los usuarios de manera que no se vuelvan a migrar tras la reversión. Siga este paso solo si desea asegurarse de que los usuarios no volverán a migrarse en el futuro. Para deshabilitar el almacén de contactos unificado para usuarios individuales, en la línea de comandos, escriba:
    
        Set-CsUserServicesPolicy -Identity "<policy name>" -UcsAllowed $False
    
    Por ejemplo:
    
        Set-CsUserServicesPolicy -Identity "UCS Enabled Users" -UcsAllowed $False

3.  Antes de mover un usuario de Lync Server 2013 a Lync Server 2010, revierta la lista de conocidos para los usuarios especificados en Lync Server.
    
    > [!IMPORTANT]  
    > Si se omite este paso, se perderá la lista de conocidos.
    


4.  Revierta los usuarios especificados. En la línea de comandos, escriba:
    
        Invoke-CsUcsRollback -Identity "<user display name>"
    
    Por ejemplo:
    
        Invoke-CsUcsRollback -Identity "Ken Myer"
    
    > [!IMPORTANT]  
    > No se recomienda usar la opción –Force para forzar la reversión. Si usa esta opción, los contactos de los usuarios se perderán.
    


## Para revertir los contactos del almacén de contactos unificado de Exchange 2013 a Lync Server 2013:

1.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Shell de administración de Lync Server**.

2.  Deshabilite el almacén de contactos unificado para revertir los usuarios de manera que no se vuelvan a migrar tras la reversión. Para deshabilitar el almacén de contactos unificado para usuarios individuales, en la línea de comandos, escriba:
    
        Set-CsUserServicesPolicy -Identity "<policy name>" -UcsAllowed $False
    
    Por ejemplo:
    
        Set-CsUserServicesPolicy -Identity "UCS Enabled Users" -UcsAllowed $False

3.  Revierta los usuarios especificados. En la línea de comandos, escriba:
    
        Invoke-CsUcsRollback -Identity "<user display name>"
    
    Por ejemplo:
    
        Invoke-CsUcsRollback -Identity "Ken Myer"
    
    > [!IMPORTANT]  
    > Primero debe revertir al usuario de Lync Server y, a continuación, mover el buzón de Exchange 2013. El administrador de Exchange se bloqueará para que no revierta Exchange hasta que la reversión de Lync Server se haya completado. No se recomienda usar la opción -Force para forzar la reversión. Si lo hace, los contactos de los usuarios se perderán.
    


4.  Después de revertir al usuario a Lync Server, el administrador de Exchange puede revertir al usuario de Exchange de Exchange 2013 a Exchange 2010.

