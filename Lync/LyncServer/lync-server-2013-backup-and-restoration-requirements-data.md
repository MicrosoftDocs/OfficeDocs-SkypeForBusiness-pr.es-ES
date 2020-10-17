---
title: 'Lync Server 2013: requisitos de copia de seguridad y restauración: datos'
description: 'Lync Server 2013: requisitos de copia de seguridad y restauración: datos.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: 'Backup and restoration requirements: data'
ms:assetid: ecfb8e4d-cb4f-476d-9772-4486bd683c04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202194(v=OCS.15)
ms:contentKeyID: 51541526
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7e135f09706d31ff3f0efa54c8687546de9fab78
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48563186"
---
# <a name="backup-and-restoration-requirements-in-lync-server-2013-data"></a>Requisitos de copia de seguridad y restauración en Lync Server 2013: datos

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-03-26_

Lync Server usa la configuración y la información de configuración que se almacenan en las bases de datos y los datos que se almacenan en las bases de datos y los almacenes de archivos. En este tema se describen los datos de los que necesita hacer una copia de seguridad para poder restaurar el servicio si la organización experimenta un error o una interrupción, y también identifica los datos y componentes usados por Lync Server de los que necesita hacer una copia de seguridad por separado.

<div>

## <a name="settings-and-configuration-requirements"></a>Requisitos de parámetros y configuración

En este tema se incluyen procedimientos para realizar copias de seguridad y restaurar la información de configuración y configuración necesaria para la recuperación del servicio de Lync Server. La información de configuración se encuentra en el almacén de administración central o en otra base de datos back-end o en un servidor Standard Edition.

En la tabla siguiente se identifican las opciones de configuración y la información de configuración necesarias para hacer una copia de seguridad y restaurar.

### <a name="settings-and-configuration-data"></a>Datos de parámetros y configuración

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Tipo de datos</th>
<th>Dónde se almacenan</th>
<th>Descripción/Cuándo hacer una copia de seguridad</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Información de configuración de la topología</p></td>
<td><p>Almacén de administración central (base de datos: XDS. MDF)</p></td>
<td><p>Topología, directivas y opciones de configuración.</p>
<p>Realice una copia de seguridad con las copias de seguridad periódicas y después use los cmdlets o el panel de control de Lync Server para modificar la configuración o las directivas.</p></td>
</tr>
<tr class="even">
<td><p>Información de ubicación</p></td>
<td><p>Almacén de administración central (base de datos: Lis. MDF)</p></td>
<td><p>Información de configuración de la telefonía IP empresarial (Enterprise Voice Enhanced 9-1-1, E9-1-1). Esta información generalmente es estática.</p>
<p>Haga la copia de seguridad con el resto de copias de seguridad habituales.</p></td>
</tr>
<tr class="odd">
<td><p>Información de configuración del grupo de respuesta</p></td>
<td><p>Servidor back-end o servidor Standard Edition (base de datos: RgsConfig. MDF)</p></td>
<td><p>Grupos, colas y flujos de trabajo del agente de grupo de respuesta.</p>
<p>Haga la copia de seguridad con el resto de copias de seguridad habituales y después de agregar o modificar grupos de agentes, colas o flujos de trabajo.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="data-requirements"></a>Requisitos de datos

A continuación, se muestra una lista de los datos de Lync Server de los que necesita hacer una copia de seguridad para poder restaurar el servicio Lync Server en caso de que se produzca un error.

Tenga en cuenta que algunos tipos de datos no son necesarios para la recuperación. Este tema no contiene procedimientos para realizar copias de seguridad de estos tipos de datos, entre los que se incluyen los siguientes:

  - Datos de usuario transitorios, como extremos y suscripciones, servidores de conferencia activos y estados de conferencia transitorios (base de datos: RtcDyn.mdf)

  - Datos de la libreta de direcciones (bases de datos: Rtcab. MDF y Rtcab1. MDF). La base de datos de la libreta de direcciones se regenera automáticamente desde los servicios de dominio de Active Directory.

  - Información dinámica para la aplicación estacionamiento de llamadas (base de datos: CpsDyn. MDF)

  - Datos del grupo de respuesta transitorios, como el estado de inicio de sesión del agente y la información de llamadas en espera (base de datos: RgsDyn. MDF)

  - La base de datos de cumplimiento para chat persistente (base de datos: MgcComp. MDF). Si tiene habilitado el cumplimiento de chat persistente, la información de la base de datos de cumplimiento de chat persistente será transitoria siempre que tenga un adaptador configurado para leer información de la base de datos y convertirla a un formato alternativo. Por lo tanto, la base de datos de cumplimiento de chat persistente se considera transitoria.
    
    Lync Server 2013 el servidor de chat persistente se distribuye con un adaptador XML. También puede instalar adaptadores personalizados que toman estos datos y los mueven a otros orígenes, como archivos hospedados de Exchange.

En la tabla siguiente se identifican los datos necesarios para la copia de seguridad y la restauración.

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
<th>Dónde se almacenan</th>
<th>Descripción/Cuándo hacer una copia de seguridad</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Datos de usuario persistentes</p></td>
<td><p>Servidor back-end o servidor Standard Edition (base de datos: RTCXDS. MDF)</p></td>
<td><p>Derechos de usuario, listas de contacto de usuario, datos de grupos de servidores, conferencias programadas, etc. Estos datos de usuario no incluyen el contenido cargado en una conferencia.</p>
<p>Haga la copia de seguridad con el resto de copias de seguridad habituales. Esta información es dinámica, pero la pérdida de actualizaciones no es catastrófica para Lync Server si necesita restaurar la última copia de seguridad normal. Si las listas de contactos son esenciales para la organización, puede hacer una copia de seguridad de estos datos con más frecuencia.</p></td>
</tr>
<tr class="even">
<td><p>Datos de archivado</p></td>
<td><p>Base de datos de archivado (base de datos: LcsLog.mdf)</p>
<p>Estos datos pueden almacenarse en Exchange 2013, si ha habilitado la opción de integración de Microsoft Exchange. De lo contrario, estos datos se conservan en una base de datos de archivado de Lync Server, que puede estar combinada con otra base de datos de Lync Server o independiente en un servidor de bases de datos independiente.</p></td>
<td><p>Mensajería instantánea (MI) y contenido de reuniones.</p>
<p>Estos datos no son críticos para Lync Server, pero pueden ser críticos para su organización con fines normativos. Determine la programación de copias de seguridad según corresponda.</p></td>
</tr>
<tr class="odd">
<td><p>Datos de supervisión</p></td>
<td><p>Bases de datos de supervisión (LcsCDR.mdf y QoeMetrics.mdf)</p>
<p>Estas bases de datos pueden combinarse con otra base de datos de Lync Server o independiente en un servidor de bases de datos independiente.</p></td>
<td><p>Registros de detalles de llamadas (LcsCDR. MDF) y métricas de calidad de la experiencia (QoE) (QoeMetrics. MDF).</p>
<p>Las registros detallados de llamadas son dinámicos y pueden ser esenciales para el negocio. Determine la programación de copias de seguridad teniendo en cuenta si se necesitan estos registros con fines de cumplimiento de normativas.</p>
<p>La información de Calidad de la experiencia es dinámica. La pérdida de datos de QoE no es crítica para el funcionamiento de Lync Server, pero puede ser crítico para su empresa. Determine la programación de copias de seguridad según la importancia de esta información para la organización.</p></td>
</tr>
<tr class="even">
<td><p>Datos de chat persistente</p></td>
<td><p>Base de datos de chat persistente (administradas. MDF).</p>
<p>Esta base de datos puede estar combinada con otra base de datos de Lync Server o independiente en un servidor de base de datos independiente.</p></td>
<td><p>Los datos de chat persistente son contenido de chat real que se publica en salones de chat. Estos datos suelen ser críticos para la empresa.</p>
<p>Puede optar por usar la copia de seguridad de SQL Server o exportar la base de datos mediante el cmdlet <strong>Export-CsPersistentChatData</strong> que se proporciona en Lync Server. Para la recuperación de los datos, puede importar y restaurar la base de datos hasta el punto de la última copia de seguridad completa, lo que significa que no se puede restaurar la base de datos en el punto de error.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="file-store-data-requirements"></a>Requisitos de datos de almacén de archivos

En una implementación de Enterprise Edition, el almacén de archivos de Lync Server suele estar ubicado en un servidor de archivos. En una implementación de Standard Edition, el almacén de archivos de Lync Server se encuentra de forma predeterminada en el servidor Standard Edition. Normalmente, hay un almacén de archivos de Lync Server que se comparte en un sitio. El almacén de archivos de chat persistente usa el mismo recurso compartido de archivos que el almacén de archivos de Lync Server.

Las ubicaciones del almacén de archivos se identifican como \\ \\ \\ nombre del recurso compartido del servidor. Para buscar las ubicaciones específicas de los almacenes de archivos, abra el generador de topologías y mire en el nodo **almacenes de archivos** .

En la siguiente tabla se identifican los almacenes de archivos necesarios para hacer una copia de seguridad y restaurar el servicio.

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
<th>Dónde se almacenan</th>
<th>Descripción/Cuándo hacer una copia de seguridad</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Almacén de archivos de Lync Server</p></td>
<td><p>Normalmente en un servidor de archivos, un clúster de archivos o un servidor Standard Edition</p></td>
<td><p>Contenido de la reunión, los metadatos de contenido, las reuniones registros de cumplimiento, los archivos de datos de aplicaciones, los archivos de actualización para actualizaciones de dispositivos, los archivos de audio para el grupo de respuesta, el estacionamiento de llamadas y las aplicaciones de anuncio y los archivos publicados en los salones de chat persistente</p>
<p>Haga la copia de seguridad con el resto de copias de seguridad habituales.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="additional-backup-requirements"></a>Requisitos adicionales de las copias de seguridad

Para ayudar a garantizar la posibilidad de restaurar los servicios de Lync Server en caso de que se produzca un error, debe hacer una copia de seguridad de algunos componentes necesarios que no formen parte de Lync Server. Los siguientes componentes no se incluyen en la copia de seguridad ni se restauran como parte del proceso de copia de seguridad y restauración de Lync Server que se describe en este documento:

  - Servicios de dominio de **Active**     Directory Debe hacer una copia de seguridad de AD DS con las herramientas de Active Directory al mismo tiempo que realiza una copia de seguridad de Lync Server. Es importante mantener AD DS sincronizado con Lync Server, para evitar problemas que se pueden producir cuando Lync Server espera objetos de contacto que no coinciden con los de AD DS. AD DS almacena los siguientes valores de configuración que se usan en Lync Server:
    
      - URI del SIP del usuario y otras opciones de configuración del usuario.
    
      - Objetos de contacto para aplicaciones como grupo de respuesta y operador de conferencia.
    
      - Un puntero al almacén de administración central.
    
      - Cuenta de autenticación Kerberos (un objeto de equipo opcional) y grupos de seguridad de Lync Server.
    
    Para obtener información detallada sobre cómo realizar copias de seguridad y restaurar AD DS en Windows Server 2008, consulte la guía paso a paso de copia de seguridad y recuperación de AD DS en [https://go.microsoft.com/fwlink/p/?linkId=209105](https://go.microsoft.com/fwlink/p/?linkid=209105) .

  - **Entidad de certificación y certificados**     Use la Directiva de la organización para hacer una copia de seguridad de la entidad de certificación (CA) y los certificados. Si usa claves privadas exportables, puede hacer una copia de seguridad del certificado y la clave privada y, a continuación, exportarlos si usa los procedimientos de este documento para restaurar Lync Server. Si usa una CA interna, puede volver a inscribirse si necesita restaurar Lync Server. Es importante que conserve la clave privada en un lugar seguro donde esté disponible en caso de que se produzca un error en un equipo.

  - **System Center Operations Manager**     Si usa Microsoft System Center Operations Manager (anteriormente, Microsoft Operations Manager) para supervisar la implementación de Lync Server, puede hacer una copia de seguridad de los datos que crea mientras supervisa Lync Server. Use el proceso de copia de seguridad estándar de SQL Server para hacer una copia de seguridad de los archivos de System Center Operations Manager. Estos archivos no se restauran durante la recuperación.

  - **Configuración de puerta de enlace de red telefónica conmutada (RTC)**     Si usa dispositivos de telefonía IP empresarial o de sucursal con funciones de supervivencia, debe realizar una copia de seguridad de la configuración de la puerta de enlace RTC. Consulte con su proveedor para obtener más detalles sobre cómo hacer una copia de seguridad y restaurar configuraciones de puerta de enlace RTC.

  - **Versiones coexistentes de Lync Server u Office Communications Server**     Si su implementación de Lync Server 2013 coexiste con Lync Server 2010 o con una versión anterior de Office Communications Server, no puede usar los procedimientos de este documento para realizar copias de seguridad o restaurar la versión anterior. En lugar de ello, debe seguir los procedimientos de copias de seguridad y restauración documentados específicamente para la versión anterior. Para más detalles sobre cómo realizar copias de seguridad y restaurar Lync Server 2010, consulte [https://go.microsoft.com/fwlink/p/?linkId=265417](https://go.microsoft.com/fwlink/p/?linkid=265417) . Para obtener más información sobre cómo realizar copias de seguridad y restaurar Microsoft Office Communications Server 2007 R2, consulte [https://go.microsoft.com/fwlink/p/?linkId=168162](https://go.microsoft.com/fwlink/p/?linkid=168162) .

  - **Información**     de infraestructura Debe hacer una copia de seguridad de la infraestructura, como la configuración del firewall, la configuración del equilibrio de carga, la configuración de Internet Information Services (IIS), los registros del sistema de nombres de dominio (DNS) y las direcciones IP, y la configuración del Protocolo de configuración dinámica de host (DHCP). Para más información detallada sobre cómo hacer una copia de seguridad de estos componentes, consulte con los proveedores correspondientes.

  - **Mensajería unificada (MU) de Microsoft Exchange y Exchange**     Realice una copia de seguridad y restaure Microsoft Exchange y Exchange UM tal como se describe en la documentación de Microsoft Exchange. Para más detalles sobre cómo realizar copias de seguridad y restaurar Exchange Server 2013, consulte [https://go.microsoft.com/fwlink/?LinkId=285384](https://go.microsoft.com/fwlink/?linkid=285384) . Para más detalles sobre cómo realizar copias de seguridad y restaurar Exchange Server 2010, consulte [https://go.microsoft.com/fwlink/p/?linkId=209179](https://go.microsoft.com/fwlink/p/?linkid=209179) .
    
    Tenga en cuenta que Lync Server 2013 presenta la capacidad de tener listas de contactos de usuarios, fotos de usuarios de alta definición y datos de archivado almacenados en Exchange 2013. Consulte la lista siguiente para ver cómo realizar una copia de seguridad de estos tipos de datos:
    
      - Se realiza una copia de seguridad de las **fotos de alta definición** como parte de la copia de seguridad de Exchange Server.
    
      - El **almacén de contactos unificado** se presenta en Lync Server 2013. Almacén de contactos unificado permite a los usuarios mantener toda su información de contacto en Exchange 2013.
        
        Debe asegurarse de que las copias de seguridad están actualizadas para los usuarios en cuanto a si sus contactos de usuario se almacenan en el almacén de contactos unificados o en el servidor back-end de Lync. Los siguientes escenarios ilustran dónde migrar contactos de usuario al almacén de contactos unificado puede causar problemas en el proceso de copia de seguridad y restauración.
        
        **Escenario 1:** Los contactos de usuario se migran al almacén de contactos unificado y se realiza una restauración desde una copia de seguridad de Lync Server realizada antes de la migración de los contactos de usuario. En este escenario, el usuario tendrá un estado de contactos obsoletos durante un máximo de un día hasta que la tarea de migración de Lync Server comience a migrar los contactos de usuario a Exchange. (Tenga en cuenta que, puesto que los contactos de usuario se han migrado anteriormente al almacén de contactos unificado, se usará la información de contacto de Exchange). No se necesita ninguna intervención del administrador en este escenario.
        
        **Escenario 2:** Los contactos de usuario se almacenaban anteriormente en el almacén de contactos unificados, pero luego se revirtieron. Se realiza una restauración desde una copia de seguridad de Lync Server tomada cuando los contactos de usuario se almacenaron en el almacén de contactos unificado. En este escenario, un mensaje de error de `Error: Incorrect Exchange Version` en los registros del servidor o el cliente de Lyss puede indicar que se trata de un problema. El usuario podrá tener acceso a su lista de contactos en Lync 2013 directamente desde Exchange, pero el estado del cliente no coincidirá con el estado de Lync Server. Para solucionar esto, un administrador tendrá que ejecutar los cmdlets **Invoke-CsUCSRollback** para los usuarios afectados.
    
      - Los **datos de archivado** se pueden almacenar en Exchange 2013. Estos datos no son críticos para Lync Server, pero pueden ser críticos para su organización con fines normativos. Si los datos de archivado se almacenan en Exchange y son críticos para su organización, siga los procedimientos de copia de seguridad y restauración de Exchange. Tenga en cuenta que los datos de archivado almacenados en Exchange no se pueden volver a mover a Lync Server. Además, no hay ninguna forma de mover los datos que ya están almacenados en la base de datos de archivado de Lync a Exchange.

</div>

</div>

<span> </span>

</div>

</div>

</div>

