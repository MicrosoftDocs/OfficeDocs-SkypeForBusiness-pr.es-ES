---
title: "Lync Server 2013: Solicitar y configurar un certificado para el proxy HTTP inverso"
TOCTitle: Solicitar y configurar un certificado para el proxy HTTP inverso
ms:assetid: 4b70991e-5f10-40a3-b069-0b227c3a3a0a
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg429704(v=OCS.15)
ms:contentKeyID: 48275203
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Solicitar y configurar un certificado para el proxy HTTP inverso en Lync Server 2013

 

_**Última modificación del tema:** 2016-12-08_

Tiene que instalar el certificado de la entidad de certificación raíz (CA) en el servidor en el que se ejecuta Microsoft Forefront Threat Management Gateway 2010 o IIS ARR para la infraestructura de CA que emitió los certificados de servidor para los servidores internos en los que se ejecuta Microsoft Lync Server 2013.

También puede instalar un certificado de servidor Web público en el servidor de proxy inverso. Los nombres alternativos del sujeto de este certificado deberán contener los nombres de dominio completo (FQDN) externos publicados de cada grupo de servidores que hospeda a usuarios habilitados para acceso remoto y los FQDN externos de todos los directores o grupos de directores que se usarán en dicha infraestructura perimetral. El nombre alternativo de sujeto debe incluir también la URL sencilla de la reunión, la URL sencilla de marcado y, si implementa aplicaciones móviles y planea usar la detección automática, la URL externa del servicio Detección automática, tal como se muestra en la tabla siguiente.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>Valor</th>
<th>Ejemplo</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Nombre de sujeto</p></td>
<td><p>FQDN del grupo de servidores</p></td>
<td><p>webext.contoso.com</p></td>
</tr>
<tr class="even">
<td><p>Nombre alternativo de sujeto</p></td>
<td><p>FQDN del grupo de servidores</p></td>
<td><p>webext.contoso.com</p>
<div>

> [!IMPORTANT]  
> El nombre de sujeto también debe estar presente en el nombre alternativo de sujeto.


</div></td>
</tr>
<tr class="odd">
<td><p>Nombre alternativo de sujeto</p></td>
<td><p>Servicios web de Director opcionales (si se implementa Director)</p></td>
<td><p>webdirext.contoso.com</p></td>
</tr>
<tr class="even">
<td><p>Nombre alternativo de sujeto</p></td>
<td><p>URL sencilla de reunión</p>
<div>

> [!NOTE]
> Todas las URL sencillas de reunión deben incluirse en el nombre alternativo de sujeto. Cada dominio SIP debe tener al menos una URL sencilla de reunión activa.


</div></td>
<td><p>meet.contoso.com</p></td>
</tr>
<tr class="odd">
<td><p>Nombre alternativo de sujeto</p></td>
<td><p>URL sencilla de marcado</p></td>
<td><p>dialin.contoso.com</p></td>
</tr>
<tr class="even">
<td><p>Nombre alternativo de sujeto</p></td>
<td><p>Servidor Office Web Apps</p></td>
<td><p>officewebapps01.contoso.com</p></td>
</tr>
<tr class="odd">
<td><p>Nombre alternativo de sujeto</p></td>
<td><p>URL externa del servicio Detección automática</p></td>
<td><p>lyncdiscover.contoso.com</p>
<div>

> [!NOTE]
> Si además está usando Microsoft Exchange Server también necesitará configurar reglas de proxy inverso para las direcciones URL de servicios web y detección automática de Exchange.


</div></td>
</tr>
</tbody>
</table>



> [!NOTE]
> Si la implementación interna está formada por más de un servidor Standard Edition o grupo de servidores front-end, deberá configurar reglas de publicación de web para cada FQDN de la granja de servidores web externo y también necesitará un certificado y una escucha de web para cada uno o deberá obtener un certificado cuyo nombre alternativo de sujeto contenga los nombres que usan todos los grupos de servidores, asignarlo a una escucha de web y compartirlo entre las varias reglas de publicación de web.



## Crear una solicitud de certificado

Puede crear una solicitud de certificado en el proxy inverso. Puede crear una solicitud en otro equipo, pero debe exportar el certificado firmado con la clave privada e importarlo al proxy inverso una vez que lo haya recibido desde la entidad de certificación pública.


> [!NOTE]
> Una solicitud de certificado o solicitud de firma de certificado (CSR) es una solicitud para una autoridad de certificación pública (CA) para validar y firmar la clave pública del equipo solicitante. Cuando se genera un certificado, se crean una clave pública y una clave privada. Solo la clave pública se comparte y se firma. Como el nombre lo sugiere, la clave pública está disponible para cualquier solicitud pública. La clave pública es para el uso de los clientes, servidores y otros solicitantes que necesiten intercambiar información de forma segura y validar la identidad de un equipo. La clave privada se mantiene protegida y la usa únicamente el equipo que creó el par de claves para descifrar mensajes cifrados con su clave pública. La clave privada se puede usar para otros fines. Para fines de proxy inverso, el cifrado de datos es el uso principal. En segundo lugar, la autenticación de certificado en el nivel de la clave de certificado es otro uso y se limita únicamente a la validación de que un solicitante tiene la clave pública del equipo o que el equipo para el que se tiene la clave pública es el real.



> [!TIP]  
> Si planea los certificados de Servidor perimetral y los certificados de proxy inverso al mismo tiempo, debe tener en cuenta que hay mucha semejanza entre los dos requisitos de certificados. Cuando configura y solicita el certificado de Servidor perimetral, combine los nombres alternativos del sujeto de proxy inverso y Servidor perimetral. Puede usar el mismo certificado para el proxy inverso si exporta el certificado y la clave privada, copia el archivo exportado al proxy inverso y, a continuación, importa el par certificado/clave y lo asigna según sea necesario en los próximos procedimientos. Consulte los requisitos del certificado para Servidor perimetral  <a href="lync-server-2013-plan-for-edge-server-certificates.md">Plan para certificados de servidores perimetrales en Lync Server 2013</a> y el proxy inverso <a href="lync-server-2013-certificate-summary-reverse-proxy.md">Resumen de certificado - Proxy inverso en Lync Server 2013</a>. Asegúrese de crear el certificado con una clave privada exportable. La creación del certificado y la solicitud del certificado con una clave privada exportable se requiere para los grupos de Servidores perimetrales, por lo que se trata de una práctica normal y el Asistente para certificados en Asistente para la implementación de Lync Server para Servidor perimetral le permitirá establecer la marca <strong>Hacer exportable la clave privada</strong>. Una vez que vuelve a recibir la solicitud de certificado de la autoridad de certificación pública, podrá exportar el certificado y la clave privada. Consulte la sección “Para exportar el certificado con la clave privada para servidores perimetrales de un grupo” en el tema <a href="lync-server-2013-set-up-certificates-for-the-external-edge-interface.md">Configurar certificados para la interfaz perimetral externa en Lync Server 2013</a> para obtener detalles acerca de cómo crear y exportar el certificado con una clave privada. La extensión del certificado debe ser de tipo <strong>.pfx</strong>.



Para generar una solicitud de firma de certificado en el equipo en el que se asignarán el certificado y la clave privada, lleve a cabo el siguiente procedimiento:

**Creación de una solicitud de firma de certificado**

1.  Abra Microsoft Management Console (MMC) y agregue el complemento Certificados y seleccione **Equipos**. A continuación, expanda **Personal**. Para obtener detalles acerca de cómo crear una consola de certificados en Microsoft Management Console (MMC), consulte [http://go.microsoft.com/fwlink/?LinkId=282616](http://go.microsoft.com/fwlink/?linkid=282616).

2.  Haga clic con el botón secundario en **Certificados**, haga clic en **Todas las tareas**, en **Operaciones avanzadas** y en **Crear solicitud personalizada**.

3.  En la página **Inscripción de certificado**, haga clic en **Siguiente**.

4.  En la página **Seleccionar directiva de inscripción de certificados** en **Solicitud personalizada**, seleccione **Continuar sin directiva de inscripción**. Haga clic en **Siguiente**.

5.  En la página **Solicitud personalizada**, para **Plantilla** seleccione **Clave heredada (sin plantilla)**. A menos que su proveedor de certificado indique lo contrario, deje desactivada la casilla **Suprimir las extensiones predeterminadas** y la selección en **Formato de la solicitud** en **PKCS \#10**. Haga clic en **Siguiente**.

6.  En la página **Información del certificado**, haga clic en **Detalles** y, a continuación, en **Propiedades**.

7.  En la página **Propiedades de certificado** en la pestaña **General** en el campo **Nombre descriptivo**, escriba un nombre para este certificado. Opcionalmente, escriba una descripción en el campo **Descripción**. El administrador usa normalmente el nombre descriptivo y la descripción para identificar el propósito del certificado, tal como **Escucha de proxy inverso para Lync Server**.

8.  Seleccione la pestaña **Sujeto**. En **Nombre de sujeto** para el **Tipo**, seleccione **Nombre común** para el tipo de nombre del sujeto. Para el **Valor**, escriba el nombre de sujeto que usará para el proxy inverso y, a continuación, haga clic en **Agregar**. En el ejemplo proporcionado en la tabla de este tema, el nombre de sujeto es webext.contoso.com y se escribiría en el campo Valor del nombre de sujeto.

9.  En la pestaña **Sujeto** en **Nombre alternativo**, seleccione **DNS** del menú desplegable para **Tipo**. Para cada nombre alternativo de sujeto definido que necesite en el certificado, escriba el nombre de dominio completo y, a continuación, haga clic en **Agregar**. Por ejemplo, en la tabla hay tres nombres alternativos de sujeto, meet.contoso.com, dialin.contoso.com y lyncdiscover.contoso.com. En el campo **Valor**, escriba meet.contoso.com y, a continuación, haga clic en **Agregar**. Repita para cada nombre alternativo de sujeto que necesite definir.

10. En la página **Propiedades de certificado**, haga clic en la pestaña **Extensiones**. En esta página, definirá los propósitos de las claves criptográficas en **Uso de la clave** y el uso de la clave extendida en **Uso de clave extendida (directivas de aplicación)**.

11. Haga clic en la flecha **Uso de la clave** para mostrar las **Opciones disponibles**. En Opciones disponibles, haga clic en **Firma digital** y, a continuación, en **Agregar**. Haga clic en **Cifrado de clave** y, a continuación, en **Agregar**. Si la casilla para **Hacer que estos usos de clave sean críticos** está desactivada, actívela.

12. Haga clic en la flecha **Uso de clave extendida (directivas de aplicación)** para mostrar las **Opciones disponibles**. En Opciones disponibles, haga clic en **Autenticación de servidor** y, a continuación, en **Agregar**. Haga clic en **Autenticación de cliente** y, a continuación, en **Agregar**. Si la casilla para **Hacer que el uso de la clave extendida sea crítico** está activada, desactívela. A diferencia de la casilla para el uso de clave (que debe estar activada), debe asegurarse de que la casilla de uso de la clave extendida no esté activada.

13. En la página **Propiedades de certificado**, haga clic en la pestaña **Clave privada**. Haga clic en la flecha **Opciones de clave**. Para **Tamaño de la clave**, seleccione **2048** del menú desplegable. Si va a generar este par de claves y CSR en un equipo distinto al proxy inverso para el que se destina este certificado, active la casilla **Hacer exportable la clave privada**.
    
    <table>
    <thead>
    <tr class="header">
    <th><img src="images/Gg399038.security(OCS.15).gif" title="security" alt="security" />Seguridad Nota:</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td>Por lo general, se aconseja activar <strong>Hacer exportable la clave privada</strong> cuando se cuenta con más de un proxy inverso en una granja de servidores porque se copiará el certificado y la clave privada en cada máquina de la granja. Si permite una clave privada exportable, debe tener cuidado adicional con el certificado y el equipo en el que se genera. La clave privada, si está en riesgo, inutilizará el certificado además de que expondrá potencialmente al equipo o los equipos al acceso externo y otras vulnerabilidades de seguridad.</td>
    </tr>
    </tbody>
    </table>


14. En la pestaña **Clave privada**, haga clic en la flecha **Tipo de clave**. Seleccione la opción **Exchange**.

15. Haga clic en **Aceptar** para guardar las **Propiedades de certificado** que haya establecido.

16. En la página **Inscripción de certificado**, haga clic en **Siguiente**.

17. En la página **¿Dónde desea almacenar la solicitud sin conexión?**, se le pedirá un **Nombre de archivo** y un **Formato de archivo** para guardar la solicitud de firma del certificado.

18. En el campo de entrada **Nombre de archivo**, escriba una ruta de acceso y un nombre de archivo para la solicitud, o bien haga clic en **Examinar** para seleccionar una ubicación para el archivo y escriba el nombre de archivo para la solicitud.

19. Para **Formato de archivo**, haga clic en **Base 64** o **Binario**. Seleccione **Base 64** a menos que el proveedor de sus certificados le indique lo contrario.

20. Localice el archivo de solicitud que guardó en el paso anterior. Envíelo a la autoridad de certificación pública.
    
    > [!IMPORTANT]  
    > Microsoft ha identificado entidades emisoras públicas que cumplen con los requisitos para los fines de comunicaciones unificadas. Se mantiene una lista en el siguiente artículo de Knowledge Base. <a href="http://go.microsoft.com/fwlink/?linkid=282625">http://go.microsoft.com/fwlink/?LinkId=282625</a>
    

