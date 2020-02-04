---
title: 'Lync Server 2013: crear una configuración de archivado para administrar el archivado de grupos o sitios específicos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Creating an Archiving configuration to manage Archiving for specific sites or pools
ms:assetid: c5c864a6-96c7-4bbb-ab7c-61eb1744246c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205251(v=OCS.15)
ms:contentKeyID: 48185361
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3b0495a15d19adba9ac21fb7817347a16b78bc13
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762749"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="creating-an-archiving-configuration-in-lync-server-2013-to-manage-archiving-for-specific-sites-or-pools"></a>Creación de una configuración de archivado en Lync Server 2013 para administrar el archivado de sitios o grupos específicos

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-23_

En el panel de control de Lync Server 2013, use las configuraciones de archivado para controlar cómo se implementa el archivado en su implementación. Esto incluye las siguientes configuraciones de archivado:

  - Una configuración global que se crea de forma predeterminada al implementar Lync Server 2013.

  - Configuraciones de nivel de sitio y de grupo opcionales que puede crear y usar para especificar cómo se implementa el archivado para grupos o sitios específicos.

Inicialmente, debe configurar las configuraciones de archivado al implementar el archivado, pero puede cambiar, agregar y eliminar configuraciones después de la implementación. Para obtener detalles sobre cómo se implementan las configuraciones de archivado, incluidas las opciones que puede especificar y la jerarquía de las configuraciones de archivado, consulte [Cómo funciona el archivado en Lync Server 2013](lync-server-2013-how-archiving-works.md) en la documentación de planeación, la documentación de implementación o la documentación de operaciones.

<div>


> [!NOTE]  
> Para usar el archivado, debe configurar las directivas de archivado para especificar si desea habilitar el archivado de las comunicaciones internas, de las comunicaciones externas o de ambos para los usuarios alojados en Lync Server 2013. De forma predeterminada, el archivado no está habilitado para las comunicaciones internas o externas. Antes de habilitar el archivado en cualquier directiva, debe especificar las configuraciones de archivado apropiadas para su implementación y, opcionalmente, para determinados sitios y grupos, tal y como se describe en esta sección. Para obtener más información sobre cómo habilitar el archivado, vea <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">configurar y asignar directivas de archivado en Lync Server 2013</A> en la documentación de implementación.<BR>Si decide que después de implementar el archivado desea usar la integración de Microsoft Exchange para almacenar datos y archivos en servidores de Exchange 2013 y todos los usuarios están alojados en los servidores de Exchange 2013, debe quitar la configuración de la base de datos de SQL Server desde su topología. Para ello, debe usar el generador de topología. Para obtener más información, vea <A href="lync-server-2013-changing-archiving-database-options.md">cambiar las opciones de base de datos de archivado en Lync Server 2013</A> en la documentación de operaciones.



</div>

<div>

## <a name="to-create-an-archiving-configuration-for-a-site-or-pool"></a>Para crear una configuración de archivado para un sitio o grupo de servidores

1.  Desde una cuenta de usuario que se asigne al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Supervisión y archivado** y, después, en **Configuración de archivado**.

4.  En la página **Configuración de archivado**, haga clic en **Nuevo** y haga una de las siguientes acciones:
    
      - Para crear una configuración de archivado de sitio, haga clic en **configuración del sitio** y, a continuación, en **seleccionar un sitio**, seleccione el sitio que se va a configurar para el archivado.
    
      - Para crear una configuración de archivado de grupo, haga clic en **configuración del grupo** y, a continuación, en **seleccionar un grupo**de servidores, seleccione el grupo de servidores que se va a configurar para el archivado.

5.  En **Nueva configuración de archivado**, vaya al cuadro de lista desplegable **Configuración de archivado** y siga uno de estos procedimientos:
    
      - Para habilitar el archivado solo para las sesiones de mensajería instantánea (MI), haga clic en **Archivar sesiones de mensajería instantánea (MI)**.
    
      - Para habilitar el archivado tanto para las sesiones de mensajería instantánea (MI) como para las conferencias web, haga clic en **Archivar sesiones de mensajería instantánea (MI) y conferencias web**.
    
      - A fin de deshabilitar el archivado de la directiva, haga clic en **Deshabilitar archivado**.

6.  Además, en **Nueva configuración de archivado**, haga lo siguiente:
    
      - Para bloquear la actividad cuando el archivado no está disponible, active la casilla **Bloquear sesiones de mensajería instantánea (MI) o de conferencias web si no se pueden archivar**.
    
      - Para usar Microsoft Exchange Server para almacenar datos de archivado, haga clic en la casilla de verificación **integración con Microsoft Exchange** .
    
      - Para habilitar la purga de datos, active la casilla **Habilitar purgado de los datos de archivado** y realice una de las siguientes acciones:
        
          - Para especificar la purga al transcurrir una cantidad de días determinada, haga clic en **Purgar los datos de archivado exportados y los datos de archivado almacenados tras la duración máxima (días)** y especifique la cantidad de días.
        
          - Para limitar la purga de los datos de archivado que se han exportado, haga clic en **Purgar solo datos de archivado exportados**.

7.  Haga clic en **Confirmar**.

</div>

<div>

## <a name="creating-archiving-configuration-settings-by-using-windows-powershell-cmdlets"></a>Creación de parámetros de configuración de archivado mediante cmdlets de Windows PowerShell

Los valores de configuración de archivado se pueden crear con Windows PowerShell y el cmdlet New-CsArchivingConfiguration. Este cmdlet se puede ejecutar desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para obtener más información sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server de Windows PowerShell "Inicio rápido: administrar Microsoft Lync Server [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)2010 mediante PowerShell remoto" en.

<div>

## <a name="to-create-a-new-collection-of-archiving-configuration-settings-for-a-site"></a>Para crear una nueva colección de parámetros de configuración de archivado para un sitio

  - El comando siguiente crea una colección de opciones de configuración de archivado para el sitio de Redmond:
    
        New-CsArchivingConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-create-a-new-collection-of-archiving-configuration-settings-that-only-allow-im-archiving"></a>Para crear una nueva colección de opciones de configuración de archivado que solo permitan el archivado de mensajes instantáneos

  - Dado que, en el comando anterior, no se especificaron parámetros (además del parámetro de identidad obligatorio), la nueva colección de valores de configuración usará los valores predeterminados para todas sus propiedades. Para crear una configuración que use otros valores de propiedad, basta con incluir el parámetro y el valor correspondiente adecuados. Por ejemplo, para crear una colección de opciones de configuración de archivado que permitan el archivado de sesiones de mensajería instantánea, de forma predeterminada, use únicamente un comando como este:
    
        New-CsArchivingConfiguration -Identity "site:Redmond" -EnableArchiving "ImOnly"

</div>

<div>

## <a name="to-specify-multiple-property-values-when-creating-archiving-configuration-settings"></a>Para especificar varios valores de propiedad al crear parámetros de configuración de archivado

  - Puede incluir varios parámetros para modificar varios valores de propiedad. Por ejemplo, este comando define la nueva configuración para archivar las sesiones de mensajería instantánea y bloquear la mensajería instantánea si el servicio de archivado no está disponible:
    
        New-CsArchivingConfiguration -Identity "site:Redmond" -EnableArchiving "ImOnly" -BlockOnArchiveFailure $True

</div>

Para obtener más información, vea el tema de ayuda sobre el cmdlet [New-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsArchivingConfiguration) .

</div>

<div>

## <a name="see-also"></a>Vea también


[Cómo funciona el archivado en Lync Server 2013](lync-server-2013-how-archiving-works.md)  


[Administrar las opciones de configuración de archivado en Lync Server 2013 para su organización, sitios y grupos](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

