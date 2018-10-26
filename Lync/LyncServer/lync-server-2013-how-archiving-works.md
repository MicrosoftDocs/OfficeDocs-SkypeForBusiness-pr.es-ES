---
title: Cómo funciona el archivado en Lync Server 2013
TOCTitle: Cómo funciona el archivado en Lync Server 2013
ms:assetid: 536a52a9-cfb7-4392-9620-ffc5b319b31b
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ204900(v=OCS.15)
ms:contentKeyID: 48275248
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Cómo funciona el archivado en Lync Server 2013

 

_**Última modificación del tema:** 2014-02-04_

El archivado de Lync Server 2013 proporciona opciones para ayudarle a satisfacer sus necesidades de cumplimiento de normas. Para implementarlo y mantenerlo de la forma más eficaz posible para cumplir con los requisitos de su organización, debe conocer:

  - La información que se puede archivar.

  - Cómo habilitar y deshabilitar el archivado en su implementación.

  - Las opciones de archivado que se pueden configurar para controlar cómo se implementa el archivado.

## ¿Qué información puede archivarse?

Se pueden archivar los siguientes tipos de contenido:

  - Mensajes instantáneos de punto a punto

  - Conferencias (reuniones), que son mensajes instantáneos con varios participantes

  - Contenido de conferencias, como contenido que se carga (por ejemplo, documentos de la reunión) y contenido relacionado con el evento (por ejemplo, los usuarios que se unen o abandonan el evento, la carga de recursos compartidos y cambios en la visibilidad)

  - Pizarras y sondeos los compartidos durante una conferencia

No se almacenan los tipos de contenido siguientes:

  - Transferencias de archivos de punto a punto

  - Audio y vídeo para conferencias y mensajes instantáneos de punto a punto

  - Escritorio y uso compartido de aplicaciones para conferencias y mensajes instantáneos de punto a punto

Asimismo, Lync Server no archiva las conversaciones de Chat persistente. Para archivar las conversaciones de Chat persistente, debe habilitar y configurar el servicio de cumplimiento de normas, que es un componente que se puede implementar con Microsoft Lync Server 2013, Servidor de chat persistente. Para más información, vea [Planeación del servidor de chat persistente en Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) en la documentación de planificación.

## ¿Cómo empezar a usar el archivado?

El archivado se instala automáticamente en cada servidor front-end al implementar el servidor, pero el archivado no está habilitado hasta que se configura. La forma de configurar viene determinada por la forma de implementar el archivado:

  - **Archivado con la integración de Microsoft Exchange.** Si tiene usuarios alojados en Exchange 2013 y sus buzones se han colocado en Conservación local, puede seleccionar la opción de integrar el almacenamiento de Lync Server 2013 con el almacenamiento de Exchange. Si elige la opción de integración de Microsoft Exchange, use las directivas y las configuraciones de Exchange 2013 para controlar el archivado de datos de Lync Server 2013 para esos usuarios.

  - **Archivado con bases de datos de archivado de Lync Server.** Si tiene usuarios que no están alojados en Exchange 2013 o que no tenían colocados sus buzones en Conservación local, o si no desea usar la integración de Microsoft Exchange para alguno o todos los usuarios de la implementación, puede implementar las bases de datos de archivado de Lync Server con SQL Server para almacenar los datos de archivado para esos usuarios. En este caso, las configuraciones y directivas de archivado de Lync Server 2013 determinan si el archivado está habilitado y cómo está implementado. Para usar Lync Server 2013, debe agregar las bases de datos de SQL Server adecuadas a su topología y publicar su topología.

## Configuración de archivado al usar la integración de Microsoft Exchange

Si los usuarios están alojados en Exchange 2013 y sus buzones se han colocado en Conservación local, puede elegir la opción de integración de **Microsoft Exchange** (como se describe más adelante en esta sección) para archivar Lync Server 2013 para esos usuarios y luego controlar el archivado para ellos especificando las configuraciones y las directivas de Conservación local de Exchange, y también las configuraciones de Lync Server para controlar lo siguiente:

  - Si desea archivar MI, conferencias o ambas.

  - Si se va a implementar de modo crítico en su implementación de Lync Server.

  - La selección de la opción de integración de Microsoft Exchange para usar Exchange 2013 para el almacenamiento de datos archivados.

Estas opciones de configuración de archivado de Lync Server 2013 se describen más adelante en esta sección. Para más información sobre cómo configurar las configuraciones y las directivas de Conservación local de Exchange para admitir el archivado, vea la documentación del producto de Exchange 2013.

## Configuración de archivado con almacenamiento de base de datos de archivado de Lync Server

Si desea usar bases de datos de archivado de Lync Server (con bases de datos de SQL Server) para archivar datos para cualquier usuario de la implementación, puede configurar directivas de archivado de Lync Server para controlar si el archivado está habilitado para esos usuarios. En cada directiva de archivado, puede activar o desactivar el archivado para una o ambas de las siguientes opciones:

  - Comunicaciones internas

  - Comunicaciones externas

De forma predeterminada, el archivado no está habilitado para las comunicaciones internas ni para las comunicaciones externas en ninguna directiva de archivado de Lync Server. Puede habilitar y deshabilitar las comunicaciones utilizando Panel de control de Lync Server 2013 o con los cmdlets en el Shell de administración de Lync Server 2013.

Lync Server 2013Las directivas de archivado incluyen lo siguiente:

  - **Directiva global de archivado**. Esta es la directiva de archivado predeterminada y se aplica a la implementación completa. Se crea cuando implementa Lync Server 2013 y, de forma predeterminada, deshabilita el archivado para comunicaciones internas y externas. No se puede eliminar esta directiva. Si elige la opción Eliminar, la directiva global se restablece a la configuración predeterminada.

  - **Directiva de archivado del sitio**. Si lo desea, puede activar o desactivar el archivado para uno o más sitios específicos creando y configurando una directiva de archivado de nivel de sitio para el sitio. Cuando crea una directiva de archivado de nivel de sitio, de forma predeterminada, el archivado no está habilitado. Puede eliminar cualquier directiva de archivado de nivel de sitio que cree. Una directiva de archivado de nivel de sitio reemplaza la directiva global, pero solo para el sitio especificado en la directiva. Por ejemplo, si habilita el archivado para comunicaciones internas y externas en la directiva global y crea una directiva de sitio en la que deshabilita el archivado para las comunicaciones externas, solo se archivarían las comunicaciones internas de ese sitio.

  - **Directiva de archivado de usuario**. Si lo desea, puede activar o desactivar el archivado para uno o más usuarios específicos y grupos de usuarios creando, configurando y aplicando una directiva de archivado de nivel de usuario para los grupos de usuario y los usuarios especificados. Cuando crea una directiva de archivado de nivel de usuario, de forma predeterminada, el archivado no está habilitado. Puede eliminar cualquier directiva de archivado de nivel de usuario que cree y puede cambiar a qué usuarios y grupos de usuarios se aplica la directiva de archivado. Una directiva de archivado de nivel de usuario reemplaza la directiva global y las directivas de cualquier sitio, pero solo para los usuarios y grupos de usuario a quienes se aplica la directiva. Por ejemplo, si deshabilita el archivado para comunicaciones internas y externas en la directiva global, crea una directiva de nivel de sitio en la que habilita el archivado para comunicaciones internas y externas y, a continuación, crea una directiva de nivel de usuario en la que deshabilita el archivado para las comunicaciones externas, las comunicaciones se archivan para las comunicaciones internas y externas para todos los usuarios del sitio, excepto para los usuarios a los que se aplica la directiva de nivel de usuario, para quienes se archivan solo las comunicaciones internas.

Para más información sobre cómo configurar las directivas de archivado iniciales cuando implementa el archivado, consulte [Configurar y asignar directivas de archivado](lync-server-2013-configuring-and-assigning-archiving-policies.md) en la documentación de implementación. Para más información sobrel uso de las directivas de archivado para habilitar y deshabilitar las comunicaciones después de la implementación, consulte [Administrar el archivado de las comunicaciones internas y externas en Lync Server 2013](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md) en la documentación de las operaciones.


> [!NOTE]
> Si implementa bases de datos de archivado de Lync Server 2013 y habilita la integración de Microsoft Exchange, las directivas de Exchange 2013 reemplazan las directivas de archivado de Lync Server, pero solo para los usuarios que están alojados en Exchange 2013 y han tenido sus buzones en Conservación local. Archivado de Lync solo depende de la directiva de Conservación local de Microsoft Exchange.



## ¿Qué opciones tengo para la configuración del archivado?

Además de usar directivas y habilitar y deshabilitar el archivado, tiene otras opciones de archivado que se pueden configurar para toda la implementación y, opcionalmente, para grupos y sitios específicos. Puede controlar la mayoría de las opciones de archivado mediante el uso de una o varias configuraciones de archivado, que están disponibles en Panel de control de Lync Server 2013, pero también tiene otra opción que solo está disponible para configuración utilizando Shell de administración de Lync Server 2013.

## Opciones de configuración de archivado disponibles en el Panel de Control de Lync Server 2013

Cada configuración de archivado proporciona las siguientes opciones:

La configuración de nivel global se crea automáticamente cuando implementa el archivado y puede configurarse, pero no eliminarse. Si selecciona la opción para eliminar la configuración global, la configuración se restablece a los valores predeterminados. Puede crear varias configuraciones de sitio y grupo que, junto con la configuración global, controlan la configuración de archivado. Para la configuración global y cada configuración de sitio y grupo, tiene las siguientes opciones:

  - Deshabilitar el archivado, habilitar el archivado solo para mensajería instantánea (MI) o habilitar el archivado de mensajería instantánea y conferencias.

  - Configurar el modo crítico para bloquear las sesiones de mensajería instantánea y conferencias en caso de que se produzca un error de Lync Server. Entre los errores se encuentran los siguientes:
    
      - **Mensajería instantánea.**. Un problema con el servicio de almacenamiento de Lync Server. En este caso, la mensajería instantánea está bloqueada para los usuarios que están habilitados para el archivado.
    
      - **Conferencias**. Un error podría ser un recurso compartido de archivo no disponible o un problema con el servicio de almacenamiento. En este caso, todas las conferencias activas alojadas en el grupo de servidores en el momento del error se cambian al modo restringido y no se puede activar conferencias nuevas.
    
    Tanto el servicio de mensajería instantánea como de conferencias se recuperan automáticamente después de que se corrigen los errores.

  - Especificar el uso de la integración de Microsoft Exchange Server 2013 para utilizar Exchange 2013 para el almacenamiento de datos archivados, en lugar de configurar las bases de datos de SQL Server independientes para el almacenamiento de datos de archivado de Lync Server 2013.

  - Configurar las opciones de depuración para los datos archivados. Esto incluye indicar cuándo se deben purgar los datos archivados, que puede ser una de las siguientes opciones:
    
      - Después de un número determinado de días que especifique
    
      - Después de haber exportado los datos de archivado (que incluye datos que se han cargado en Exchange, si habilita la integración de Microsoft Exchange).
    

    > [!NOTE]
    > Si habilita la integración de Microsoft Exchange, el proceso de purga de los usuarios alojados en Exchange 2013 y con sus buzones en Conservación local es controlado por Exchange. La única calificación es para los archivos de conferencias, que se almacenan en el recurso compartido de archivos de Lync Server. Estos archivos se purgan desde el recurso compartido de archivos solo después de que los archivos se han exportado (cargados a Exchange), si selecciona la opción de purgar los datos una vez que se han exportado los datos de archivado o después del número máximo especificado de días, si especifica un número máximo de días de retención.



De forma predeterminada, no hay opciones de archivado habilitadas. Puede administrar las configuraciones de archivado con Panel de control de Lync Server 2013.

Puede especificar las siguientes configuraciones de archivado:

  - **Configuración de archivado global**. Esta es la configuración de archivado predeterminada y se aplica a la implementación completa. Se crea al implementar Lync Server 2013 y, de forma predeterminada, no habilita la función de archivado. Puede modificar la configuración global, pero no la puede eliminar. Si elige la opción de eliminar la configuración, la configuración global se restablece a la configuración predeterminada.

  - **Configuración de archivado de sitio**. Si lo desea, puede configurar el archivado para uno o más sitios específicos creando y estableciendo una configuración de archivado de nivel de sitio para un sitio individual. Una configuración de archivado de nivel de sitio existe solo si la crea. Puede modificar o eliminar cualquier configuración de archivado de nivel de sitio. Una configuración de archivado de nivel de sitio reemplaza la configuración global, pero solo para el sitio especificado en la configuración de nivel de sitio. Por ejemplo, si habilita el archivado de mensajería instantánea exclusivamente en la configuración global y crea una configuración de sitio en la que habilita el archivado de mensajería instantánea y conferencias, las conferencias podrían archivarse solo para el sitio, no para el resto de la organización.

  - **Configuración de archivado de grupo**. Si lo desea, puede especificar la configuración de archivado para uno o más grupos específicos creando y estableciendo una configuración de nivel de grupo para el grupo de servidores individual. Una configuración de archivado de nivel de grupo existe solo si la crea. Puede modificar y eliminar cualquier configuración de archivado de nivel de grupo. Una configuración de archivado de nivel de grupo reemplaza la configuración global y la configuración de archivado de cualquier sitio que haya creado. Por ejemplo, si habilita el archivado de mensajería instantánea solo en la configuración global, crea una configuración de nivel de sitio en la que habilite el archivado de mensajería instantánea y conferencias para el sitio y, a continuación, crea una configuración de nivel de grupo en la que habilite el archivado solo para mensajería instantánea, las comunicaciones se archivarán para mensajería instantánea y conferencias para todos los usuarios del sitio excepto los usuarios alojados en el grupo especificado en la configuración de nivel de grupo. Para todos los demás usuarios de la organización, se habilitará el archivado solo para mensajería instantánea.

Para más información sobre cómo establecer las configuraciones de archivado iniciales cuando implementa el archivado, consulte [Configurar opciones de archivado](lync-server-2013-configuring-archiving-options.md) en la documentación de implementación. Para más información sobrel uso de las directivas de archivado para habilitar y deshabilitar las comunicaciones después de la implementación, consulte [Administrar las opciones de configuración de archivado de Lync Server 2013 para su organización, sitios y grupos de servidores](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md) en la documentación de las operaciones.

## Opciones de archivado disponibles solo en Windows PowerShell

Mediante Shell de administración de Lync Server 2013, puede usar los cmdlets para implementar las opciones que no están disponibles en Panel de control de Lync Server 2013. Estas opciones incluyen lo siguiente:

  - **Archivar mensajes duplicados**. Para más información, vea [New-CsArchivingConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsArchivingConfiguration) y [Set-CsArchivingConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsArchivingConfiguration) en la documentación de operaciones.

  - **Exportar datos archivados**. Para más información, vea [Export-CsArchivingData](https://docs.microsoft.com/en-us/powershell/module/skype/Export-CsArchivingData)

## ¿Cómo se puede acceder a datos archivados?

El acceso a los datos archivados depende de dónde se almacenan los datos:

  - **Almacenamiento de Microsoft Exchange**. Si elige la opción de integración de Exchange, Lync Server coloca el contenido de archivado en el almacén Exchange 2013 para todos los usuarios que están alojados en Exchange 2013 y que han tenido sus buzones en Conversación local. Los datos archivados se almacenan en la carpeta de elementos recuperables de los buzones de usuario, que normalmente es invisible para los usuarios y en la que solo pueden buscar usuarios que tengan el rol Exchange**Administración de detección**. Exchange permite la detección y la búsqueda federada, junto con SharePoint, si se implementa. Si desea información detallada sobre almacenamiento, retención y detección de datos almacenados en Exchange, consulte la documentación de Exchange 2013 y SharePoint.

  - **Almacenamiento de Lync Server.** Si configura bases de datos de archivado de Lync Server 2013 para el almacenamiento de datos de Lync Server, Lync Server coloca el contenido de archivado en las bases de datos de archivado de Lync Server (bases de datos de SQL Server) para cualquier usuario alojado en Exchange 2013 y han tenido sus buzones en Conservación local. Estos datos no pueden buscarse, pero se pueden exportar a formatos que se pueden buscar mediante otras herramientas. Para más información sobre cómo exportar los datos almacenados en las bases de datos de archivado, vea [Exportar datos archivados de Lync Server 2013](lync-server-2013-exporting-archived-data.md) en la documentación de operaciones.

Para más detalles sobre cómo funcionan juntos Lync Server 2013 y Exchange 2013, vea [Compatibilidad de la integración Exchange Server y SharePoint en Lync Server 2013](lync-server-2013-exchange-and-sharepoint-integration-support.md) en la documentación de compatibilidad.

