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
ms.openlocfilehash: ca026dcfb9b994353de139b6e10ecd419c9dd165
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738940"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="how-archiving-works-in-lync-server-2013"></a>Cómo funciona el archivado en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-02-04_

Lync Server 2013 archiving ofrece opciones para ayudarle a satisfacer sus necesidades de cumplimiento. Para implementar y mantenerla de la manera que más se adapte a los requisitos de su organización, debe comprender lo siguiente:

  - Qué información se puede archivar.

  - Cómo habilitar y deshabilitar el archivado en la implementación.

  - Las opciones de archivado que se pueden configurar para controlar cómo se implementa el archivado.

<div>

## <a name="what-information-can-be-archived"></a>¿Qué información se puede archivar?

Se pueden archivar los siguientes tipos de contenido:

  - Mensajes instantáneos de punto a punto

  - Conferencias (reuniones), que son mensajes instantáneos con varios participantes

  - Contenido de conferencias, como contenido que se carga (por ejemplo, documentos de la reunión) y contenido relacionado con el evento (por ejemplo, los usuarios que se unen o abandonan el evento, la carga de recursos compartidos y los cambios en la visibilidad)

  - Pizarras y sondeos compartidos durante una conferencia

Los siguientes tipos de contenido no se archivan:

  - Transferencias de archivos de punto a punto

  - Audio o vídeo para conferencias y mensajes instantáneos de punto a punto

  - Escritorio y uso compartido de aplicaciones para conferencias y mensajes instantáneos de punto a punto

Lync Server tampoco archiva conversaciones de chat persistentes. Para archivar conversaciones de chat persistentes, debe habilitar y configurar el servicio de cumplimiento, que es un componente que se puede implementar con Microsoft Lync Server 2013, servidor de chat persistente. Para obtener más información, vea [planeación de un servidor de chat persistente en Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) en la documentación de planeación.

</div>

<div>

## <a name="how-do-i-start-using-archiving"></a>¿Cómo empiezo a usar el archivado?

El archivado se instala automáticamente en cada servidor front-end al implementar el servidor, pero el archivado no está habilitado hasta que lo configure. La forma en que la configure está determinada por la forma en que implementa el archivado:

  - **Archivar con la integración de Microsoft Exchange.** Si tiene usuarios alojados en Exchange 2013 y sus buzones se han colocado en conservación local, puede seleccionar la opción para integrar el almacenamiento de Lync Server 2013 con almacenamiento de Exchange. Si elige la opción de integración de Microsoft Exchange, usará las directivas y configuraciones de Exchange 2013 para controlar el archivado de datos de Lync Server 2013 para esos usuarios.

  - **Archivar con bases de datos de archivado de Lync Server.** Si tiene usuarios que no están alojados en Exchange 2013 o que no han puesto sus buzones en conservación local, o si no desea usar la integración de Microsoft Exchange para ninguno o todos los usuarios de su implementación, puede implementar bases de datos de archivado de Lync Server con SQL Server  para almacenar los datos de archivado de esos usuarios. En este caso, las directivas de archivado y las configuraciones de Lync Server 2013 determinan si el archivado está habilitado y cómo se implementa. Para usar Lync Server 2013, debe agregar las bases de datos de SQL Server apropiadas a su topología y publicar la topología.

<div>

## <a name="archiving-setup-when-using-microsoft-exchange-integration"></a>Archivar la configuración al usar la integración de Microsoft Exchange

Si los usuarios están alojados en Exchange 2013 y sus buzones se han puesto en conservación local, puede elegir la opción de **integración de Microsoft Exchange** (según se describe más adelante en esta sección) para archivar Lync Server 2013 para esos usuarios y, a continuación, controlar el archivado de esos usuarios especificando la configuración y las directivas de retención local de Exchange, así como las configuraciones de Lync Server, para controlar lo siguiente:

  - Si deseas archivar mi, conferencia o ambos.

  - Si desea implementar el modo crítico para su implementación de Lync Server.

  - Selección de la opción de integración de Microsoft Exchange para usar Exchange 2013 para el almacenamiento de datos archivados.

Estas opciones de configuración del archivado de Lync Server 2013 se describen más adelante en esta sección. Para obtener información sobre cómo configurar las directivas y la configuración de retención local de Exchange para admitir el archivado, consulte la documentación del producto Exchange 2013.

</div>

<div>

## <a name="archiving-setup-when-using-lync-server-archiving-database-storage"></a>Archivar la configuración al usar el almacenamiento de base de datos de archivado de Lync Server

Si desea usar las bases de datos de archivado de Lync Server (con bases de datos de SQL Server) para archivar los datos de los usuarios de su implementación, puede configurar las directivas de archivado de Lync Server para controlar si el archivado está habilitado para esos usuarios. En cada directiva de archivado, puede habilitar o deshabilitar el archivado para cualquiera de las siguientes opciones:

  - Comunicaciones internas

  - Comunicaciones externas

De forma predeterminada, el archivado no está habilitado para las comunicaciones internas ni las comunicaciones externas en ninguna directiva de archivado de Lync Server. Las comunicaciones se habilitan y deshabilitan mediante el panel de control de Lync Server 2013 o mediante cmdlets en el shell de administración de Lync Server 2013.

Entre las directivas de archivado de Lync Server 2013 se incluyen las siguientes:

  - **Directiva de archivado global**. Esta es la Directiva de archivado predeterminada y se aplica a toda la implementación. Se crea al implementar Lync Server 2013 y, de forma predeterminada, deshabilita el archivado para las comunicaciones internas y externas. No puede eliminar esta Directiva. Si elige la opción eliminar, la directiva global se restablece a la configuración predeterminada.

  - **Directiva de archivado de sitio**. De manera opcional, puede habilitar o deshabilitar el archivado de uno o varios sitios específicos creando y configurando una directiva de archivado de nivel de sitio para el sitio. Al crear una directiva de archivado de nivel de sitio, el archivado no está habilitado de forma predeterminada. Puede eliminar cualquier directiva de archivado de nivel de sitio que cree. Una directiva de archivado de nivel de sitio reemplaza la directiva global, pero solo para el sitio especificado en la Directiva. Por ejemplo, si habilita el archivado para las comunicaciones internas y externas en su directiva global y crea una directiva de sitio en la que deshabilite el archivado de las comunicaciones externas, solo se archivarán las comunicaciones internas de ese sitio.

  - **Directiva de archivado de usuario**. De manera opcional, puede habilitar o deshabilitar el archivado para uno o varios usuarios específicos y un grupo de usuarios creando, configurando y aplicando una directiva de archivado de nivel de usuario para los usuarios y grupos de usuarios especificados. Al crear una directiva de archivado de nivel de usuario, el archivado no está habilitado de forma predeterminada. Puede eliminar cualquier directiva de archivado de nivel de usuario que cree y puede cambiar los usuarios y el grupo de usuarios a los que se aplica la Directiva de archivado. Una directiva de archivado de nivel de usuario reemplaza la directiva global y las directivas del sitio, pero solo para los usuarios y grupos de usuarios a los que se aplica la Directiva. Por ejemplo, si deshabilita el archivado de las comunicaciones internas y externas en su directiva global, cree una directiva de nivel de sitio en la que habilitar el archivado para las comunicaciones internas y externas y, a continuación, cree una directiva de nivel de usuario en la que deshabilite Archivado para las comunicaciones externas, las comunicaciones se archivarán para las comunicaciones externas e internas de todos los usuarios del sitio, excepto en que, para los usuarios a los que usted aplica la Directiva de nivel de usuario, solo se archivarán las comunicaciones internas.

Para obtener detalles sobre cómo configurar las directivas de archivado iniciales al implementar el archivado, vea [configurar y asignar directivas de archivado en Lync Server 2013](lync-server-2013-configuring-and-assigning-archiving-policies.md) en la documentación de implementación. Para obtener detalles sobre cómo usar las directivas de archivado para habilitar y deshabilitar las comunicaciones después de la implementación, vea [administrar el archivado de comunicaciones internas y externas en Lync Server 2013](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md) en la documentación de operaciones.

<div>


> [!NOTE]  
> Si implementa las bases de datos de archivado de Lync Server 2013 y habilita la integración de Microsoft Exchange, las directivas de Exchange 2013 invalidarán las directivas de archivado de Lync Server, pero solo para los usuarios que estén alojados en Exchange 2013 y hayan puesto sus buzones en conservación local . El archivado de Lync depende solo de la Directiva de retención local de Microsoft Exchange.



</div>

</div>

<div>

## <a name="what-options-do-i-have-for-configuring-archiving"></a>¿Qué opciones tengo para configurar el archivado?

Además de usar directivas y habilitar y deshabilitar el archivado, tiene otras opciones de archivado que se pueden configurar para toda la implementación y, opcionalmente, para determinados sitios y grupos. Puede controlar la mayoría de las opciones de archivado mediante una o más configuraciones de archivado, que están disponibles en el panel de control de Lync Server 2013, pero también tienen otra opción que solo está disponible para la configuración con el shell de administración de Lync Server 2013.

<div>

## <a name="archiving-configuration-options-available-in-lync-server-2013-control-panel"></a>Opciones de configuración de archivado disponibles en el panel de control de Lync Server 2013

Cada configuración de archivado proporciona las siguientes opciones:

La configuración de nivel global se crea automáticamente al implementar el archivado y puede configurarse, pero no eliminarse. Si selecciona la opción para eliminar la configuración global, la configuración se restablecerá a los valores predeterminados. Puede crear varias configuraciones de sitios y grupos, junto con la configuración global, para controlar la configuración de archivado. Para la configuración global y cada configuración de sitios y grupos, tiene las siguientes opciones:

  - Deshabilite el archivado, habilite el archivado solo para mensajería instantánea (mi) o habilite el archivado de mensajes instantáneos y de conferencia.

  - Configure el modo crítico para bloquear las sesiones de mensajería instantánea y de conferencia en caso de que se produzca un error de Lync Server. Los errores pueden ser los siguientes:
    
      - **Mensajería instantánea**. Un problema con el servicio de almacenamiento de Lync Server. En este caso, la mensajería instantánea se bloquea para los usuarios que tienen el archivado habilitado.
    
      - **Conferencia**. Un error puede ser un recurso compartido de archivo no disponible o un problema con el servicio de almacenamiento. En este caso, todas las conferencias activas hospedadas en el grupo de servidores en el momento del error se cambian al modo restringido y no se puede activar conferencias nuevas.
    
    Tanto la mensajería instantánea como las conferencias se recuperan automáticamente después de que se corrigen los errores.

  - Especifique el uso de la integración de Microsoft Exchange Server 2013 para usar Exchange 2013 para el almacenamiento de datos archivados, en lugar de configurar bases de datos de SQL Server independientes para el almacenamiento de datos de archivado de Lync Server 2013.

  - Configure las opciones de depuración de datos archivados. Esto incluye especificar Cuándo purgar los datos archivados, lo que puede ser cualquiera de los siguientes:
    
      - Después de un número específico de días especificado
    
      - Después de exportar los datos de archivado (que incluye los datos que se han cargado en Exchange, si habilita la integración de Microsoft Exchange).
    
    <div>
    

    > [!NOTE]  
    > Si habilita la integración de Microsoft Exchange, la depuración para usuarios alojados en Exchange 2013 y con sus buzones en la conservación local está controlada por Exchange. La única calificación es para los archivos de conferencia, que se almacenan en el recurso compartido de archivos de Lync Server. These files are purged from the file share only after the files have been exported (uploaded to Exchange), if you select the option to purge data after the archiving data has been exported, or after the specified maximum number of days, if you specify a maximum number of days for retention.

    
    </div>

De forma predeterminada, no se habilitan las opciones de archivado. Puede administrar las configuraciones de archivado mediante el panel de control 2013 de Lync Server.

Puede especificar las siguientes configuraciones de archivado:

  - **Configuración global de archivado**. Esta es la configuración de archivado predeterminada y se aplica a toda la implementación. Se crea al implementar Lync Server 2013 y, de forma predeterminada, no habilita la funcionalidad de archivado. Puede modificar la configuración global, pero no puede eliminarla. Si elige la opción Eliminar para la configuración, la configuración global se restablecerá a la configuración predeterminada.

  - **Configuración de archivado del sitio**. De manera opcional, puede configurar el archivado para uno o más sitios específicos creando y configurando una configuración de archivado de nivel de sitio para un sitio individual. Solo existe una configuración de archivado de nivel de sitio si la crea. Puede modificar o eliminar cualquier configuración de archivado de nivel de sitio. Una configuración de archivado de nivel de sitio reemplaza la configuración global, pero solo para el sitio especificado en la configuración de nivel de sitio. Por ejemplo, si habilita el archivado solo para mensajería instantánea en su configuración global y crea una configuración de sitio en la que habilitar el archivado para mensajería instantánea y conferencias, las conferencias solo se archivarán en el sitio, no en el resto de la organización.

  - **Configuración de archivado del grupo**. De manera opcional, puede especificar la configuración de archivado para una o más agrupaciones específicas creando y configurando una configuración de nivel de grupo para cada grupo. Solo existe una configuración de archivado de nivel de grupo si la crea. Puede modificar y eliminar cualquier configuración de archivado de nivel de grupo. Una configuración de archivado de nivel de grupo reemplaza la configuración global y cualquier configuración de archivado de sitios que haya creado. Por ejemplo, si habilita el archivado solo para mensajería instantánea en la configuración global, cree una configuración de nivel de sitio en la que habilite el archivado para la mensajería instantánea y las conferencias para el sitio y, a continuación, cree una configuración de nivel de grupo en la que habilitar el archivado solo para MI, las comunicaciones se archivarán para mensajería instantánea y conferencias para todos los usuarios del sitio, excepto los usuarios alojados en el grupo especificado en la configuración de nivel de grupo. Para el resto de los usuarios de su organización, el archivado se habilitará solo para mensajería instantánea.

Para obtener detalles sobre cómo configurar las configuraciones de archivado iniciales al implementar el archivado, vea [configurar las opciones de archivado en Lync Server 2013](lync-server-2013-configuring-archiving-options.md) en la documentación de implementación. Para más información sobre cómo usar las directivas de archivado para habilitar y deshabilitar comunicaciones después de la implementación, vea [administrar las opciones de configuración de archivado en Lync Server 2013 para su organización, sitios y grupos](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md) en la documentación de operaciones.

</div>

<div>

## <a name="archiving-options-available-only-in-windows-powershell"></a>Opciones de archivado disponibles solo en Windows PowerShell

Mediante el shell de administración de Lync Server 2013, puede usar cmdlets para implementar opciones que no están disponibles en el panel de control de Lync Server 2013. Entre estas opciones se incluyen las siguientes:

  - **Archivar mensajes duplicados**. Para obtener más información, vea [New-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsArchivingConfiguration) y [set-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsArchivingConfiguration) en la documentación de operaciones.

  - **Exportar datos archivados**. Para obtener más información, consulte [exportar-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData)

</div>

</div>

</div>

<div>

## <a name="how-do-i-access-archived-data"></a>¿Cómo puedo obtener acceso a los datos archivados?

El acceso a los datos archivados depende de dónde se almacenan los datos:

  - **Almacenamiento de Microsoft Exchange**. Si elige la opción de integración de Exchange, Lync Server deposita el contenido de archivado en el almacén de 2013 de Exchange para todos los usuarios alojados en Exchange 2013 y que tienen sus buzones en conservación local. Los datos archivados se almacenan en buzones de usuario carpeta elementos recuperables, que generalmente es invisible para los usuarios, y solo los usuarios con el rol de **Administración de detección** de Exchange pueden buscarlos. Exchange permite la búsqueda y detección federadas, junto con SharePoint, si se ha implementado. Para obtener más información sobre el almacenamiento, la retención y el descubrimiento de datos almacenados en Exchange, consulte la documentación de Exchange 2013 y SharePoint.

  - **Almacenamiento de Lync Server**. Si configura las bases de datos de archivado de Lync Server 2013 para el almacenamiento de datos de Lync Server, los depósitos de Lync Server archivan el contenido de las bases de datos de archivado de Lync Server (bases de datos de SQL Server) para los usuarios que no estén alojados en Exchange 2013 y que no hayan puesto sus buzones Conservación local. This data is not searchable, but it can be exported to formats that are searchable using other tools. Para obtener más información sobre cómo exportar datos almacenados en bases de datos de archivado, consulte [exportar datos archivados de Lync Server 2013](lync-server-2013-exporting-archived-data.md) en la documentación de operaciones.

Para obtener más información acerca de cómo Lync Server 2013 y Exchange 2013 funcionan conjuntamente, consulte [compatibilidad de la integración de Exchange Server y SharePoint en Lync server 2013](lync-server-2013-exchange-and-sharepoint-integration-support.md) en la documentación de soporte técnico.

</div>

</div>

<span> </span>

</div>

</div>

</div>

