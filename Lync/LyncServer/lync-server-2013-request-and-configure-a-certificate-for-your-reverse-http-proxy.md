---
title: Solicitar y configurar un certificado para el proxy HTTP inverso
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Request and configure a certificate for your reverse HTTP proxy
ms:assetid: 4b70991e-5f10-40a3-b069-0b227c3a3a0a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429704(v=OCS.15)
ms:contentKeyID: 48184085
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9c380cb67e1e156bef616f81ce0c42f699b472d8
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144947"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="request-and-configure-a-certificate-for-your-reverse-http-proxy-in-lync-server-2013"></a>Solicitar y configurar un certificado para el proxy HTTP inverso en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-02-14_

Debe instalar el certificado de la entidad de certificación raíz (CA) en el servidor que ejecuta Microsoft Forefront Threat Management Gateway 2010 o IIS ARR para la infraestructura de CA que emitió los certificados de servidor a los servidores internos que ejecutan Microsoft Lync. Servidor 2013.

También debe instalar un certificado de servidor web público en el servidor de proxy inverso. Los nombres alternativos del sujeto de este certificado deben contener los nombres de dominio completos (FQDN) externos publicados de cada grupo de servidores que se hospedan en los usuarios habilitados para acceso remoto, y los FQDN externos de todos los directores o grupos de directores que se usarán en esa infraestructura perimetral. El nombre de sujeto alternativo también debe contener la dirección URL simple de la reunión, la dirección URL simple de marcación y, si desea implementar aplicaciones móviles y planea usar el servicio de detección automática, la dirección URL del servicio de autodetección externo tal como se muestra en la tabla siguiente.


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



> [!IMPORTANT]
> El nombre del sujeto también debe estar presente en el nombre alternativo del sujeto.

</td>
</tr>
<tr class="odd">
<td><p>Nombre alternativo de sujeto</p></td>
<td><p>Servicios Web de Director opcional (si se implementa el director)</p></td>
<td><p>webdirext.contoso.com</p></td>
</tr>
<tr class="even">
<td><p>Nombre alternativo de sujeto</p></td>
<td><p>URL sencilla de reunión</p>



> [!NOTE]
> Todas las URL sencillas de reunión deben incluirse en el nombre alternativo de sujeto. Cada dominio SIP debe tener al menos una URL sencilla de reunión activa.

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
<td><p>URL externa del servicio Detección automática</p></td>
<td><p>lyncdiscover.contoso.com</p>



> [!NOTE]
> Si también usa Microsoft Exchange Server, también tendrá que configurar las reglas de proxy inverso para las direcciones URL de Exchange Autodiscover y servicios Web.

</td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]
> Si la implementación interna está formada por más de un servidor Standard Edition o grupo de servidores front-end, deberá configurar reglas de publicación de web para cada FQDN de la granja de servidores web externo y también necesitará un certificado y una escucha de web para cada uno o deberá obtener un certificado cuyo nombre alternativo de sujeto contenga los nombres que usan todos los grupos de servidores, asignarlo a una escucha de web y compartirlo entre las varias reglas de publicación de web.



</div>

<div>

## <a name="create-a-certificate-request"></a>Crear una solicitud de certificado

Cree una solicitud de certificado en el proxy inverso. Crea una solicitud en otro equipo, pero debe exportar el certificado firmado con la clave privada e importarlo en el proxy inverso una vez que lo haya recibido de la entidad de certificación pública.

<div>


> [!NOTE]
> Una solicitud de certificado o una solicitud de firma de certificado (CSR) es una solicitud a una entidad de certificación pública de confianza (CA) para validar y firmar la clave pública del equipo de solicitud. Cuando se genera un certificado, se crea una clave pública y una clave privada. Solo se comparte y firma la clave pública. Como su nombre implica, la clave pública se pone a disposición de cualquier solicitud pública. La clave pública es para su uso por parte de clientes, servidores y otros solicitantes que necesitan intercambiar información de forma segura y validar la identidad de un equipo. La clave privada se mantiene protegida y solo la usa el equipo que creó el par de claves para descifrar los mensajes cifrados con su clave pública. La clave privada se puede usar para otros fines. Para fines de proxy inverso, el cifrado de datos es el uso principal. Secondarily, la autenticación del certificado en el nivel de clave del certificado es otro uso y solo está limitada a la validación de que un solicitante tiene la clave pública del equipo, o que el equipo para el que tiene una clave pública es realmente el equipo que dice ser.



</div>

<div>


> [!TIP]
> Si planea los certificados del servidor perimetral y los certificados de proxy inverso al mismo tiempo, debe tener en cuenta que hay un gran grado de similitud entre los dos requisitos de los certificados. Cuando configure y solicite el certificado del servidor perimetral, combine el servidor perimetral y los nombres alternativos del sujeto del proxy inverso. Puede usar el mismo certificado para el proxy inverso Si exporta el certificado y la clave privada, y copia el archivo exportado en el proxy inverso y, a continuación, importa el par de certificado/clave y lo asigna según sea necesario en los procedimientos siguientes. Consulte los requisitos de certificado para el plan del&nbsp;servidor perimetral<A href="lync-server-2013-plan-for-edge-server-certificates.md">para los certificados del servidor perimetral en Lync Server 2013</A> y el resumen del certificado de proxy inverso <A href="lync-server-2013-certificate-summary-reverse-proxy.md">-proxy inverso en Lync Server 2013</A>. Asegúrese de crear el certificado con una clave privada exportable. La creación del certificado y la solicitud de certificado con una clave privada exportable es necesaria para los servidores perimetrales agrupados, por lo que se trata de un procedimiento normal y el Asistente para la implementación de Lync Server para el servidor perimetral le permitirá establecer la marca de <STRONG>hacer que la clave privada sea exportable</STRONG> . Una vez que haya recibido la solicitud de certificado de la entidad de certificación pública, deberá exportar el certificado y la clave privada. Consulte la sección "para exportar el certificado con la clave privada para servidores perimetrales en un grupo de servidores" en el tema set up Certificates for <A href="lync-server-2013-set-up-certificates-for-the-external-edge-interface.md">The external Edge Interface for Lync Server 2013</A> para obtener más información sobre cómo crear y exportar el certificado con una clave privada. La extensión del certificado debe ser del tipo <STRONG>. pfx</STRONG>.



</div>

Para generar una solicitud de firma de certificado en el equipo donde se asignará el certificado y la clave privada, haga lo siguiente:

**Creación de una solicitud de firma de certificado**

1.  Abra Microsoft Management Console (MMC), agregue el complemento certificados y seleccione **equipos**y, a continuación, expanda **personal**. Para obtener más información sobre cómo crear una consola de certificados en Microsoft Management Console (MMC), [https://go.microsoft.com/fwlink/?LinkId=282616](https://go.microsoft.com/fwlink/?linkid=282616)consulte.

2.  Haga clic con el botón secundario en **certificados**, haga clic en **todas las tareas**y en **operaciones avanzadas**, haga clic en **crear solicitud personalizada**.

3.  En la página **inscripción de certificado** , haga clic en **siguiente**.

4.  En la página **seleccionar Directiva de inscripción de certificados** , en **solicitud personalizada**, seleccione **continuar sin directiva de inscripción**. Haga clic en **Siguiente**.

5.  En la página **solicitud personalizada** , para la clave de **plantilla** **(sin plantilla) heredada**. A menos que su proveedor de certificados le indique lo contrario, deje **suprimir las extensiones predeterminadas** desactivadas y la selección de **formato de solicitud** en **PKCS \#10**. Haga clic en **Siguiente**.

6.  En la página **información del certificado** , haga clic en **detalles**y, a continuación, en **propiedades**.

7.  En la página de **propiedades del certificado** , en la ficha **General** , en el campo **nombre descriptivo** , escriba un nombre para este certificado. Si lo desea, puede escribir una descripción en el campo **Descripción** . El administrador suele usar el nombre descriptivo y la descripción para identificar cuál es el propósito del certificado, como la **escucha de proxy inverso para Lync Server**.

8.  Seleccione la pestaña **asunto** . En **nombre de sujeto** del **tipo**, seleccione **nombre común** para el tipo de nombre de sujeto. Para el **valor**, escriba el nombre de sujeto que va a usar para el proxy inverso y, a continuación, haga clic en **Agregar**. En el ejemplo que se proporciona en la tabla de este tema, el nombre del sujeto es webext.contoso.com y se escribiría en el campo valor para el nombre del sujeto.

9.  En la ficha **asunto** , en **nombre alternativo**, seleccione **DNS** en el menú desplegable para **tipo**. Para cada nombre alternativo de sujeto definido que necesite en el certificado, escriba el nombre de dominio completo y, a continuación, haga clic en **Agregar**. Por ejemplo, en la tabla hay tres nombres alternativos de sujeto, meet.contoso.com, dialin.contoso.com y lyncdiscover.contoso.com. En el campo **valor** , escriba meet.contoso.com y, a continuación, haga clic en **Agregar**. Repita el procedimiento para cada uno de los nombres alternativos de sujeto que necesite definir.

10. En la página de **propiedades del certificado** , haga clic en la ficha **extensiones** . En esta página, se definen los objetivos de la clave de cifrado en **uso clave** y el uso de la clave extendida en el **uso mejorado de clave (directivas de aplicación)**.

11. Haga clic en la flecha **uso de clave** para mostrar las **opciones disponibles**. En opciones disponibles, haga clic en **firma digital**y, a continuación, haga clic en **Agregar**. Haga clic en **cifrado de clave**y, a continuación, en **Agregar**. Si la casilla de verificación **hacer que estos usos de clave sean críticos** no está seleccionada, active la casilla.

12. Haga clic en la flecha **uso mejorado de clave (directivas de aplicación)** para mostrar las **opciones disponibles**. En opciones disponibles, haga clic en **autenticación del servidor**y, a continuación, en **Agregar**. Haga clic en **autenticación de cliente**y, a continuación, en **Agregar**. Si está activada la casilla de verificación **hacer que los usos de la clave extendida sean críticos** , anule la selección de la casilla. Al contrario que la casilla uso de la clave (que debe comprobarse), debe asegurarse de que la casilla uso de clave extendida no está activada.

13. En la página de **propiedades del certificado** , haga clic en la ficha **clave privada** . Haga clic en la flecha **Opciones de clave** . En **tamaño de clave**, seleccione **2048** en la lista desplegable. Si va a generar este par de claves y CSR en un equipo distinto del proxy inverso para el que se ha diseñado este certificado, seleccione hacer que la **clave privada sea exportable**.
    
    <div>
    
    <table>
    <thead>
    <tr class="header">
    <th><img src="images/Gg398321.security(OCS.15).gif" title="seguridad" alt="security" />Nota de seguridad:</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td>Por lo general, es aconsejable seleccionar <strong>hacer que una clave privada exportable</strong> cuando hay más de un proxy inverso en una granja de servidores, ya que copiará el certificado y la clave privada en cada uno de los equipos de la granja de servidores. Si permite una clave privada exportable, debe tener especial cuidado con el certificado y el equipo en el que se genera. La clave privada, si se encuentra en peligro, representará el certificado inútil, así como la posibilidad de exponer el equipo o los equipos a acceso externo y otras vulnerabilidades de seguridad.</td>
    </tr>
    </tbody>
    </table>
    
    </div>

14. En la ficha **clave privada** , haga clic en la flecha **tipo de clave** . Seleccione la opción **Exchange** .

15. Haga clic en **Aceptar** para guardar las **propiedades del certificado** que ha establecido.

16. En la página **inscripción de certificado** , haga clic en **siguiente**.

17. En la página **¿dónde desea guardar la solicitud sin conexión?** , se le pedirá un nombre de **archivo** y un **formato de archivo** para guardar la solicitud de firma de certificado.

18. En el campo entrada de **nombre de archivo** , escriba una ruta de acceso y un nombre de archivo para la solicitud, o haga clic en **examinar** para seleccionar una ubicación para el archivo y escriba el nombre de archivo para la solicitud.

19. En **formato de archivo**, haga clic en **base 64** o **binario**. Seleccione **Base 64** a menos que el proveedor le indique lo contrario para los certificados.

20. Busque el archivo de solicitud que guardó en el paso anterior. Envíe a su entidad de certificación pública.
    
    <div>
    

    > [!IMPORTANT]
    > Microsoft ha identificado entidades de certificación públicas que cumplen con los requisitos de las comunicaciones unificadas. Se mantiene una lista en el siguiente artículo de Knowledge base. <A href="https://go.microsoft.com/fwlink/?linkid=282625">https://go.microsoft.com/fwlink/?LinkId=282625</A>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

