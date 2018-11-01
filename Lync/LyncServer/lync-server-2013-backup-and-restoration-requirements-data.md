---
title: 'Requisitos de copia de seguridad y restauración: datos'
TOCTitle: 'Requisitos de copia de seguridad y restauración: datos'
ms:assetid: ecfb8e4d-cb4f-476d-9772-4486bd683c04
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Hh202194(v=OCS.15)
ms:contentKeyID: 52061961
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Requisitos de copia de seguridad y restauración: datos

 

_**Última modificación del tema:** 2016-12-08_

Lync Server usa información de parámetros y configuración almacenada en las bases de datos, así como los datos almacenados en bases de datos y almacenes de archivos. En esta sección se describen los datos que necesita guardar en una copia de seguridad para poder restaurar el servicio si ocurre un error o interrupción en la organización y, asimismo, se identifican los datos y componentes usados por Lync Server que debe guardar por separado.

## Requisitos de parámetros y configuración

En este documento se incluyen los procedimientos para hacer una copia de seguridad y restaurar la información de parámetros y configuración necesaria para recuperar el servicio de Lync Server. Esta configuración está ubicada en el Almacén de administración central o en otra base de datos o Servidor Standard Edition back-end.

En la siguiente tabla se recoge la información de parámetros y configuración que se debe guardar en una copia de seguridad y restaurar.

### Datos de parámetros y configuración

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
<td><p>Almacén de administración central (base de datos: Xds.mdf)</p></td>
<td><p>Topología, directivas y opciones de configuración.</p>
<p>Haga la copia de seguridad con el resto de copias de seguridad habituales y, a continuación, use el Panel de control de Lync Server o cmdlets para modificar las configuraciones o directivas.</p></td>
</tr>
<tr class="even">
<td><p>Información de ubicación</p></td>
<td><p>Almacén de administración central (base de datos: Lis.mdf)</p></td>
<td><p>Información de configuración de la telefonía IP empresarial (Enterprise Voice Enhanced 9-1-1, E9-1-1). Esta información generalmente es estática.</p>
<p>Haga la copia de seguridad con el resto de copias de seguridad habituales.</p></td>
</tr>
<tr class="odd">
<td><p>Información de configuración del grupo de respuesta</p></td>
<td><p>Servidor o Servidor Standard Edition back-end (base de datos: RgsConfig.mdf)</p></td>
<td><p>Grupos de agentes, colas y flujos de trabajo de Grupo de respuesta.</p>
<p>Haga la copia de seguridad con el resto de copias de seguridad habituales y después de agregar o modificar grupos de agentes, colas o flujos de trabajo.</p></td>
</tr>
</tbody>
</table>


## Requisitos de datos

A continuación se indican los datos de Lync Server de los que se debe hacer una copia de seguridad para poder restaurar el servicio de Lync Server en caso de que se produzca un error.

Tenga en cuenta que algunos de los tipos de datos no son necesarios para la tarea de restauración. En este tema no se detallan los procedimientos para hacer una copia de seguridad de estos tipos de datos, que son los siguientes:

  - Datos de usuario transitorios, como extremos y suscripciones, servidores de conferencia activos y estados de conferencia transitorios (base de datos: RtcDyn.mdf)

  - Datos de la Libreta de direcciones (bases de datos: Rtcab.mdf y Rtcab1.mdf). La base de datos de la Libreta de direcciones se vuelve a generar automáticamente desde Servicios de dominio de Active Directory.

  - Información dinámica para Aplicación de estacionamiento de llamadas (base de datos: CpsDyn.mdf)

  - Datos de Grupo de respuesta transitorios, como el estado de inicio de sesión de agentes y la información de llamadas en espera (base de datos: RgsDyn.mdf)

  - La base de datos de conformidad del Chat persistente (base de datos: MgcComp.mdf). Si ha habilitado la conformidad de chat persistente, la información almacenada en la base de datos de conformidad del Chat persistente será transitoria siempre que se haya configurado un adaptador que lea la información de la base de datos y la convierta en otro formato. En tal caso, la base de datos de conformidad de Chat persistente se considera como transitoria.
    
    El Servidor de chat persistente de Lync Server 2013 viene con un adaptador de XML. También se pueden instalar adaptadores personalizados que tomen estos datos y los trasladen a otros orígenes, como Exchange Hosted Archive.

En la siguiente tabla se recogen los datos que se deben guardar en una copia de seguridad y restaurar.

### Datos almacenados en bases de datos

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
<td><p>Servidor back-end o Servidor Standard Edition (base de datos: RTCXDS.mdf)</p></td>
<td><p>Derechos de usuario, listas de contacto de usuario, datos de grupos de servidores, conferencias programadas, etc. Estos datos de usuario no incluyen el contenido cargado en una conferencia.</p>
<p>Haga la copia de seguridad con el resto de copias de seguridad habituales. Esta información es dinámica, pero la pérdida de actualizaciones no es catastrófica para Lync Server si debe restaurar la última de las copias de seguridad habituales. Si las listas de contactos son esenciales para la organización, puede hacer una copia de seguridad de estos datos con más frecuencia.</p></td>
</tr>
<tr class="even">
<td><p>Datos de archivado</p></td>
<td><p>Base de datos de archivado (base de datos: LcsLog.mdf)</p>
<p>Estos datos se pueden almacenar en Exchange 2013 si ha habilitado la opción de integración de Microsoft Exchange; de lo contrario, se guardarán en una base de datos de archivado de Lync Server, que puede estar colocada con otra base de datos de Lync Server o de forma independiente en otro servidor de base de datos.</p></td>
<td><p>Mensajería instantánea (MI) y contenido de reuniones.</p>
<p>Estos datos no son esenciales para Lync Server, pero pueden ser esenciales para la organización con fines de cumplimiento de normativas. Determine la programación de copias de seguridad según corresponda.</p>
<p>Lync Server admite solo el modelo de recuperación simple para las bases de datos de archivado. Con el modelo de recuperación simple, las bases de datos se recuperan hasta el momento de la última copia de seguridad completa, lo que significa que no se puede restaurar una base de datos hasta el momento en que se produjo el error o hasta un momento específico.</p></td>
</tr>
<tr class="odd">
<td><p>Datos de supervisión</p></td>
<td><p>Bases de datos de supervisión (LcsCDR.mdf y QoeMetrics.mdf)</p>
<p>Estas bases de datos pueden estar colocadas con otra base de datos de Lync Server o de forma independiente en otro servidor de base de datos.</p></td>
<td><p>Registro detallado de llamadas (LcsCDR.mdf) y métricas de Calidad de la experiencia o QoE (QoeMetrics.mdf).</p>
<p>Las registros detallados de llamadas son dinámicos y pueden ser esenciales para el negocio. Determine la programación de copias de seguridad teniendo en cuenta si se necesitan estos registros con fines de cumplimiento de normativas.</p>
<p>La información de Calidad de la experiencia es dinámica. La pérdida de QoE no es esencial para el funcionamiento de Lync Server, pero puede serlo para el negocio. Determine la programación de copias de seguridad según la importancia que esta información tenga en la organización.</p>
<p>Lync Server admite solo el modelo de recuperación simple para las bases de datos de supervisión. Con el modelo de recuperación simple, las bases de datos se recuperan hasta el momento de la última copia de seguridad completa, lo que significa que no se puede restaurar una base de datos hasta el momento en que se produjo el error o hasta un momento específico.</p></td>
</tr>
<tr class="even">
<td><p>Datos de chat persistente</p></td>
<td><p>Base de datos de chat persistente (mgd.mdf).</p>
<p>Esta base de datos puede estar colocada con otra base de datos de Lync Server o de forma independiente en otro servidor de base de datos.</p></td>
<td><p>Los datos de chat persistente es el contenido de chat real que se está publicando en los salones de chat. Estos datos suelen ser cruciales para la empresa.</p>
<p>Puede optar entre usar la copia de seguridad de SQL Server o exportar la base de datos mediante el cmdlet <strong>Export-CsPersistentChatData</strong> que se incluye en Lync Server. A la hora de recuperar los datos, puede importar y restaurar la base de datos en el punto de la última copia de seguridad completa, lo que significa que no se puede restaurar al momento en el que el error se produjo.</p></td>
</tr>
</tbody>
</table>


## Requisitos de datos de almacén de archivos

En una implementación de Enterprise Edition, el almacén de archivos de Lync Server suele estar en un servidor de archivos, mientras que en una implementación de Standard Edition, el almacén de archivos de Lync Server se encuentra de forma predeterminada en el Servidor Standard Edition. Por lo general, hay un almacén de archivos de Lync Server que se comparte para un sitio. El almacén de archivos de Chat persistente emplea el mismo recurso compartido de archivos que el almacén de archivos de Lync Server.

La ubicación de los almacenes de archivos se identifican con el nombre \\\\servidor\\recurso\_compartido. Para encontrar la ubicación específica de un almacén de archivos, abra Generador de topologías y busque en el nodo **Almacenes de archivos**.

En la siguiente tabla se identifican los almacenes de archivos necesarios para hacer una copia de seguridad y restaurar el servicio.

### Almacenes de archivos

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
<td><p>Generalmente se encuentra en un servidor de archivos, clúster de archivos o en un Servidor Standard Edition</p></td>
<td><p>Contenido de reuniones; metadatos de contenido de reuniones; registros de requisitos de reuniones; archivos de datos de aplicación; archivos de actualización para actualizaciones de dispositivos; archivos de audio para las aplicaciones de grupo de respuesta, estacionamiento de llamadas, aplicaciones de anuncios y archivos publicados en los salones de chat persistente.</p>
<p>Haga la copia de seguridad con el resto de copias de seguridad habituales.</p></td>
</tr>
</tbody>
</table>


## Requisitos adicionales de las copias de seguridad

A fin de garantizar que se van a poder restaurar los servicios de Lync Server en caso de error, se debe guardar una copia de seguridad de algunos componentes necesarios que no forman parte de Lync Server en sí. No se realiza una copia de seguridad ni se restauran los siguientes componentes como parte del proceso de copia de seguridad y restauración de Lync Server que se describe en este documento:

  - **Servicios de dominio de Active Directory**   Debe hacer una copia de seguridad de los servicios de dominio de Active Directory (AD DS) mediante las herramientas de Active Directory al mismo tiempo que hace una copia de seguridad de Lync Server. Es importante que AD DS esté sincronizado con Lync Server, ya que así se evitarán problemas que surgen cuando Lync Server espera unos objetos de contacto que no coinciden con los de AD DS. AD DS almacena las siguientes configuraciones que Lync Server utiliza:
    
      - URI de SIP del usuario y otros parámetros de usuario.
    
      - Objetos de contacto para aplicaciones como Grupo de respuesta y Operador de conferencia.
    
      - Una referencia al almacén de Administración central.
    
      - Cuenta de autenticación Kerberos (objeto de equipo opcional) y grupos de seguridad de Lync Server.
    
    Para obtener información detallada sobre cómo hacer copias de seguridad y restaurar AD DS en Windows Server 2008, consulte la guía paso a paso sobre copias de seguridad y recuperación de AD DS en <http://go.microsoft.com/fwlink/?linkid=209105>.

  - **Entidad de certificación y certificados**   Siga las directivas de la organización para hacer una copia de seguridad de su entidad de certificación y los certificados. Si usa claves privadas exportables, puede hacer una copia de seguridad del certificado y de la clave privada y, luego, exportarlos según los procedimientos detallados en este documento para restaurar Lync Server. Si usa una entidad de certificación interna, puede volver a inscribirse si necesita restaurar Lync Server. Es importante que conserve la clave privada en un lugar seguro donde esté disponible en caso de que se produzca un error en un equipo.

  - **System Center Operations Manager**   Si usa Microsoft System Center Operations Manager (anteriormente Microsoft Operations Manager) para supervisar la implementación de Lync Server, puede hacer una copia de seguridad de los datos que crea mientras está supervisando Lync Server. Siga el proceso estándar de copias de seguridad de SQL Server para hacer una copia de seguridad de los archivos de System Center Operations Manager. Estos archivos no se restauran durante la recuperación.

  - **Configuración de puerta de enlace de red telefónica conmutada (RTC)** Si usa Telefonía IP empresarial o aplicaciones de sucursal con funciones de supervivencia, debe hacer una copia de seguridad de la configuración de la puerta de enlace RTC. Consulte con su proveedor para obtener más detalles sobre cómo hacer una copia de seguridad y restaurar configuraciones de puerta de enlace RTC.

  - **Versiones coexistentes de Lync Server o Office Communications Server**   En caso de que la implementación de Lync Server 2013 coexista con Lync Server 2010 o con una versión anterior de Office Communications Server, no le servirán los procedimientos de este documento para hacer copias de seguridad o restaurar la versión anterior. En lugar de ello, deberá seguir los procedimientos de copia de seguridad y restauración documentados específicamente para la versión anterior. Para obtener información detallada sobre cómo hacer copias de seguridad y restaurar Lync Server 2010, vea <http://go.microsoft.com/fwlink/?linkid=265417>. Para más detalles sobre cómo hacer copias de seguridad y restaurar Microsoft Office Communications Server 2007 R2, vea <http://go.microsoft.com/fwlink/?linkid=168162>.

  - **Información de infraestructura** Debe hacer una copia de seguridad de la información sobre la infraestructura, como la configuración del firewall, configuración del equilibrio de carga, configuración de Internet Information Services (IIS), registros del Sistema de nombres de dominio (DNS) y direcciones IP, además de la configuración del Protocolo de configuración dinámica de host (DHCP). Para obtener información detallada sobre cómo hacer una copia de seguridad de estos componentes, consulte con los proveedores correspondientes.

  - **Microsoft Exchange y mensajería unificada de Exchange (UM)**   Haga una copia de seguridad y restaure Microsoft Exchange y Mensajería unificada de Exchange del modo descrito en la documentación sobre Microsoft Exchange. Para obtener información detallada sobre cómo hacer copias de seguridad y restaurar Exchange Server 2013, vea <http://go.microsoft.com/fwlink/?linkid=285384>. Para obtener información detallada sobre cómo hacer copias de seguridad y restaurar Exchange Server 2010, vea <http://go.microsoft.com/fwlink/?linkid=209179>.
    
    Tenga presente que con Lync Server 2013 se incluyó la posibilidad de almacenar en Exchange 2013 las listas de contactos de usuario, las fotos de usuario de alta definición y los datos de archivado. Consulte la siguiente lista para saber cómo hacer una copia de seguridad de estos tipos de datos:
    
      - Las **fotos de alta definición** se guardan en una copia de seguridad como parte del proceso de copia de seguridad de Exchange Server.
    
      - El **almacén de contactos unificado** apareció con Lync Server 2013, y permite a los usuarios guardar toda su información de contactos en Exchange 2013.
        
        Debe procurar que todas las copias de seguridad estén actualizadas para los usuarios, en el sentido de si los contactos de usuario se almacenan en el almacén de contactos unificado o en el servidor back-end de Lync. Con los siguientes escenarios se ilustra de qué manera la migración de los contactos de usuario al almacén de contactos unificado puede provocar problemas en el proceso de copia de seguridad y restauración.
        
        **Escenario 1:** los contactos de usuario se han migrado al almacén de contactos unificado y se lleva a cabo una restauración a partir de una copia de seguridad de Lync Server realizada antes de dicha migración de contactos. En este escenario, el estado de los contactos aparecerá como desfasado durante un día como máximo, hasta que la tarea de migración de Lync Server empiece a migrar los contactos del usuario a Exchange (observe que, como los usuarios se migraron al almacén de contactos unificado con anterioridad, se usará la información de contactos de Exchange). En este escenario se prescinde de la intervención del administrador.
        
        **Escenario 2:** los contactos del usuario estaban almacenados previamente en el almacén de contactos unificado, pero luego se revertieron. Se realiza una restauración a partir de una copia de seguridad de Lync Server que se hizo cuando los contactos del usuario estaban almacenados en el almacén de contactos unificado. En este escenario, un mensaje de error de tipo `Error: Incorrect Exchange Version` en el cliente o en los registros de servidor de Lyss puede considerar esto como un problema. El usuario podrá acceder a su lista de contactos en Lync 2013 directamente desde Exchange, pero el estado del cliente no coincidirá con el de Lync Server. Para solucionarlo, un administrador deberá ejecutar los cmdlets **Invoke-CsUCSRollback** para los usuarios afectados.
    
      - Los **datos de archivado** se pueden almacenar en Exchange 2013. Estos datos no son esenciales para Lync Server, pero pueden serlo para la organización con fines de cumplimiento de normativas. Si los datos de archivado se almacenan en Exchange y son esenciales en la organización, siga los procedimientos de copia de seguridad y restauración de Exchange. Tenga en cuenta que los datos de archivado almacenados en Exchange no pueden volver a trasladarse a Lync Server. Además, no existe forma de mover a Exchange los datos que ya están almacenados en la base de datos de archivado de Lync.

