---
title: Solicitar y configurar un certificado para el proxy HTTP inverso
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Request and configure a certificate for your reverse HTTP proxy
ms:assetid: 4b70991e-5f10-40a3-b069-0b227c3a3a0a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429704(v=OCS.15)
ms:contentKeyID: 48184085
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ffe1ce6a4b206b927b2fcdec4c02b905e01d5bd1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823311"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="request-and-configure-a-certificate-for-your-reverse-http-proxy-in-lync-server-2013"></a>Solicitar y configurar un certificado para el proxy HTTP inverso en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-02-14_

Debe instalar el certificado de la entidad emisora de certificados raíz (CA) en el servidor que ejecuta Microsoft Forefront Threat Management Gateway 2010 o IIS ARR para la infraestructura de CA que emitió los certificados de servidor a los servidores internos que ejecutan Microsoft Lync. Server 2013.

También debe instalar un certificado de servidor web público en el servidor proxy inverso. Los nombres alternativos de los sujetos de este certificado deben contener los nombres de dominio completos (FQDN) externos de cada grupo que está en la parte principal de los usuarios habilitados para acceso remoto, y los FQDN externos de todos los directores o grupos de directores que se usarán en esa infraestructura perimetral. El nombre alternativo del sujeto también debe contener la dirección URL simple de la reunión, la dirección URL simple de acceso telefónico y, si está implementando aplicaciones móviles y va a usar la detección automática, la dirección URL del servicio de detección automática externa tal como se muestra en la tabla siguiente.


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
<td><p>Nombre del asunto</p></td>
<td><p>FQDN del grupo de servidores</p></td>
<td><p>webext.contoso.com</p></td>
</tr>
<tr class="even">
<td><p>Nombre alternativo de sujeto</p></td>
<td><p>FQDN del grupo de servidores</p></td>
<td><p>webext.contoso.com</p>



> [!IMPORTANT]
> El nombre del asunto también debe estar presente en el nombre alternativo del firmante.

</td>
</tr>
<tr class="odd">
<td><p>Nombre alternativo de sujeto</p></td>
<td><p>Servicios Web de directores opcionales (si el director está implementado)</p></td>
<td><p>webdirext.contoso.com</p></td>
</tr>
<tr class="even">
<td><p>Nombre alternativo de sujeto</p></td>
<td><p>Dirección URL simple de la reunión</p>



> [!NOTE]
> Todas las direcciones URL simples de la reunión deben encontrarse en el nombre alternativo del firmante. Cada dominio SIP debe tener al menos una dirección URL simple de la reunión activa.

</td>
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
<td><p>Dirección URL del servicio de detección automática externa</p></td>
<td><p>lyncdiscover.contoso.com</p>



> [!NOTE]
> Si también usa Microsoft Exchange Server, también tendrá que configurar las reglas de proxy inverso para las direcciones URL de Autodiscover y servicios Web de Exchange.

</td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]
> Si su implementación interna consta de más de un servidor Standard Edition o un grupo de servidores front-end, debe configurar reglas de publicación web para cada FQDN de granja de servidores Web externo y necesitará un certificado y una escucha de web para cada uno, o debe obtener un certificado. el nombre de sujeto alternativo contiene los nombres que se usan en todas las agrupaciones, la asigna a una escucha de web y la comparte entre varias reglas de publicación Web.



</div>

<div>

## <a name="create-a-certificate-request"></a>Crear una solicitud de certificado

Crear una solicitud de certificado en el proxy inverso. Usted crea una solicitud en otro equipo, pero debe exportar el certificado firmado con la clave privada e importarlo en el proxy inverso una vez que lo haya recibido de la entidad de certificación pública.

<div>


> [!NOTE]
> Una solicitud de certificado o una solicitud de firma de certificado (CSR) es una solicitud a una entidad de certificación (CA) pública de confianza para validar y firmar la clave pública del equipo de solicitud. Cuando se genera un certificado, se crea una clave pública y una clave privada. Solo la clave pública está compartida y firmada. Como su nombre indica, la clave pública está disponible para cualquier solicitud pública. La clave pública es para que la usen los clientes, los servidores y otros solicitantes que necesiten intercambiar información de forma segura y validar la identidad de un equipo. La clave privada se mantiene protegida y solo la usa el equipo que creó el par de claves para descifrar mensajes cifrados con su clave pública. La clave privada se puede usar para otros fines. Para fines de proxy inverso, el cifrado de datos es el uso principal. Secondarily, la autenticación de certificados en el nivel de clave de certificado es otro uso, y solo se limita a la validación de que un solicitante tiene la clave pública del equipo o que el equipo al que tiene una clave pública es realmente el equipo que dice ser.



</div>

<div>


> [!TIP]
> Si planea los certificados de su servidor perimetral y los certificados de proxy inverso al mismo tiempo, debe tener en cuenta que hay una gran similitud entre los dos requisitos de los certificados. Cuando configure y solicite el certificado del servidor perimetral, combine los nombres alternativos con el servidor perimetral y el proxy inverso. Puede usar el mismo certificado para el proxy inverso si exporte el certificado y la clave privada, y copie el archivo exportado en el proxy inverso y, a continuación, importe el par de certificado o clave y asígnelo según sea necesario en los procedimientos que se describen a continuación. Consulte los requisitos de certificado para el plan de&nbsp;servidores perimetrales<A href="lync-server-2013-plan-for-edge-server-certificates.md">para los certificados de servidor perimetral en Lync Server 2013</A> y el resumen del certificado de proxy inverso <A href="lync-server-2013-certificate-summary-reverse-proxy.md">: proxy inverso en Lync Server 2013</A>. Asegúrese de crear el certificado con una clave privada exportable. La creación del certificado y de la solicitud de certificados con una clave privada exportable es necesaria para los servidores perimetrales agrupados, por lo que esto es una práctica normal, y el Asistente de certificados del asistente de implementación de Lync Server para el servidor perimetral le permitirá establecer la <STRONG>marca marca de exportación de clave privada</STRONG> . Una vez que reciba de nuevo la solicitud de certificado de la entidad emisora de certificados pública, exportará el certificado y la clave privada. Consulte la sección "para exportar el certificado con la clave privada para servidores perimetrales en un grupo" en el tema <A href="lync-server-2013-set-up-certificates-for-the-external-edge-interface.md">configurar certificados para la interfaz de borde externo para Lync Server 2013</A> para obtener más información sobre cómo crear y exportar el certificado con una clave privada. La extensión del certificado debe ser de tipo <STRONG>. pfx</STRONG>.



</div>

Para generar una solicitud de firma de certificado en el equipo en el que se asignará el certificado y la clave privada, haga lo siguiente:

**Crear una solicitud de firma de certificado**

1.  Abra Microsoft Management Console (MMC), agregue el complemento certificados, seleccione **equipos**y, a continuación, expanda **personal**. Para obtener más información sobre cómo crear una consola de certificados en la consola de administración de Microsoft ( [http://go.microsoft.com/fwlink/?LinkId=282616](http://go.microsoft.com/fwlink/?linkid=282616)MMC), consulte.

2.  Haga clic con el botón derecho en **certificados**, haga clic en **todas las tareas**, en **operaciones avanzadas**y en **crear solicitud personalizada**.

3.  En la página **inscripción de certificados** , haga clic en **siguiente**.

4.  En la página **seleccionar Directiva de inscripción de certificados** , en **solicitud personalizada**, seleccione **continuar sin directiva de inscripción**. Haga clic en **Siguiente**.

5.  En la página de **solicitud personalizada** , para la clave de selección de **plantilla** **(sin plantilla) heredada**. A menos que su proveedor de certificados le indique lo contrario, deje **suprimir las extensiones** predeterminadas desactivadas y la **solicitud de formato** seleccionado en **PKCS \#10**. Haga clic en **Siguiente**.

6.  En la página **información del certificado** , haga clic en **detalles**y, a continuación, en **propiedades**.

7.  En la página de **propiedades del certificado** , en la pestaña **General** , en el campo **nombre descriptivo** , escriba un nombre para este certificado. De manera opcional, escriba una descripción en el campo **Descripción** . El administrador suele usar el nombre descriptivo y la descripción para identificar cuál es el propósito del certificado, como la **escucha de proxy invertida para Lync Server**.

8.  Seleccione la pestaña **asunto** . En **nombre del sujeto** del **tipo**, seleccione **nombre común** para el tipo de nombre de sujeto. Para el **valor**, escriba el nombre del asunto que usará para el proxy inverso y, a continuación, haga clic en **Agregar**. En el ejemplo que se proporciona en la tabla de este tema, el nombre del asunto es webext.contoso.com y se escribiría en el campo de valor del nombre del asunto.

9.  En la pestaña **asunto** , en **nombre alternativo**, seleccione **DNS** de la lista desplegable para **tipo**. Para cada nombre alternativo de asunto definido que necesite en el certificado, escriba el nombre de dominio completo y, a continuación, haga clic en **Agregar**. Por ejemplo, en la tabla hay tres nombres alternativos de asunto, meet.contoso.com, dialin.contoso.com y lyncdiscover.contoso.com. En el campo **valor** , escriba meet.contoso.com y, a continuación, haga clic en **Agregar**. Repita el procedimiento para cada uno de los nombres alternativos de asunto que necesite definir.

10. En la página de **propiedades del certificado** , haga clic en la pestaña **extensiones** . En esta página, definirá los objetivos de las claves criptográficas en **uso de claves** y el uso de claves extendidas en el **uso mejorado de claves (directivas de aplicación)**.

11. Haga clic en la flecha **uso de clave** para mostrar las **opciones disponibles**. En opciones disponibles, haga clic en **firma digital**y, a continuación, en **Agregar**. Haga clic en cifrado de **clave**y, a continuación, en **Agregar**. Si la casilla para **hacer que estos usos de claves sean críticas** no está marcada, active la casilla.

12. Haga clic en la flecha **uso de clave extendida (directivas de aplicación)** para mostrar las **opciones disponibles**. En opciones disponibles, haga clic en **autenticación de servidor**y luego en **Agregar**. Haga clic en **autenticación de cliente**y luego en **Agregar**. Si la casilla para **hacer que los usos extendidos de claves** estén marcadas, anule la selección de la casilla. Al contrario que la casilla de uso de claves (que debe estar activada), debe asegurarse de que la casilla uso de clave extendida no esté activada.

13. En la página de **propiedades del certificado** , haga clic en la pestaña **clave privada** . Haga clic en la flecha **Opciones de clave** . En **tamaño de clave**, seleccione **2048** de la lista desplegable. Si está generando este par de claves y CSR en un equipo distinto del proxy inverso para el que se ha diseñado este certificado, seleccione hacer que la **clave privada**sea exportable.
    
    <div>
    
    <table>
    <thead>
    <tr class="header">
    <th><img src="images/Gg398321.security(OCS.15).gif" title="seguridad" alt="security" />Nota de seguridad:</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td>La selección de <strong>hacer que una clave privada</strong> sea exportable se suele aconsejar cuando tiene más de un proxy inverso en una granja de servidores porque copiará el certificado y la clave privada en cada uno de los equipos de la granja. Si permite una clave privada exportable, debe tener especial cuidado con el certificado y el equipo en el que está generada. La clave privada, si se pone en peligro, representará el certificado sin utilidad, y también expondrá el equipo o equipos a acceso externo y otras vulnerabilidades de seguridad.</td>
    </tr>
    </tbody>
    </table>
    
    </div>

14. En la pestaña **clave privada** , haga clic en la flecha **tipo de clave** . Seleccione la opción **Exchange** .

15. Haga clic en **Aceptar** para guardar las **propiedades del certificado** que ha establecido.

16. En la página **inscripción de certificados** , haga clic en **siguiente**.

17. En la página **¿dónde desea guardar la solicitud sin conexión?** , se le pedirá un nombre de **archivo** y un **formato de archivo** para guardar la solicitud de firma de certificado.

18. En el campo de entrada **nombre de archivo** , escriba una ruta y un nombre de archivo para la solicitud, o haga clic en **examinar** para seleccionar una ubicación para el archivo y escriba el nombre de archivo de la solicitud.

19. En **formato de archivo**, haga clic en **base 64** o en **binario**. Seleccione **64 base** a menos que el proveedor le indique lo contrario.

20. Busque el archivo de solicitud que guardó en el paso anterior. Envía a tu entidad de certificación pública.
    
    <div>
    

    > [!IMPORTANT]
    > Microsoft ha identificado entidades emisoras públicas que cumplen con los requisitos de las comunicaciones unificadas. Una lista se mantiene en el siguiente artículo de Knowledge base. <A href="http://go.microsoft.com/fwlink/?linkid=282625">http://go.microsoft.com/fwlink/?LinkId=282625</A>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

