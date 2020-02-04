---
title: Configuración de Lync Server 2013 para usar el archivado de Microsoft Exchange Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Lync Server 2013 to use Exchange Server 2013 archiving
ms:assetid: 260346d1-edc8-4a0c-8ad2-6c2401c3c377
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ679896(v=OCS.15)
ms:contentKeyID: 49557731
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3b163b0ce3324455f8a80eca7be5c1423b302a3d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723190"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-microsoft-lync-server-2013-to-use-microsoft-exchange-server-2013-archiving"></a>Configuración de Microsoft Lync Server 2013 para usar el archivado de Microsoft Exchange Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-06-24_

Microsoft Lync Server 2013 ofrece a los administradores la opción de enviar mensajes instantáneos y las transcripciones de conferencias web archivadas en el buzón de correo de un usuario de Microsoft Exchange Server 2013, en lugar de una base de datos de SQL Server. Si se habilita esta opción, las transcripciones se escribirán en la carpeta Purga del buzón del usuario. La carpeta Purga es una carpeta oculta que se encuentra en la carpeta Elementos recuperables. Aunque esta carpeta no está visible para los usuarios finales, la carpeta la indiza el motor de búsqueda de Exchange y se puede detectar mediante la búsqueda de correo de Exchange y/o Microsoft SharePoint Server 2013. Debido a que la información se almacena en la misma carpeta que usa la característica de conservación local de Exchange (responsable de archivar el correo electrónico y otras comunicaciones de Exchange), los administradores pueden usar una única herramienta para buscar todas las comunicaciones electrónicas archivadas para un usuario.

<div>


> [!IMPORTANT]  
> Para deshabilitar por completo el archivado de una conversación de Lync, también debe deshabilitar el historial de conversaciones de Lync. Para obtener más información, vea los siguientes temas: <A href="lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md">administrar el archivado de comunicaciones internas y externas en Lync Server 2013</A>, <A href="https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy">New-ClientPolicy</A>y <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy">set-ClientPolicy</A>.



</div>

Para archivar transcripciones a Exchange 2013 debe comenzar con la configuración de la autenticación de servidor a servidor entre los dos servidores. Una vez que se haya habilitado la autenticación de servidor a servidor, podrá realizar las siguientes tareas en Microsoft Lync Server 2013 (tenga en cuenta que, según la configuración y la configuración, es posible que no tenga que completar todas estas tareas):

1.  Habilite el archivado de Exchange modificando los valores de configuración de archivado de Lync Server. Este paso es obligatorio en todas las implementaciones.

2.  Habilite el archivado de comunicaciones externas/internas de los usuarios. Este paso es obligatorio en todas las implementaciones.

3.  Configure la propiedad ExchangeArchivingPolicy de cada usuario. Este paso solo es necesario en Lync Server y Exchange se encuentran en bosques diferentes.

<div>

## <a name="step-1-enabling-exchange-archiving"></a>Paso 1: habilitar el archivado de Exchange

El archivado en Lync Server se administra principalmente mediante la configuración de archivado. Al instalar Lync Server 2013, se le asigna automáticamente una única colección global de esta configuración. (Los administradores pueden, opcionalmente, crear nuevas colecciones de opciones de archivado en el ámbito del sitio). De forma predeterminada, el archivado no está habilitado en la configuración global ni está habilitado el archivado de Exchange en esta configuración. Para poder usar los administradores de archivado de Exchange, debe configurar las propiedades EnableArchiving y EnableExchangeArchiving en estas opciones de configuración. La propiedad EnableArchiving se puede establecer en uno de estos tres valores posibles:

  - **None**. El archivado está deshabilitado. Este es el valor predeterminado. Si EnableArchiving se establece en ninguno, no se archivará nada en la base de datos de archivado de Lync Server o en Exchange 2013.

  - **Solo**. Solo se archivan las transcripciones de mensajes instantáneos. Si habilita el archivado de Exchange, estas transcripciones se archivarán en Exchange 2013. Si el archivado de Exchange está deshabilitado, estas transcripciones se archivarán en Lync Server.

  - **ImAndWebConf**. Se archivan las transcripciones de mensajes instantáneos y las transcripciones de conferencias por Internet. Si habilita el archivado de Exchange, estas transcripciones se archivarán en Exchange 2013. Si el archivado de Exchange está deshabilitado, estas transcripciones se archivarán en Lync Server.

La propiedad EnableExchangeArchiving es un valor booleano: establezca EnableExchangeArchiving en true ($True) para habilitar el archivado de Exchange o establezca EnableExchangeArchiving en false ($False) para deshabilitar el archivado de Exchange. Por ejemplo, este comando permite el archivado de transcripciones de mensajería instantánea y también permite el archivado de Exchange:

    Set-CsArchivingConfiguration -Identity "global" -EnableArchiving ImOnly -EnableExchangeArchiving $True

Para deshabilitar el archivado de Exchange, use un comando similar al siguiente, que permite el archivado de mensajería instantánea pero deshabilita el archivado en Exchange (es decir, las transcripciones se archivarán en Lync Server):

    Set-CsArchivingConfiguration -Identity "global" -EnableArchiving ImOnly -EnableExchangeArchiving $False

<div>


> [!NOTE]  
> Si la propiedad EnableArchiving se establece en None, Lync Server no archivará ni el correo instantáneo ni las transcripciones de conferencias por Internet. En este caso, el servidor simplemente ignorará el valor configurado de la propiedad EnableExchangeArchiving.



</div>

El archivado de Exchange también se puede habilitar (o deshabilitar) mediante el panel de control de Lync Server. Para ello, haga lo siguiente:

1.  En el Panel de control, haga clic en **Supervisión y archivado** y, luego, en **Configuración de archivado**.

2.  En la pestaña **Configuración de archivado**, haga doble clic en la recopilación de opciones de archivado que quiera modificar (por ejemplo, **Global**).

3.  En el panel **Editar configuración de archivado**, haga clic en la lista desplegable **Configuración de archivado** y seleccione **Archivar sesiones de mensajería instantánea** (para archivar solo las sesiones de mensajería instantánea) o **Archivar sesiones de mensajería instantánea y conferencias web** (para archivar las sesiones tanto de conferencia web como de mensajería instantánea).

4.  Después de elegir los elementos para archivar, seleccione la casilla **integración de Exchange Server** para habilitar el archivado de Exchange. Para deshabilitar el archivado de Exchange, desactive esta casilla.

<div>


> [!NOTE]  
> La casilla <STRONG>Integración de Exchange Server</STRONG> no estará disponible si la opción <STRONG>Configuración de archivado</STRONG> está establecida en <STRONG>Deshabilitar archivado</STRONG>. Debe habilitar primero el archivado y, después, habilitar el archivado de Exchange.



</div>

Si Lync Server 2013 y Exchange 2013 se encuentran en el mismo bosque, el archivado para usuarios individuales (o, al menos, para los usuarios que tienen cuentas de correo electrónico en Exchange 2013) se administra mediante las directivas de retención local de Exchange. Si tiene usuarios alojados en una versión anterior de Exchange, el archivado de esos usuarios se administrará mediante las directivas de archivado de Lync Server. Tenga en cuenta que solo los usuarios con cuentas en Exchange 2013 pueden tener las transcripciones de Lync archivadas en Exchange.

Si Lync Server 2013 y Exchange 2013 se encuentran en bosques diferentes, el archivado para usuarios individuales se administra mediante la configuración de la propiedad ExchangeArchivingPolicy para cada cuenta de usuario individual. Mire el paso 3 para más información.

</div>

<div>

## <a name="step-2-enabling-the-archiving-of-internal-andor-external-communications"></a>Paso 2: habilitar el archivado de comunicaciones internas o externas

Una vez que haya habilitado el archivado (y el archivado de Exchange), debe modificar las directivas de archivado apropiadas para asegurarse de que las sesiones de usuario se hayan archivado realmente. Tenga en cuenta que simplemente habilitar el archivado (paso 1) no provoca que Lync Server empiece a archivar la mensajería instantánea y las transcripciones de conferencias por Internet. Hay que usar directivas de archivado para habilitar el archivado externo o interno. Al instalar Lync Server 2013, también se instala una única directiva de archivado global que contiene dos propiedades:

  - **ArchiveInternal**. Cuando se establece en True ($True), indica que solo se archivarán las sesiones de comunicaciones internas (solo las sesiones de los usuarios que tienen cuentas de Active Directory en la organización).

  - **ArchiveExternal**. Cuando se establece en True ($True), indica que solo se archivarán las sesiones de comunicaciones externas (sesiones en las que al menos un usuario no tiene una cuenta de Active Directory en la organización).

Los valores de estas propiedades están establecidos de forma predeterminada en False, lo que implica que no se archivan las sesiones de comunicaciones ni internas ni externas. Para modificar la directiva global, puede usar el shell de administración de Lync Server y el cmdlet Set-CsArchivingPolicy. El siguiente comando habilita el archivado de las sesiones de comunicaciones internas y externas:

    Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $True -ArchiveExternal $True

Otra opción consiste en usar el cmdlet New-CsArchivingPolicy para crear una directiva para el sitio o por usuario. Por ejemplo, este comando permite crear una directiva de archivado específica para un usuario con el nombre RedmondArchivingPolicy:

    New-CsArchivingPolicy -Identity "RedmondArchivingPolicy" -ArchiveInternal $True -ArchiveExternal $True

Si crea una directiva específica para un usuario, necesitará asignar dicha directiva a los usuarios correspondientes. Por ejemplo:

    Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName  "RedmondArchivingPolicy"

Las directivas de archivado también se pueden administrar mediante el panel de control de Lync Server. Desde el Panel de control, haga clic en **Supervisión y archivado** y haga clic en **Directiva de archivado**. Para modificar una directiva existente, haga doble clic en la directiva (por ejemplo, Global) y, en el panel **Editar directiva de archivado**, active o desactive las casillas **Archivar comunicaciones internas** o **Archivar comunicaciones externas**, según sea necesario. Para crear una nueva Directiva de archivado, haga clic en **nuevo** y, a continuación, seleccione **Directiva del sitio** o **Directiva de usuario**. Si crea una directiva de usuario, necesitará tener acceso a las cuentas de usuario correspondientes (desde la pestaña **Usuarios**) y asignar la nueva directiva a dichos usuarios.

</div>

<div>

## <a name="step-3-configuring-the-exchangearchivingpolicy-property"></a>Paso 3: configurar la propiedad ExchangeArchivingPolicy

Si Lync Server 2013 y Exchange 2013 se encuentran en diferentes bosques, no basta con que simplemente habilite el archivado de Exchange en la configuración de archivado; eso no hará que los mensajes instantáneos y las transcripciones de conferencias web se archiven en Exchange. En su lugar, también debe configurar la propiedad ExchangeArchivingPolicy en cada una de las cuentas de usuario de Lync Server relevantes. Esta propiedad se puede establecer en uno de los cuatro valores posibles:

1.  No inicializados. Indica que el archivado se basará en la configuración de conservación local configurada para el buzón del usuario de Exchange. Si no se ha habilitado la retención local en el buzón del usuario, el usuario tendrá su mensajería y sus expedientes de conferencia web archivados en Lync Server.

2.  **UseLyncArchivingPolicy**. Indica que la mensajería instantánea y las transcripciones de conferencias web del usuario deben archivarse en Lync Server en lugar de en Exchange.

3.  **NoArchiving**. Indica que las transcripciones de mensajería instantánea y de las conferencias web no necesitan archivarse. Tenga en cuenta que esta configuración sobrescribe las directivas de archivado de Lync Server asignadas al usuario.

4.  **ArchivingToExchange**. Indica que la mensajería instantánea del usuario y las transcripciones de conferencias web deberían archivarse en Exchange independientemente de la configuración de retención local que tenga (o no) se haya asignado al buzón del usuario.

Por ejemplo, para configurar una cuenta de usuario de modo que la mensajería instantánea y las transcripciones de conferencias web se archiven siempre a Exchange, puede usar un comando similar a este en el shell de administración de Lync Server:

    Set-CsUser -Identity "Ken Myer" -ExchangeArchivingPolicy ArchivingToExchange

Si desea establecer la misma directiva de archivado para un grupo de usuarios (por ejemplo, todos los usuarios hospedados en un Grupo de registradores específico), utilice un comando similar al siguiente:

    Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.litwareinc.com"} | Set-CsUser -ExchangeArchivingPolicy ArchivingToExchange

Tenga en cuenta que debe usar el shell de administración de Lync Server (y Windows PowerShell) para configurar el valor de la propiedad ExchangeArchivingPolicy. Esta propiedad no se expone a los administradores en el panel de control de Lync Server.

Si desea ver una lista de los usuarios a los que se ha asignado una directiva de archivado específica, use un comando similar al siguiente, que devuelve el nombre para mostrar de Active Directory de todos los usuarios para los que se ha establecido la propiedad ExchangeArchivingPolicy como Uninitialized:

    Get-CsUser | Where-Object {$_.ExchangeArchivingPolicy -eq "Uninitialized"} | Select-Object DisplayName

Del mismo modo, este comando devuelve el nombre para mostrar de los usuarios que no tienen la propiedad ExchangeArchivingPolicy establecida como UseLyncArchivingPolicy:

    Get-CsUser | Where-Object {$_.ExchangeArchivingPolicy -ne "UseLyncArchivingPolicy"} | Select-Object DisplayName

</div>

</div>

<span> </span>

</div>

</div>

</div>

