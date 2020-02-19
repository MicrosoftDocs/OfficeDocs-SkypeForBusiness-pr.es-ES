---
title: 'Lync Server 2013: Cómo funciona el archivado'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: How Archiving works
ms:assetid: 536a52a9-cfb7-4392-9620-ffc5b319b31b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204900(v=OCS.15)
ms:contentKeyID: 48184174
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 587405b686832aa3240754575962bf8830181a03
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138001"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="how-archiving-works-in-lync-server-2013"></a>Cómo funciona el archivado en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-02-04_

El archivado de Lync Server 2013 proporciona opciones para ayudarle a satisfacer sus necesidades de cumplimiento. Para implementarla y mantenerla de manera que se adapte mejor a los requisitos de su organización, debe comprender:

  - La información que se puede archivar.

  - Cómo habilitar y deshabilitar el archivado en su implementación.

  - Las opciones de archivado que se pueden configurar para controlar cómo se implementa el archivado.

<div>

## <a name="what-information-can-be-archived"></a>¿Qué información puede archivarse?

Se pueden archivar los siguientes tipos de contenido:

  - Mensajes instantáneos de punto a punto

  - Conferencias (reuniones), que son mensajes instantáneos con varios participantes

  - Contenido de conferencias, como contenido que se carga (por ejemplo, documentos de la reunión) y contenido relacionado con el evento (por ejemplo, los usuarios que se unen o abandonan el evento, la carga de recursos compartidos y cambios en la visibilidad)

  - Pizarras y sondeos los compartidos durante una conferencia

No se almacenan los tipos de contenido siguientes:

  - Transferencias de archivos de punto a punto

  - Audio y vídeo para conferencias y mensajes instantáneos de punto a punto

  - Escritorio y uso compartido de aplicaciones para conferencias y mensajes instantáneos de punto a punto

Lync Server tampoco archiva conversaciones de chat persistente. Para archivar conversaciones de chat persistente, debe habilitar y configurar el servicio de cumplimiento, que es un componente que se puede implementar con Microsoft Lync Server 2013, el servidor de chat persistente. Para obtener más información, consulte [Planning for persistent chat Server in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) en la documentación referente a la planeación.

</div>

<div>

## <a name="how-do-i-start-using-archiving"></a>¿Cómo empezar a usar el archivado?

El archivado se instala automáticamente en cada servidor front-end al implementar el servidor, pero el archivado no está habilitado hasta que se configura. La forma de configurar viene determinada por la forma de implementar el archivado:

  - **Archivado con la integración de Microsoft Exchange.** Si tiene usuarios hospedados en Exchange 2013 y sus buzones se han colocado en conservación local, puede seleccionar la opción de integrar el almacenamiento de Lync Server 2013 con el almacenamiento de Exchange. Si elige la opción de integración de Microsoft Exchange, use las directivas y configuraciones de Exchange 2013 para controlar el archivado de los datos de Lync Server 2013 para esos usuarios.

  - **Archivado mediante las bases de datos de archivado de Lync Server.** Si tiene usuarios que no están hospedados en Exchange 2013 o que no tienen buzones en conservación local, o si no desea usar la integración de Microsoft Exchange para alguno o todos los usuarios de la implementación, puede implementar las bases de datos de archivado de Lync Server con SQL Server.  para almacenar datos de archivado para esos usuarios. En este caso, las directivas y configuraciones de archivado de Lync Server 2013 determinan si el archivado está habilitado y cómo se implementa. Para usar Lync Server 2013, debe agregar las bases de datos de SQL Server adecuadas a la topología y publicar la topología.

<div>

## <a name="archiving-setup-when-using-microsoft-exchange-integration"></a>Configuración de archivado al usar la integración de Microsoft Exchange

Si los usuarios están hospedados en Exchange 2013 y sus buzones se han puesto en conservación local, puede elegir la opción de **integración de Microsoft Exchange** (tal y como se describe más adelante en esta sección) para archivar Lync Server 2013 para esos usuarios y, a continuación, controlar el archivado para esos usuarios especificando la configuración y las directivas de conservación local de Exchange, así como las configuraciones de Lync Server para controlar lo siguiente:

  - Si desea archivar MI, conferencias o ambas.

  - Si se va a implementar el modo crítico para la implementación de Lync Server.

  - Selección de la opción de integración de Microsoft Exchange para usar Exchange 2013 para el almacenamiento de datos archivados.

Estas opciones de configuración de archivado de Lync Server 2013 se describen más adelante en esta sección. Para obtener información sobre cómo configurar las directivas y configuraciones de conservación local de Exchange para admitir el archivado, consulte la documentación del producto de Exchange 2013.

</div>

<div>

## <a name="archiving-setup-when-using-lync-server-archiving-database-storage"></a>Configuración de archivado con almacenamiento de base de datos de archivado de Lync Server

Si desea usar las bases de datos de archivado de Lync Server (con bases de datos de SQL Server) para archivar datos de los usuarios de la implementación, puede configurar las directivas de archivado de Lync Server para controlar si el archivado está habilitado para esos usuarios. En cada directiva de archivado, puede activar o desactivar el archivado para una o ambas de las siguientes opciones:

  - Comunicaciones internas

  - Comunicaciones externas

De forma predeterminada, el archivado no está habilitado para las comunicaciones internas o externas en ninguna directiva de archivado de Lync Server. Puede habilitar y deshabilitar las comunicaciones mediante el panel de control de Lync Server 2013 o el uso de cmdlets en el shell de administración de Lync Server 2013.

Las directivas de archivado 2013 de Lync Server incluyen las siguientes:

  - **Directiva global de archivado**. Esta es la directiva de archivado predeterminada y se aplica a la implementación completa. Se crea al implementar Lync Server 2013 y, de forma predeterminada, deshabilita el archivado para las comunicaciones internas y externas. No se puede eliminar esta directiva. Si elige la opción Eliminar, la directiva global se restablece a la configuración predeterminada.

  - **Directiva de archivado del sitio**. Si lo desea, puede activar o desactivar el archivado para uno o más sitios específicos creando y configurando una directiva de archivado de nivel de sitio para el sitio. Cuando crea una directiva de archivado de nivel de sitio, de forma predeterminada, el archivado no está habilitado. Puede eliminar cualquier directiva de archivado de nivel de sitio que cree. Una directiva de archivado de nivel de sitio reemplaza la directiva global, pero solo para el sitio especificado en la directiva. Por ejemplo, si habilita el archivado para comunicaciones internas y externas en la directiva global y crea una directiva de sitio en la que deshabilita el archivado para las comunicaciones externas, solo se archivarían las comunicaciones internas de ese sitio.

  - **Directiva de archivado de usuario**. Si lo desea, puede activar o desactivar el archivado para uno o más usuarios específicos y grupos de usuarios creando, configurando y aplicando una directiva de archivado de nivel de usuario para los grupos de usuario y los usuarios especificados. Cuando crea una directiva de archivado de nivel de usuario, de forma predeterminada, el archivado no está habilitado. Puede eliminar cualquier directiva de archivado de nivel de usuario que cree y puede cambiar a qué usuarios y grupos de usuarios se aplica la directiva de archivado. Una directiva de archivado de nivel de usuario reemplaza la directiva global y las directivas de cualquier sitio, pero solo para los usuarios y grupos de usuario a quienes se aplica la directiva. Por ejemplo, si deshabilita el archivado para comunicaciones internas y externas en la directiva global, crea una directiva de nivel de sitio en la que habilita el archivado para comunicaciones internas y externas y, a continuación, crea una directiva de nivel de usuario en la que deshabilita el archivado para las comunicaciones externas, las comunicaciones se archivan para las comunicaciones internas y externas para todos los usuarios del sitio, excepto para los usuarios a los que se aplica la directiva de nivel de usuario, para quienes se archivan solo las comunicaciones internas.

Para obtener más información sobre cómo configurar las directivas de archivado iniciales al implementar el archivado, consulte [Configuring and Assigning policies in Lync Server 2013](lync-server-2013-configuring-and-assigning-archiving-policies.md) en la documentación sobre implementación. Para obtener información detallada sobre cómo usar las directivas de archivado para habilitar y deshabilitar las comunicaciones tras la implementación, consulte [Managing The archiving of Internal and external Communications in Lync Server 2013](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md) en la documentación de operaciones.

<div>


> [!NOTE]  
> Si implementa las bases de datos de archivado de Lync Server 2013 y habilita la integración de Microsoft Exchange, las directivas de Exchange 2013 invalidan las directivas de archivado de Lync Server, pero solo para los usuarios hospedados en Exchange 2013 y cuyos buzones se han puesto en conservación local . El archivado de Lync depende solo de la Directiva de conservación local de Microsoft Exchange.



</div>

</div>

<div>

## <a name="what-options-do-i-have-for-configuring-archiving"></a>¿Qué opciones tengo para la configuración del archivado?

Además de usar directivas y habilitar y deshabilitar el archivado, tiene otras opciones de archivado que se pueden configurar para toda la implementación y, opcionalmente, para grupos y sitios específicos. Puede controlar la mayoría de las opciones de archivado con una o varias configuraciones de archivado, que están disponibles en el panel de control de Lync Server 2013, pero también tienen otra opción que solo está disponible para la configuración mediante el shell de administración de Lync Server 2013.

<div>

## <a name="archiving-configuration-options-available-in-lync-server-2013-control-panel"></a>Opciones de configuración de archivado disponibles en el Panel de Control de Lync Server 2013

Cada configuración de archivado proporciona las siguientes opciones:

La configuración de nivel global se crea automáticamente cuando implementa el archivado y puede configurarse, pero no eliminarse. Si selecciona la opción para eliminar la configuración global, la configuración se restablece a los valores predeterminados. Puede crear varias configuraciones de sitio y grupo que, junto con la configuración global, controlan la configuración de archivado. Para la configuración global y cada configuración de sitio y grupo, tiene las siguientes opciones:

  - Deshabilitar el archivado, habilitar el archivado solo para mensajería instantánea (MI) o habilitar el archivado de mensajería instantánea y conferencias.

  - Configure el modo crítico para bloquear las sesiones de mensajería instantánea y conferencias en caso de que se produzca un error en Lync Server. Entre los errores se encuentran los siguientes:
    
      - **Mi**. Un problema con el servicio de almacenamiento de Lync Server. En este caso, la mensajería instantánea se bloquea para usuarios que tienen el archivado habilitado.
    
      - **Conferencias**. Un error podría ser un recurso compartido de archivo no disponible o un problema con el servicio de almacenamiento. En este caso, todas las conferencias activas alojadas en el grupo de servidores en el momento del error se cambian al modo restringido y no se puede activar conferencias nuevas.
    
    Tanto el servicio de mensajería instantánea como de conferencias se recuperan automáticamente después de que se corrigen los errores.

  - Especifique el uso de la integración de Microsoft Exchange Server 2013 para usar Exchange 2013 para el almacenamiento de datos archivados, en lugar de configurar bases de datos de SQL Server independientes para el almacenamiento de datos de archivado de Lync Server 2013.

  - Configurar las opciones de depuración para los datos archivados. Esto incluye indicar cuándo se deben purgar los datos archivados, que puede ser una de las siguientes opciones:
    
      - Después de un número determinado de días que especifique
    
      - Una vez que se han exportado los datos de archivado (lo que incluye los datos cargados en Exchange, si habilita la integración de Microsoft Exchange).
    
    <div>
    

    > [!NOTE]  
    > Si habilita la integración de Microsoft Exchange, la depuración para usuarios hospedados en Exchange 2013 y con sus buzones en conservación local se controla mediante Exchange. La única calificación es para los archivos de conferencia, que se almacenan en el recurso compartido de archivos de Lync Server. Estos archivos se purgan del recurso compartido de solo después de que los archivos se hayan exportado (cargado a Exchange), si selecciona la opción para purgar datos después de que se exporten los datos de archivado o después de un número máximo especificado de días, si especifica un número máximo de días para la retención.

    
    </div>

De forma predeterminada, no hay opciones de archivado habilitadas. Puede administrar las configuraciones de archivado con el panel de control 2013 de Lync Server.

Puede especificar las siguientes configuraciones de archivado:

  - **Configuración de archivado global**. Esta es la configuración de archivado predeterminada y se aplica a la implementación completa. Se crea al implementar Lync Server 2013 y, de forma predeterminada, no habilita la funcionalidad de archivado. Puede modificar la configuración global, pero no la puede eliminar. Si elige la opción de eliminar la configuración, la configuración global se restablece a la configuración predeterminada.

  - **Configuración de archivado de sitio**. Si lo desea, puede configurar el archivado para uno o más sitios específicos creando y estableciendo una configuración de archivado de nivel de sitio para un sitio individual. Una configuración de archivado de nivel de sitio existe solo si la crea. Puede modificar o eliminar cualquier configuración de archivado de nivel de sitio. Una configuración de archivado de nivel de sitio reemplaza la configuración global, pero solo para el sitio especificado en la configuración de nivel de sitio. Por ejemplo, si habilita el archivado de mensajería instantánea exclusivamente en la configuración global y crea una configuración de sitio en la que habilita el archivado de mensajería instantánea y conferencias, las conferencias podrían archivarse solo para el sitio, no para el resto de la organización.

  - **Configuración de archivado de grupo**. Si lo desea, puede especificar la configuración de archivado para uno o más grupos específicos creando y estableciendo una configuración de nivel de grupo para el grupo de servidores individual. Una configuración de archivado de nivel de grupo existe solo si la crea. Puede modificar y eliminar cualquier configuración de archivado de nivel de grupo. Una configuración de archivado de nivel de grupo reemplaza la configuración global y la configuración de archivado de cualquier sitio que haya creado. Por ejemplo, si habilita el archivado de mensajería instantánea solo en la configuración global, crea una configuración de nivel de sitio en la que habilite el archivado de mensajería instantánea y conferencias para el sitio y, a continuación, crea una configuración de nivel de grupo en la que habilite el archivado solo para mensajería instantánea, las comunicaciones se archivarán para mensajería instantánea y conferencias para todos los usuarios del sitio excepto los usuarios alojados en el grupo especificado en la configuración de nivel de grupo. Para todos los demás usuarios de la organización, se habilitará el archivado solo para mensajería instantánea.

Para obtener más información sobre cómo configurar las configuraciones iniciales de archivado al implementar el archivado, consulte [Configuring archiving Options in Lync Server 2013](lync-server-2013-configuring-archiving-options.md) en la documentación sobre implementación. Para obtener información detallada sobre cómo usar las directivas de archivado para habilitar y deshabilitar las comunicaciones tras la implementación, consulte [Managing archiving Configurations in Lync Server 2013 for your Organization, Sites, and pools](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md) en la documentación de operaciones.

</div>

<div>

## <a name="archiving-options-available-only-in-windows-powershell"></a>Opciones de archivado disponibles solo en Windows PowerShell

Mediante el shell de administración de Lync Server 2013, puede usar cmdlets para implementar opciones que no están disponibles en el panel de control de Lync Server 2013. Estas opciones incluyen lo siguiente:

  - **Archivar mensajes duplicados**. Para más información, vea [New-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsArchivingConfiguration) y [Set-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsArchivingConfiguration) en la documentación de operaciones.

  - **Exportar datos archivados**. Para más información, vea [Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData)

</div>

</div>

</div>

<div>

## <a name="how-do-i-access-archived-data"></a>¿Cómo se puede acceder a datos archivados?

El acceso a los datos archivados depende de dónde se almacenan los datos:

  - **Almacenamiento de Microsoft Exchange**. Si elige la opción de integración de Exchange, Lync Server deposita el contenido de archivado en el almacén de Exchange 2013 para todos los usuarios hospedados en Exchange 2013 y cuyos buzones se han puesto en conservación local. Los datos archivados se almacenan en la carpeta elementos recuperables de los buzones de usuario, que suele ser invisible para los usuarios, y solo los usuarios pueden buscar en ellos un rol de **Administración de detección** de Exchange. Exchange permite la búsqueda y detección federadas, junto con SharePoint, si se implementa. Para obtener más información sobre el almacenamiento, la retención y la detección de datos almacenados en Exchange, consulte la documentación de Exchange 2013 y SharePoint.

  - **Almacenamiento de Lync Server.** Si configura las bases de datos de archivado de Lync Server 2013 para el almacenamiento de datos de Lync Server, el contenido de archivado de los depósitos de Lync Server en las bases de datos de archivado de Lync Server (bases de datos de SQL Server) para los usuarios no hospedados en Exchange 2013 y a los que no se hayan puesto en sus buzones Conservación local. Estos datos no pueden buscarse, pero se pueden exportar a formatos que se pueden buscar mediante otras herramientas. Para obtener información detallada sobre cómo exportar datos almacenados en bases de datos de archivado, consulte [exportar datos archivados desde Lync Server 2013](lync-server-2013-exporting-archived-data.md) en la documentación de operaciones.

Para obtener más información acerca de cómo Lync Server 2013 y Exchange 2013 funcionan conjuntamente, consulte [Exchange Server and SharePoint Integration support in Lync server 2013](lync-server-2013-exchange-and-sharepoint-integration-support.md) en la documentación sobre compatibilidad.

</div>

</div>

<span> </span>

</div>

</div>

</div>

