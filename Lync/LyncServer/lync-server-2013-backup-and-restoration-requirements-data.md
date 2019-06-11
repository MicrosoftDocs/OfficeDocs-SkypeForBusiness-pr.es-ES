---
title: 'Lync Server 2013: requisitos de copia de seguridad y restauración: datos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: 'Backup and restoration requirements: data'
ms:assetid: ecfb8e4d-cb4f-476d-9772-4486bd683c04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202194(v=OCS.15)
ms:contentKeyID: 51541526
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 54814295343b99cb51e5827791df160dbeff2638
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842886"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backup-and-restoration-requirements-in-lync-server-2013-data"></a>Requisitos de copia de seguridad y restauración en Lync Server 2013: datos

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-03-26_

Lync Server usa la configuración y la información de configuración que se almacenan en bases de datos y datos que se almacenan en bases de datos y almacenes de archivos. En este tema se describen los datos de los que debe hacer una copia de seguridad para poder restaurar el servicio si su organización sufre un error o una interrupción, y también identifica los datos y componentes usados por Lync Server que necesita para hacer una copia de seguridad por separado.

<div>

## <a name="settings-and-configuration-requirements"></a>Requisitos de configuración y configuración

Este tema incluye procedimientos para realizar copias de seguridad y restaurar la configuración y la información de configuración necesarias para la recuperación del servicio de Lync Server. La información de configuración se encuentra en el almacén central de administración o en otra base de datos back-end o en un servidor Standard Edition.

La siguiente tabla identifica la configuración y la información de configuración que necesita para realizar copias de seguridad y restaurar.

### <a name="settings-and-configuration-data"></a>Datos de configuración y configuración

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Tipo de datos</th>
<th>Donde se almacena</th>
<th>Descripción/Cuándo hacer una copia de seguridad</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Información de configuración de topología</p></td>
<td><p>Tienda de administración central (base de datos: XDS. MDF)</p></td>
<td><p>Topología, Directiva y parámetros de configuración.</p>
<p>Haga una copia de seguridad de las copias de seguridad periódicas y después use los cmdlets o el panel de control de Lync Server para modificar su configuración o directivas.</p></td>
</tr>
<tr class="even">
<td><p>Información de ubicación</p></td>
<td><p>Almacén de administración central (base de datos: Lis. MDF)</p></td>
<td><p>Información de configuración de Enterprise Voice Enhanced 9-1-1 (E9-1-1). Generalmente, esta información es estática.</p>
<p>Haga una copia de seguridad de sus copias de seguridad periódicas.</p></td>
</tr>
<tr class="odd">
<td><p>Información de configuración del grupo de respuesta</p></td>
<td><p>Servidor back-end o servidor Standard Edition (base de datos: RgsConfig. MDF)</p></td>
<td><p>Grupos de agentes de grupo de respuesta, colas y flujos de trabajo.</p>
<p>Haga una copia de seguridad de sus copias de seguridad periódicas y después agregue o cambie los grupos de agentes, las colas o los flujos de trabajo.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="data-requirements"></a>Requisitos de datos

A continuación se muestra una lista de los datos de Lync Server que necesita para realizar una copia de seguridad de modo que pueda restaurar el servicio Lync Server en caso de que se produzca un error.

Tenga en cuenta que algunos tipos de datos no son necesarios para la recuperación. Este tema no contiene procedimientos para realizar copias de seguridad de estos tipos de datos, entre los que se incluyen los siguientes:

  - Datos de usuario transitorios, como puntos finales y suscripciones, servidores de conferencia activos y Estados de conferencia transitorios (base de datos: RtcDyn. MDF)

  - Datos de la libreta de direcciones (bases de datos: Rtcab. MDF y Rtcab1. MDF). La base de datos de la libreta de direcciones se regenera automáticamente desde los servicios de dominio de Active Directory.

  - Información dinámica para la aplicación de estacionamiento de llamadas (base de datos: CpsDyn. MDF)

  - Datos de grupo de respuesta transitorios, como el estado de inicio de sesión del agente y la información de llamada en espera (base de datos: RgsDyn. MDF)

  - La base de datos de cumplimiento para una conversación persistente (base de datos: MgcComp. MDF). Si tiene habilitada la compatibilidad de chat persistente, la información de la base de datos de cumplimiento persistente de chat es transitoria siempre que tenga un adaptador configurado para leer la información de la base de datos y convertirla a un formato alternativo. Por lo tanto, la base de datos de cumplimiento para chat persistente se considera transitoria.
    
    Lync Server 2013 el servidor de chat persistente se distribuye con un adaptador XML. También puede instalar adaptadores personalizados que toman estos datos y los mueven a otros orígenes, como archivos hospedados de Exchange.

La siguiente tabla identifica los datos que necesita para realizar copias de seguridad y restaurar.

### <a name="data-stored-in-databases"></a>Datos almacenados en bases de datos

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Tipo de datos</th>
<th>Donde se almacena</th>
<th>Descripción/Cuándo hacer una copia de seguridad</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Datos de usuario persistentes</p></td>
<td><p>Servidor back-end o servidor Standard Edition (base de datos: RTCXDS. MDF)</p></td>
<td><p>Derechos de usuario, listas de contactos de usuarios, datos de servidores o agrupaciones, conferencias programadas, etc. Los datos de este usuario no incluyen contenido cargado en una conferencia.</p>
<p>Haga una copia de seguridad de sus copias de seguridad periódicas. Esta información es dinámica, pero la pérdida de actualizaciones no es catastrófica para Lync Server si necesita restaurar la última copia de seguridad normal. Si las listas de contactos son críticas para su organización, puede realizar copias de seguridad de estos datos con más frecuencia.</p></td>
</tr>
<tr class="even">
<td><p>Archivar datos</p></td>
<td><p>Base de datos de archivado (base de datos: LcsLog. MDF)</p>
<p>Estos datos pueden almacenarse en Exchange 2013, si ha habilitado la opción de integración de Microsoft Exchange. De lo contrario, estos datos se guardan en una base de datos de archivado de Lync Server, que se puede colocar con otra base de datos de Lync Server o independiente en un servidor de base de datos independiente.</p></td>
<td><p>Mensajería instantánea (mi) y contenido de la reunión.</p>
<p>Esta información no es crítica para Lync Server, pero puede ser fundamental para su organización con fines normativos. Determine la programación de la copia de seguridad según corresponda.</p></td>
</tr>
<tr class="odd">
<td><p>Supervisión de datos</p></td>
<td><p>Supervisar bases de datos (LcsCDR. MDF y QoeMetrics. MDF)</p>
<p>Estas bases de datos pueden estar colocadas con otra base de datos de Lync Server o independiente en un servidor de base de datos independiente.</p></td>
<td><p>Registros de detalles de llamadas (LcsCDR. MDF) y métricas de la calidad de la experiencia (QoE) (QoeMetrics. MDF).</p>
<p>Los registros de detalles de llamadas son dinámicos y pueden ser esenciales para tu empresa. Determine la programación de la copia de seguridad teniendo en cuenta si necesita estos registros por razones normativas.</p>
<p>La calidad de la experiencia de la información es dinámica. La pérdida de los datos de la calidad de la calidad no es crítica para el funcionamiento de Lync Server, pero puede ser crítico para su empresa. Determine la programación de la copia de seguridad en función de la importancia de esta información para su organización.</p></td>
</tr>
<tr class="even">
<td><p>Datos de chat persistente</p></td>
<td><p>Base de datos de chat persistente (MGD. MDF).</p>
<p>Esta base de datos puede estar colocada con otra base de datos de Lync Server o independiente en un servidor de base de datos independiente.</p></td>
<td><p>Los datos de chat persistentes son contenido de chat real que se publican en salones de chat. Estos datos son a menudo críticos para la empresa.</p>
<p>Puede optar por usar la copia de seguridad de SQL Server o exportar la base de datos con el cmdlet <strong>Export-CsPersistentChatData</strong> que se proporciona en Lync Server. Para recuperar los datos, puede importar y restaurar la base de datos hasta el momento de la última copia de seguridad completa, lo que significa que no puede restaurar la base de datos hasta el momento del error.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="file-store-data-requirements"></a>Requisitos de datos del almacén de archivos

En una implementación de Enterprise Edition, el almacén de archivos de Lync Server suele encontrarse en un servidor de archivos. En una implementación de Standard Edition, el almacén de archivos de Lync Server se encuentra de forma predeterminada en el servidor Standard Edition. Normalmente, hay un almacén de archivos de Lync Server compartido para un sitio. El almacén de archivos de chat persistente usa el mismo recurso compartido de archivos que el almacén de archivos de Lync Server.

Las ubicaciones del almacén de archivos \\ \\se\\identifican como nombres de recursos compartidos del servidor. Para buscar las ubicaciones específicas de los almacenes de archivos, abra el generador de topologías y mire en el nodo **almacenes de archivos** .

La siguiente tabla identifica los almacenes de archivos que necesita para realizar copias de seguridad y restaurar.

### <a name="file-stores"></a>Almacenes de archivos

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Tipo de datos</th>
<th>Donde se almacena</th>
<th>Descripción/Cuándo hacer una copia de seguridad</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Almacén de archivos de Lync Server</p></td>
<td><p>Normalmente, en un servidor de archivos, un clúster de archivos o un servidor Standard Edition</p></td>
<td><p>Contenido de la reunión, metadatos de contenido, reuniones registros de cumplimiento, archivos de datos de aplicaciones, archivos de actualización para actualizaciones de dispositivos, archivos de audio para el grupo de respuesta, detener la llamada y aplicaciones de presentación, y archivos publicados en salones de chat persistentes.</p>
<p>Haga una copia de seguridad de sus copias de seguridad periódicas.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="additional-backup-requirements"></a>Requisitos de copia de seguridad adicionales

Para garantizar su capacidad de restaurar los servicios de Lync Server en el caso de que se produzca un error, debe hacer una copia de seguridad de algunos componentes necesarios que no forman parte de Lync Server. Los siguientes componentes no se incluyen en la copia de seguridad ni se restauran como parte del proceso de copia de seguridad y restauración de Lync Server descrito en este documento:

  - **Servicios de dominio de Active**   Directory necesita hacer una copia de seguridad de AD DS con las herramientas de Active Directory al mismo tiempo que realiza una copia de seguridad de Lync Server. Es importante mantener AD DS sincronizado con Lync Server, para evitar problemas que se pueden producir cuando Lync Server espera objetos de contacto que no coinciden con los de AD DS. AD DS almacena los siguientes valores de configuración usados por Lync Server:
    
      - URI del SIP del usuario y otra configuración de usuario.
    
      - Objetos de contacto para aplicaciones como el grupo de respuesta y el operador de conferencia.
    
      - Puntero al almacén de administración central.
    
      - Cuenta de autenticación Kerberos (un objeto de equipo opcional) y grupos de seguridad de Lync Server.
    
    Para obtener detalles sobre cómo realizar copias de seguridad y restaurar AD DS en Windows Server 2008, consulte "Guía paso a paso de copia de seguridad y recuperación [http://go.microsoft.com/fwlink/p/?linkId=209105](http://go.microsoft.com/fwlink/p/?linkid=209105)de AD DS" en.

  - **Entidad de certificación y certificados**   : Use la Directiva de su organización para realizar copias de seguridad de su entidad de certificación (CA) y certificados. Si utiliza claves privadas exportables, puede hacer una copia de seguridad del certificado y de la clave privada y, a continuación, exportarlos si usa los procedimientos de este documento para restaurar Lync Server. Si usa una CA interna, puede volver a inscribirse si necesita restaurar Lync Server. Es importante que mantenga la clave privada en una ubicación segura donde estará disponible si se produce un error en un equipo.

  - **System Center Operations Manager**   si usa Microsoft System Center Operations Manager (anteriormente Microsoft Operations Manager) para supervisar su implementación de Lync Server, puede hacer una copia de seguridad de los datos que crea mientras está supervisando Lync Servidores. Use el proceso de copia de seguridad estándar de SQL Server para realizar copias de seguridad de los archivos de System Center Operations Manager. Estos archivos no se restauran durante la recuperación.

  - **Configuración de puerta de enlace de red de telefonía pública conmutada (RTC)**   si usa dispositivos de voz o de sucursales con supervivencia, tendrá que realizar una copia de seguridad de la configuración de la puerta de enlace RTC. Consulte a su proveedor para obtener detalles sobre cómo realizar copias de seguridad y restaurar las configuraciones de puerta de enlace RTC.

  - **Versiones coexistentes de Lync Server o de Office Communications Server**   si su implementación de Lync Server 2013 coexiste con Lync Server 2010 o una versión anterior de Office Communications Server, no puede usar los procedimientos de este documento para realizar copias de seguridad o restaurar la versión anterior. En su lugar, debe usar los procedimientos de copia de seguridad y restauración documentados específicamente para su versión anterior. Para obtener detalles sobre cómo realizar copias de seguridad y restaurar Lync Server [http://go.microsoft.com/fwlink/p/?linkId=265417](http://go.microsoft.com/fwlink/p/?linkid=265417) 2010, consulte. Para obtener más información sobre cómo realizar copias de seguridad y restaurar Microsoft Office Communications Server [http://go.microsoft.com/fwlink/p/?linkId=168162](http://go.microsoft.com/fwlink/p/?linkid=168162)2007 R2, consulte.

  - **Información de infraestructura**   necesita realizar una copia de seguridad de la información sobre su infraestructura, como la configuración del firewall, la configuración del equilibrio de carga, la configuración de servicios de Internet Information Server (IIS), los registros del sistema de nombres de dominio (DNS) y Direcciones IP y configuración de protocolo de configuración dinámica de host (DHCP). Para obtener detalles sobre cómo realizar una copia de seguridad de estos componentes, consulte a sus respectivos proveedores.

  - **Copia de seguridad de mensajería unificada (UM)**   de Microsoft Exchange y Exchange y restaurar Microsoft Exchange y Exchange um según se describe en la documentación de Microsoft Exchange. Para obtener detalles sobre cómo realizar copias de seguridad y restaurar Exchange Server [http://go.microsoft.com/fwlink/?LinkId=285384](http://go.microsoft.com/fwlink/?linkid=285384)2013, consulte. Para obtener detalles sobre cómo realizar copias de seguridad y restaurar Exchange Server [http://go.microsoft.com/fwlink/p/?linkId=209179](http://go.microsoft.com/fwlink/p/?linkid=209179)2010, consulte.
    
    Tenga en cuenta que Lync Server 2013 introduce la posibilidad de disponer de listas de contactos de usuarios, fotos de usuarios de alta definición y archivado de datos almacenados en Exchange 2013. Consulte la siguiente lista para ver cómo hacer una copia de seguridad de estos tipos de datos:
    
      - Se realiza una copia de seguridad de las **fotos de alta definición** como parte de la copia de seguridad de Exchange Server.
    
      - El **almacén de contactos unificado** se introdujo en Lync Server 2013. El almacén de contactos unificado permite a los usuarios mantener toda la información de contacto en Exchange 2013.
        
        Debe asegurarse de que las copias de seguridad están actualizadas para los usuarios en cuanto a si sus contactos de usuario se almacenan en el almacenamiento de contactos unificado o en el servidor back-end de Lync. Los siguientes escenarios muestran dónde migrar contactos de usuario al almacén de contactos unificado puede causar problemas para el proceso de copia de seguridad y restauración.
        
        **Escenario 1:** Los contactos de usuario se migran al almacén de contactos unificado y se realiza una restauración desde una copia de seguridad de Lync Server realizada antes de la migración de los contactos de usuario. En este escenario, el usuario tendrá un estado de contactos anticuados durante un día hasta que la tarea de migración de Lync Server comience a migrar los contactos de los usuarios a Exchange. (Tenga en cuenta que, dado que los contactos del usuario se han migrado previamente al almacén de contactos unificado, se usará la información de contacto de Exchange). No es necesario que intervenga el administrador en este escenario.
        
        **Escenario 2:** Los contactos de usuario se almacenaron anteriormente en el almacén de contactos unificados, pero después se deshicieron. Una restauración se realiza desde una copia de seguridad de Lync Server realizada cuando los contactos del usuario se almacenaron en el almacén de contactos unificado. En este escenario, un mensaje de error `Error: Incorrect Exchange Version` de los registros del cliente o del servidor Lyss puede indicar que se trata de un problema. El usuario podrá obtener acceso a su lista de contactos en Lync 2013 directamente desde Exchange, pero el estado del cliente no coincidirá con el estado del servidor de Lync. Para corregir este error, un administrador tendrá que ejecutar los cmdlets **Invoke-CsUCSRollback** para los usuarios afectados.
    
      - El archivado de **datos** puede almacenarse en Exchange 2013. Esta información no es crítica para Lync Server, pero puede ser fundamental para su organización con fines normativos. Si los datos de archivado se almacenan en Exchange y son esenciales para su organización, siga los procedimientos de copia de seguridad y restauración de Exchange. Tenga en cuenta que los datos de archivado almacenados en Exchange no se pueden volver a mover a Lync Server. Además, no hay ninguna manera de mover los datos que ya están almacenados en la base de datos de archivado de Lync a Exchange.

</div>

</div>

<span> </span>

</div>

</div>

</div>

