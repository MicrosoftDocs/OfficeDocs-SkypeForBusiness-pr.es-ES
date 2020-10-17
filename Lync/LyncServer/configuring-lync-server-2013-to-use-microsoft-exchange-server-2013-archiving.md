---
title: Configurar Lync Server 2013 para usar el archivado de Microsoft Exchange Server 2013
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
ms.openlocfilehash: b6f557c95b9bf706b3a38b51bdbea4fea156b314
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48503167"
---
# <a name="configuring-microsoft-lync-server-2013-to-use-microsoft-exchange-server-2013-archiving"></a>Configuración de Microsoft Lync Server 2013 para usar el archivado de Microsoft Exchange Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-06-24_

Microsoft Lync Server 2013 ofrece a los administradores la opción de hacer que las transcripciones de mensajería instantánea y de conferencias web se archiven en un buzón de correo de Microsoft Exchange Server 2013 de un usuario en lugar de una base de datos de SQL Server. Si se habilita esta opción, las transcripciones se escribirán en la carpeta Purga del buzón del usuario. La carpeta Purga es una carpeta oculta que se encuentra en la carpeta Elementos recuperables. Aunque esta carpeta no es visible para los usuarios finales, el motor de búsqueda de Exchange indiza la carpeta y se puede detectar mediante la búsqueda en buzones de Exchange o Microsoft SharePoint Server 2013. Debido a que la información se almacena en la misma carpeta que usa la característica de retención de In-Place de Exchange (responsable de archivar el correo electrónico y otras comunicaciones de Exchange), los administradores pueden usar una única herramienta para buscar todas las comunicaciones electrónicas archivadas para un usuario.

<div>


> [!IMPORTANT]  
> Para deshabilitar por completo el archivado de la conversación de Lync, también debe deshabilitar el historial de conversaciones de Lync. Para obtener más información, vea los temas siguientes: <A href="lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md">Administración del archivado de comunicaciones internas y externas en Lync Server 2013</A>, <A href="https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy">New-CsClientPolicy</A>y <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy">set-CsClientPolicy</A>.



</div>

Para archivar transcripciones en Exchange 2013 debe empezar configurando la autenticación de servidor a servidor entre los dos servidores. Una vez implementada la autenticación de servidor a servidor, puede llevar a cabo las siguientes tareas en Microsoft Lync Server 2013 (tenga en cuenta que, según la configuración y la configuración, es posible que no necesite completar todas estas tareas):

1.  Habilite el archivado de Exchange modificando las opciones de configuración de archivado de Lync Server. Este paso es obligatorio para todas las implementaciones.

2.  Habilite el archivado de comunicaciones externas/internas de los usuarios. Este paso es obligatorio para todas las implementaciones.

3.  Configure la propiedad ExchangeArchivingPolicy para cada usuario. Este paso solo es necesario en Lync Server y Exchange se encuentran en bosques diferentes.

<div>

## <a name="step-1-enabling-exchange-archiving"></a>Paso 1: habilitar el archivado de Exchange

El archivado en Lync Server se administra principalmente mediante las opciones de configuración de archivado. Al instalar Lync Server 2013, se le asigna automáticamente una colección global única de estas opciones de configuración. (De manera opcional, los administradores pueden crear nuevas colecciones de configuraciones de archivado en el ámbito de sitio). De forma predeterminada, el archivado no está habilitado en la configuración global, ni está habilitado para el archivado de Exchange en esta configuración. Para poder usar los administradores de archivado de Exchange, debe configurar las propiedades EnableArchiving y EnableExchangeArchiving en estas opciones de configuración. La propiedad EnableArchiving se puede establecer en uno de estos tres valores posibles:

  - **Ninguno**. El archivado está deshabilitado. Este es el valor predeterminado. Si EnableArchiving se establece en None, no se archivará nada en la base de datos de archivado de Lync Server o en Exchange 2013.

  - **Solo**. Solo se archivarán las transcripciones de mensajería instantánea. Si está habilitado el archivado de Exchange, estas transcripciones se archivarán en Exchange 2013. Si el archivado de Exchange está deshabilitado, estas transcripciones se archivarán en Lync Server.

  - **ImAndWebConf**. Se archivarán las transcripciones de mensajería instantánea y de las conferencias web. Si está habilitado el archivado de Exchange, estas transcripciones se archivarán en Exchange 2013. Si el archivado de Exchange está deshabilitado, estas transcripciones se archivarán en Lync Server.

La propiedad EnableExchangeArchiving es un valor booleano: establezca EnableExchangeArchiving en true ($True) para habilitar el archivado de Exchange o establezca EnableExchangeArchiving en false ($False) para deshabilitar el archivado de Exchange. Por ejemplo, este comando habilita el archivado de transcripciones de mensajería instantánea y también permite archivado de Exchange:

    Set-CsArchivingConfiguration -Identity "global" -EnableArchiving ImOnly -EnableExchangeArchiving $True

Para deshabilitar el archivado de Exchange, use un comando similar al siguiente, que permite el archivado de mensajería instantánea pero deshabilita el archivado en Exchange (es decir, las transcripciones se archivarán en Lync Server):

    Set-CsArchivingConfiguration -Identity "global" -EnableArchiving ImOnly -EnableExchangeArchiving $False

<div>


> [!NOTE]  
> Si la propiedad EnableArchiving está establecida en None, Lync Server no archivará las transcripciones de mensajería instantánea y de conferencias web. En este caso, el servidor simplemente ignorará el valor configurado de la propiedad EnableExchangeArchiving.



</div>

El archivado de Exchange también se puede habilitar (o deshabilitar) mediante el panel de control de Lync Server. Para ello, lleve a cabo el procedimiento siguiente:

1.  En el Panel de control, haga clic en **Configuración y archivado** y, a continuación, en **Configuración de archivado**.

2.  En la pestaña **Configuración de archivado**, haga doble clic en la recopilación de opciones de archivado que desea modificar (por ejemplo, la recopilación **Global**).

3.  En el panel **Editar configuración de archivado**, haga clic en la lista desplegable **Configuración de archivado** y seleccione **Archivar sesiones de mensajería instantánea** (para archivar solo las sesiones de mensajería instantánea) o **Archivar sesiones de mensajería instantánea y conferencias web** (para archivar tanto las sesiones de conferencia web y mensajería instantánea).

4.  Después de elegir los elementos que se van a archivar, active la casilla **integración de Exchange Server** para habilitar el archivado de Exchange. Para deshabilitar el archivado de Exchange, desactive esta casilla.

<div>


> [!NOTE]  
> La casilla <STRONG>Integración con Exchange Server</STRONG> no estará disponible si la opción <STRONG>Configuración de archivado</STRONG> está configurada como <STRONG>Deshabilitar archivado</STRONG>. Primero debe habilitar el archivado y, a continuación, habilitar el archivado de Exchange.



</div>

Si Lync Server 2013 y Exchange 2013 están ubicados en el mismo bosque, el archivado para usuarios individuales (o al menos para usuarios que tienen cuentas de correo en Exchange 2013) se administra mediante las directivas de suspensión de Exchange In-Place. Si tiene usuarios hospedados en una versión anterior de Exchange, el archivado para esos usuarios se administrará con las directivas de archivado de Lync Server. Tenga en cuenta que solo los usuarios con cuentas en Exchange 2013 pueden archivar sus transcripciones de Lync en Exchange.

Si Lync Server 2013 y Exchange 2013 están ubicados en bosques diferentes, el archivado para usuarios individuales se administra configurando la propiedad ExchangeArchivingPolicy para cada cuenta de usuario individual. Vea el paso 3 para obtener más información.

</div>

<div>

## <a name="step-2-enabling-the-archiving-of-internal-andor-external-communications"></a>Paso 2: Habilitación del archivado de comunicaciones internas o externas

Una vez que haya habilitado el archivado (y el archivado de Exchange), debe modificar las directivas de archivado adecuadas para asegurarse de que las sesiones de usuario se archiven realmente. Tenga en cuenta que, al habilitar el archivado (paso 1), no se produce que Lync Server comience a archivar las transcripciones de mensajería instantánea y la conferencia Web. En su lugar, debe usar directivas de archivado para habilitar el archivado externo o interno. Al instalar Lync Server 2013, también se instala una única directiva de archivado global que contiene dos propiedades:

  - **ArchiveInternal**. Cuando se establece en True ($True), indica que solo se archivarán las sesiones de comunicaciones internas (solo las sesiones de los usuarios de su organización que dispongan de cuentas de Active Directory).

  - **ArchiveExternal**. Cuando se establece en True ($True), indica que solo se archivarán las sesiones de comunicaciones externas (sesiones en las que al menos usuario de su organización no disponga de cuenta de Active Directory).

De forma predeterminada, estos valores de propiedades están establecidos como False, lo que implica que no se archivan ni las sesiones de comunicaciones internas ni externas. Para modificar la directiva global, puede usar el shell de administración de Lync Server y el cmdlet Set-CsArchivingPolicy. El comando siguiente habilita el archivado de las sesiones de comunicaciones internas y externas:

    Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $True -ArchiveExternal $True

De forma alternativa, puede usar el cmdlet New-CsArchivingPolicy para crear una nueva directiva para el sitio o por usuario. Por ejemplo, este comando permite crear una directiva de archivado específica para un usuario con el nombre RedmondArchivingPolicy:

    New-CsArchivingPolicy -Identity "RedmondArchivingPolicy" -ArchiveInternal $True -ArchiveExternal $True

Si crea una directiva específica para un usuario, necesitará asignar dicha directiva a los usuarios correspondientes. Por ejemplo:

    Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName  "RedmondArchivingPolicy"

Las directivas de archivado también se pueden administrar mediante el panel de control de Lync Server. Desde el Panel de control, haga clic en **Supervisión  y archivado** y haga clic en **Directiva de archivado**. Para modificar una directiva existente, haga doble clic en la directiva (por ejemplo, Global) y, a continuación, en el panel **Editar directiva de archivado**, active o desactive las casillas **Archivar comunicaciones internas** o **Archivar comunicaciones externas** según sea necesario. Para crear una nueva Directiva de archivado, haga clic en **nuevo** y, a continuación, seleccione **Directiva de sitio** o **Directiva de usuario**. Si crea una nueva directiva de usuario, deberá tener acceso a las cuentas de usuario correspondientes (desde la pestaña **Usuarios**) y asignar dichos usuarios a la nueva directiva.

</div>

<div>

## <a name="step-3-configuring-the-exchangearchivingpolicy-property"></a>Paso 3: Configuración de la propiedad ExchangeArchivingPolicy

Si Lync Server 2013 y Exchange 2013 están ubicados en bosques diferentes, no basta con habilitar el archivado de Exchange en las opciones de configuración de archivado; eso no provocará que se archiven las transcripciones de mensajería instantánea y de conferencias web en Exchange. En su lugar, también debe configurar la propiedad ExchangeArchivingPolicy en cada una de las cuentas de usuario de Lync Server relevantes. Esta propiedad puede establecerse con uno de los cuatro valores posibles:

1.  Sin inicializar. Indica que el archivado se basará en la configuración de retención de In-Place configurada para el buzón de Exchange del usuario; Si no se ha habilitado la retención de In-Place en el buzón del usuario, el usuario tendrá archivado sus expedientes de mensajería y conferencias web en Lync Server.

2.  **UseLyncArchivingPolicy**. Indica que la mensajería instantánea del usuario y las transcripciones de conferencias web deben archivarse en Lync Server en lugar de en Exchange.

3.  No **archivar**. Indica que las transcripciones de mensajería instantánea y de las conferencias web no deben archivarse. Tenga en cuenta que esta configuración reemplaza cualquier directiva de archivado de Lync Server asignada al usuario.

4.  **ArchivingToExchange**. Indica que la mensajería instantánea del usuario y las transcripciones de conferencias web deben archivarse en Exchange independientemente de la configuración de retención de In-Place que se haya asignado (o no) al buzón del usuario.

Por ejemplo, para configurar una cuenta de usuario para que las transcripciones de mensajería instantánea y de conferencias web siempre se archiven en Exchange, puede usar un comando similar al siguiente desde el shell de administración de Lync Server:

    Set-CsUser -Identity "Ken Myer" -ExchangeArchivingPolicy ArchivingToExchange

Si desea establecer la misma directiva de archivado para un grupo de usuarios (por ejemplo, todos los usuarios hospedados en un Grupo de registradores específico), utilice un comando similar al siguiente:

    Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.litwareinc.com"} | Set-CsUser -ExchangeArchivingPolicy ArchivingToExchange

Tenga en cuenta que debe usar el shell de administración de Lync Server (y Windows PowerShell) para poder configurar el valor de la propiedad ExchangeArchivingPolicy. Esta propiedad no se expone a los administradores en el panel de control de Lync Server.

Si desea ver una lista de los usuarios a los que se ha asignado una directiva de archivado específica, utilice un comando similar al siguiente, que devuelve el nombre para mostrar de Active Directory de todos los usuarios para los que se ha establecido la propiedad ExchangeArchivingPolicy como Uninitialized:

    Get-CsUser | Where-Object {$_.ExchangeArchivingPolicy -eq "Uninitialized"} | Select-Object DisplayName

Del mismo modo, este comando devuelve el nombre para mostrar de los usuarios que no tienen la propiedad ExchangeArchivingPolicy establecida como UseLyncArchivingPolicy:

    Get-CsUser | Where-Object {$_.ExchangeArchivingPolicy -ne "UseLyncArchivingPolicy"} | Select-Object DisplayName

</div>

</div>

<span> </span>

</div>

</div>

</div>

