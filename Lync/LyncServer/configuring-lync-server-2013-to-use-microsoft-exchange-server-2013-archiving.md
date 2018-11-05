---
title: "Configurar MS Lync Server 2013 para utilizar el archivado de MS Exchange Server 2013"
TOCTitle: Configuración de Microsoft Lync Server 2013 para utilizar el archivado de Exchange Server 2013
ms:assetid: 260346d1-edc8-4a0c-8ad2-6c2401c3c377
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ679896(v=OCS.15)
ms:contentKeyID: 49888932
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuración de Microsoft Lync Server 2013 para utilizar el archivado de Microsoft Exchange Server 2013

 

_**Última modificación del tema:** 2014-06-24_

Microsoft Lync Server 2013 ofrece a los administradores la opción de archivar las transcripciones de conferencias web y sesiones de mensajería instantánea en el buzón de Microsoft Exchange Server 2013 del usuario en lugar de en una base de datos de SQL Server. Si se habilita esta opción, las transcripciones se escribirán en la carpeta Purga del buzón del usuario. La carpeta Purga es una carpeta oculta que se encuentra en la carpeta Elementos recuperables. Aunque dicha carpeta no está visible para los usuarios finales, es una carpeta que indiza el motor de búsqueda de Exchange y en la que se pueden realizar búsquedas con la característica de búsqueda de buzón de Exchange o de Microsoft SharePoint Server 2013. Puesto que la información se almacena en la misma carpeta que usa la característica de puesta en espera de Exchange (responsable del archivado del correo electrónico y de otras comunicaciones de Exchange), los administradores pueden usar una única herramienta para todas las comunicaciones electrónicas archivadas del usuario.

> [!IMPORTANT]  
> Para desactivar completamente el archivado de una conversación de Lync, debe desactivar también el historial de conversaciones de Lync. Para obtener más información, vea los siguientes temas: <a href="lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md">Administrar el archivado de las comunicaciones internas y externas en Lync Server 2013</a>, <a href="https://docs.microsoft.com/en-us/powershell/module/skype/New-CsClientPolicy">New-CsClientPolicy</a> y <a href="https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsClientPolicy">Set-CsClientPolicy</a>.



Para archivar las transcripciones en Exchange 2013, debe comenzar por configurar la autenticación de servidor a servidor entre los dos servidores. Una vez configurada la autenticación de servidor a servidor, podrá llevar a cabo las siguientes tareas en Microsoft Lync Server 2013 (tenga en cuenta que en función de su instalación y configuración, es posible que no tenga que completar todas estas tareas):

1.  Habilite el archivado en Exchange. Para ello, modifique la configuración de archivado de Lync Server. Este paso es obligatorio en todas las implementaciones.

2.  Habilite el archivado de comunicaciones externas/internas de los usuarios. Este paso es obligatorio para todas las implementaciones.

3.  Configure la propiedad ExchangeArchivingPolicy para cada usuario. Este paso solo es obligatorio si Lync Server y Exchange se encuentran bosques distintos.

## Paso 1: Habilitación del archivado en Exchange

El archivado en Lync Server suele administrarse mediante las opciones de archivado. Cuando instale Lync Server 2013, dispondrá de una recopilación única y global de estas opciones. (Los administradores pueden crear, de forma opcional, nuevas colecciones de opciones de archivado en el sitio.) De forma predeterminada, el archivado no está habilitado en las opciones globales. Asimismo, el archivado en Exchange tampoco está habilitado en estas opciones. Para poder utilizar el archivado en Exchange, los administradores deben configurar las propiedades EnableArchiving y EnableExchangeArchiving en las opciones de configuración. Es posible establecer la propiedad EnableArchiving con uno de los tres valores siguientes:

  - **None**. El archivado está deshabilitado. Este es el valor predeterminado. Si EnableArchiving se establece en None, no se archivará ningún contenido tanto en la base de datos de archivado de Lync Server como en Exchange 2013.

  - **ImOnly**. Solo se archivarán las transcripciones de mensajería instantánea. Si se habilita el archivado en Exchange, estas transcripciones se archivarán en Exchange 2013. Si el archivado en Exchange está deshabilitado, las transcripciones se archivarán en Lync Server.

  - **ImAndWebConf**. Se archivarán las transcripciones de mensajería instantánea y de las conferencias web. Si se habilita el archivado en Exchange, estas transcripciones se archivarán en Exchange 2013. Si el archivado en Exchange está deshabilitado, las transcripciones se archivarán en Lync Server.

La propiedad EnableExchangeArchiving es un valor booleano: establezca EnableExchangeArchiving en True ($True) para habilitar el archivado en Exchange o en False ($False) para deshabilitar el archivado en Exchange. Por ejemplo, este comando habilita el archivado de transcripciones de mensajería instantánea y también habilita el archivado en Exchange:

    Set-CsArchivingConfiguration -Identity "global" -EnableArchiving ImOnly -EnableExchangeArchiving $True

Para deshabilitar el archivado en Exchange, use un comando similar al siguiente. Este comando habilita el archivado de la mensajería instantánea pero deshabilita el archivado en Exchange (en otras palabras, las transcripciones se archivarán en Lync Server):

    Set-CsArchivingConfiguration -Identity "global" -EnableArchiving ImOnly -EnableExchangeArchiving $False


> [!NOTE]
> Si se establece la propiedad EnableArchiving en None, Lync Server no archivará ni las transcripciones de mensajería instantánea ni las transcripciones de conferencias web. En este caso, el servidor simplemente ignorará el valor configurado de la propiedad EnableExchangeArchiving.



También es posible habilitar (o deshabilitar) el archivado en Exchange desde el Panel de control de Lync Server. Para ello, lleve a cabo el procedimiento siguiente:

1.  En el Panel de control, haga clic en **Configuración y archivado** y, a continuación, en **Configuración de archivado**.

2.  En la pestaña **Configuración de archivado**, haga doble clic en la recopilación de opciones de archivado que desea modificar (por ejemplo, la recopilación **Global**).

3.  En el panel **Editar configuración de archivado**, haga clic en la lista desplegable **Configuración de archivado** y seleccione **Archivar sesiones de mensajería instantánea** (para archivar solo las sesiones de mensajería instantánea) o **Archivar sesiones de mensajería instantánea y conferencias web** (para archivar tanto las sesiones de conferencia web y mensajería instantánea).

4.  Tras seleccionar los elementos que desea archivar, marque la casilla **Integración con Exchange Server** para habilitar el archivado en Exchange. Para deshabilitar el archivado en Exchange, desactive esta casilla de verificación.


> [!NOTE]
> La casilla <STRONG>Integración con Exchange Server</STRONG> no estará disponible si la opción <STRONG>Configuración de archivado</STRONG> está configurada como <STRONG>Deshabilitar archivado</STRONG>. Debe habilitar el archivado en primer lugar y, a continuación, habilitar el archivado en Exchange.



Si Lync Server 2013 y Exchange 2013 se encuentran en el mismo bosque, el archivado de usuarios individuales (o al menos de los usuarios que dispongan de cuentas de correo electrónico en Exchange 2013) puede administrarse mediante las directivas de mantenimiento en espera de Exchange. Si tiene usuarios hospedados en una versión anterior de Exchange, el archivado para dichos usuarios puede administrarse mediante directivas de archivado de Lync Server. Tenga en cuenta que solo los usuarios con cuentas en Exchange 2013 pueden archivar sus transcripciones de Lync en Exchange.

Si Lync Server 2013 y Exchange 2013 se encuentran en bosques distintos, el archivado de usuarios individuales debe administrarse mediante la configuración de la propiedad ExchangeArchivingPolicy de cada cuenta de usuario individual. Vea el paso 3 para obtener más información.

## Paso 2: Habilitación del archivado de comunicaciones internas o externas

Tras habilitar el archivado (y el archivado en Exchange), debe modificar las directivas correspondientes para garantizar el archivado de las sesiones de los usuarios. Tenga en cuenta que la simple habilitación del archivado (Paso 1) no basta para que Lync Server inicie el archivado de las transcripciones de mensajería instantánea y de conferencias web. En su lugar, debe usar directivas de archivado para habilitar el archivado externo o interno. Cuando instale Lync Server 2013, también deberá instalar una única directiva de archivado global que contenga dos propiedades:

  - **ArchiveInternal**. Cuando se establece en True ($True), indica que solo se archivarán las sesiones de comunicaciones internas (solo las sesiones de los usuarios de su organización que dispongan de cuentas de Active Directory).

  - **ArchiveExternal**. Cuando se establece en True ($True), indica que solo se archivarán las sesiones de comunicaciones externas (sesiones en las que al menos usuario de su organización no disponga de cuenta de Active Directory).

De forma predeterminada, estos valores de propiedades están establecidos como False, lo que implica que no se archivan ni las sesiones de comunicaciones internas ni externas. Para modificar la directiva global, use el Shell de administración de Lync Server y el cmdlet Set-CsArchivingPolicy. El comando siguiente habilita el archivado de las sesiones de comunicaciones internas y externas:

    Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $True -ArchiveExternal $True

De forma alternativa, puede usar el cmdlet New-CsArchivingPolicy para crear una nueva directiva para el sitio o por usuario. Por ejemplo, este comando permite crear una directiva de archivado específica para un usuario con el nombre RedmondArchivingPolicy:

    New-CsArchivingPolicy -Identity "RedmondArchivingPolicy" -ArchiveInternal $True -ArchiveExternal $True

Si crea una directiva específica para un usuario, necesitará asignar dicha directiva a los usuarios correspondientes. Por ejemplo:

    Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName  "RedmondArchivingPolicy"

También puede administrar las directivas de archivado mediante el Panel de control de Lync Server. Desde el Panel de control, haga clic en **Supervisión y archivado** y haga clic en **Directiva de archivado**. Para modificar una directiva existente, haga doble clic en la directiva (por ejemplo, Global) y, a continuación, en el panel **Editar directiva de archivado**, active o desactive las casillas **Archivar comunicaciones internas** o **Archivar comunicaciones externas** según sea necesario. Para crear una nueva directiva de archivado, haga clic en **Nueva** y, a continuación, seleccione **Directiva de sitio** o **Directiva de usuario**. Si crea una nueva directiva de usuario, deberá tener acceso a las cuentas de usuario correspondientes (desde la pestaña **Usuarios**) y asignar dichos usuarios a la nueva directiva.

## Paso 3: Configuración de la propiedad ExchangeArchivingPolicy

En caso de que Lync Server 2013 y Exchange 2013 se encuentren en bosques distintos, no bastará con habilitar el archivado en Exchange en las opciones de configuración para que se archiven las transcripciones de mensajería instantánea y de las conferencias web en Exchange. En su lugar, deberá configurar la propiedad ExchangeArchivingPolicy en cada cuenta de usuario de Lync Server correspondiente. Esta propiedad puede establecerse con uno de los cuatro valores posibles:

1.  Uninitialized. Indica que el archivado se llevará a cabo en función de las opciones de puesta en espera configuradas para el buzón de Exchange del usuario. Si la puesta en espera no se ha habilitado en el buzón del usuario, se archivarán las transcripciones de mensajería instantánea o de las conferencias web del usuario en Lync Server.

2.  **UseLyncArchivingPolicy**. Indica que las transcripciones de mensajería instantánea y de las conferencias web se deben archivar en Lync Server y no en Exchange.

3.  **NoArchiving**. Indica que las transcripciones de mensajería instantánea y de las conferencias web no deben archivarse. Tenga en cuenta que esta opción anula cualquier directiva de archivado de Lync Server asignada al usuario.

4.  **ArchivingToExchange**. Indica que las transcripciones de mensajería instantánea y de las conferencias web se deben archivar en Exchange, sin importar cuál sea la configuración de puesta en espera asignada (o no asignada) al buzón del usuario.

Por ejemplo, para configurar una cuenta de usuario para que las transcripciones de mensajería instantánea y de las conferencias web se archiven siempre en Exchange, utilice un comando similar al siguiente desde el Shell de administración de Lync Server:

    Set-CsUser -Identity "Ken Myer" -ExchangeArchivingPolicy ArchivingToExchange

Si desea establecer la misma directiva de archivado para un grupo de usuarios (por ejemplo, todos los usuarios hospedados en un Grupo de registradores específico), utilice un comando similar al siguiente:

    Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.litwareinc.com"} | Set-CsUser -ExchangeArchivingPolicy ArchivingToExchange

Tenga en cuenta que debe utilizar el Shell de administración de Lync Server (y Windows PowerShell) para configurar el valor de la propiedad ExchangeArchivingPolicy. Esta propiedad no se muestra a los administradores en el Panel de control de Lync Server.

Si desea ver una lista de los usuarios a los que se ha asignado una directiva de archivado específica, utilice un comando similar al siguiente, que devuelve el nombre para mostrar de Active Directory de todos los usuarios para los que se ha establecido la propiedad ExchangeArchivingPolicy como Uninitialized:

    Get-CsUser | Where-Object {$_.ExchangeArchivingPolicy -eq "Uninitialized"} | Select-Object DisplayName

Del mismo modo, este comando devuelve el nombre para mostrar de los usuarios que no tienen la propiedad ExchangeArchivingPolicy establecida como UseLyncArchivingPolicy:

    Get-CsUser | Where-Object {$_.ExchangeArchivingPolicy -ne "UseLyncArchivingPolicy"} | Select-Object DisplayName

