---
title: 'Lync Server 2013: Configurar las reglas de publicación web para un solo grupo de servidores interno'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure web publishing rules for a single internal pool
ms:assetid: 86ff4b2a-1ba9-46a2-a175-8b19e00a49dd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429712(v=OCS.15)
ms:contentKeyID: 48184725
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6ffe61072df14e28c20c45eb72302905986c6357
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842335"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-web-publishing-rules-for-a-single-internal-pool-in-lync-server-2013"></a>Configurar las reglas de publicación web para un solo grupo de servidores interno en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-07-07_

Microsoft Forefront Threat Management Gateway 2010 y enrutamiento de solicitudes de aplicaciones de Internet Information Server (IIS ARR) usa reglas de publicación web para publicar recursos internos, como una dirección URL de una reunión, a usuarios de Internet.

Además de las direcciones URL de los servicios web para los directorios virtuales, también debe crear reglas de publicación para direcciones URL simples, la dirección URL de LyncDiscover y el servidor de Office Web Apps. Para cada dirección URL simple, debe crear una regla individual en el proxy inverso que apunta a esa dirección URL simple.

Si implementa la movilidad y usa el descubrimiento automático, debe crear una regla de publicación para la dirección URL del servicio de detección automática externa. El descubrimiento automático también requiere reglas de publicación para la dirección URL de los servicios Web de Lync Server externo para el grupo de directores y el grupo de servidores front-end. Para obtener información detallada sobre la creación de reglas de publicación web para el descubrimiento automático, consulte [configurar el proxy inverso para movilidad en Lync Server 2013](lync-server-2013-configuring-the-reverse-proxy-for-mobility.md).

Use los procedimientos siguientes para crear reglas de publicación en Web.

<div>


> [!NOTE]  
> En estos procedimientos se supone que ha instalado la edición estándar de Forefront Threat Management Gateway (TMG) 2010 o que ha instalado y configurado Internet Information Server con la extensión de enrutamiento de solicitudes de aplicaciones (IIS ARR). Puede usar TMG o IIS ARR.



</div>

<div>

## <a name="to-create-a-web-server-publishing-rule-on-the-computer-running-tmg-2010"></a>Para crear una regla de publicación de servidor Web en el equipo que ejecuta TMG 2010

1.  Haga clic en **Inicio**, seleccione **programas**, **Microsoft Forefront TMG**y, a continuación, haga clic en **Administración de Forefront TMG**.

2.  En el panel izquierdo, expanda **ServerName**, haga clic con el botón secundario en **Directiva de Firewall**, seleccione **nuevo**y, después, haga clic en regla de **publicación de sitio web**.

3.  En la página **Asistente para nueva regla de publicación de web** , escriba un nombre para mostrar para la regla de publicación (por ejemplo, LyncServerWebDownloadsRule).

4.  En la página **Seleccionar acción de regla** , seleccione **permitir**.

5.  En la página **tipo de publicación** , seleccione **publicar un único sitio web o un equilibrador de carga**.

6.  En la página **seguridad de conexión de servidor** , seleccione **usar SSL para conectarse al servidor web o conjunto**de servidores publicado.

7.  En la página **detalles internos de publicación** , escriba el nombre de dominio completo (FQDN) de la granja de servidores web interna que hospeda el contenido de la reunión y el contenido de la libreta de direcciones en el cuadro **nombre del sitio interno** .
    
    <div>
    

    > [!NOTE]  
    > Si su servidor interno es un servidor Standard Edition, este FQDN es el FQDN del servidor Standard Edition. Si su servidor interno es un grupo front-end, este FQDN es una IP virtual (VIP) de equilibrador de carga de hardware que equilibra la carga de los servidores internos de la granja de servidores Web. El servidor de TMG debe poder resolver el FQDN en la dirección IP del servidor Web interno. Si el servidor de TMG no puede resolver el FQDN en la dirección IP correcta, puede seleccionar <STRONG>usar un nombre de equipo o una dirección IP para conectarse al servidor publicado</STRONG>y, a continuación, en el cuadro <STRONG>dirección IP</STRONG> <STRONG>o nombre del equipo</STRONG> , escriba la dirección IP del servidor EB. Si lo hace, debe asegurarse de que el puerto 53 está abierto en el servidor de TMG y de que puede comunicarse con un servidor DNS que reside en la red perimetral. También puede usar entradas en el archivo hosts local para proporcionar resolución de nombres.

    
    </div>

8.  En la página **Internal Publishing** details, en la **ruta de acceso (opcional)** , escriba ** / ** como la ruta de acceso de la carpeta que se va a publicar.
    
    <div>
    

    > [!NOTE]  
    > En el Asistente para la publicación de sitios web, solo puede especificar una ruta de acceso. Se pueden agregar rutas adicionales modificando las propiedades de la regla.

    
    </div>

9.  En la página **detalles de nombre público** , confirme que **este nombre de dominio** está seleccionado en **aceptar solicitudes de**, escriba el FQDN de los servicios web externos, en el cuadro **nombre público** .

10. En la página **seleccionar escucha de web** , haga clic en **nuevo** para abrir el Asistente para nueva definición de escucha de Web.

11. En la página **Asistente para nueva escucha de web** , escriba un nombre para la escucha de Web en el cuadro Nombre de la **escucha de web** (por ejemplo, LyncServerWebServers).

12. En la página **seguridad de conexión de cliente** , seleccione **requerir conexiones seguras SSL con clientes**.

13. En la página **dirección IP de escucha de web** , seleccione **externo**y, a continuación, haga clic en **seleccionar direcciones IP**.

14. En la página **selección de IP del agente de escucha externo** , seleccione **dirección IP especificada en el equipo Forefront TMG, en la red seleccionada**, seleccione la dirección IP adecuada y haga clic en **Agregar**.

15. En la página **certificados SSL de escucha** , seleccione **asignar un certificado para cada dirección IP**, seleccione la dirección IP asociada con el FQDN de la web externa y, a continuación, haga clic en **seleccionar certificado**.

16. En la página **seleccionar certificado** , seleccione el certificado que coincida con los nombres públicos especificados en el paso 9, haga clic en **seleccionar**.

17. En la página **configuración de autenticación** , seleccione **sin autenticación**.

18. En la página de **configuración de inicio de sesión único** , haga clic en **siguiente**.

19. En la página **finalización del Asistente para la escucha de web** , compruebe que la configuración de la escucha de **Web** es correcta y, a continuación, haga clic en **Finalizar**.

20. En la página **delegación de autenticación** , seleccione **sin delegación, pero el cliente puede autenticar directamente**.

21. En la página **conjunto de usuarios** , haga clic en **siguiente**.

22. En la página **finalización del Asistente para nueva regla de publicación de web** , compruebe que la configuración de la regla de publicación de web es correcta y, a continuación, haga clic en **Finalizar**.

23. Haga clic en **aplicar** en el panel de detalles para guardar los cambios y actualizar la configuración.

</div>

<div>

## <a name="to-create-a-web-server-publishing-rule-on-the-computer-running-iis-arr"></a>Para crear una regla de publicación de servidor Web en el equipo que ejecuta IIS ARR

1.  Enlace el certificado que usará para el proxy inverso al protocolo HTTPS. Haga clic en **Inicio**, seleccione **programas**, seleccione **herramientas administrativas**y, a continuación, haga clic en **Administrador de Internet Information Services (IIS)**.
    
    <div>
    

    > [!NOTE]  
    > Encontrará ayuda adicional, capturas de pantalla y orientación sobre la implementación y la configuración de IIS ARR en el artículo de NextHop <A href="http://go.microsoft.com/fwlink/?linkid=293391">que usa IIS ARR como proxy inverso para Lync Server 2013</A>.

    
    </div>

2.  Si aún no lo ha hecho, importe el certificado que usará para el proxy inverso. En el **Administrador de Internet Information Services (IIS)**, haga clic en el nombre del servidor de proxy inverso en el tamaño del lado izquierdo de la consola. En medio de la consola, en **IIS** , busque **certificados de servidor**. Haga clic con el botón secundario en **certificados de servidor** y seleccione **abrir característica**.

3.  En la parte derecha de la consola, haga clic en **Importar..**.. Escriba la ruta de acceso y el nombre de archivo del certificado con la extensión o haga clic en **...** para buscar el certificado. Seleccione el certificado y haga clic en **abrir**. Proporcione la contraseña usada para proteger la clave privada (si ha asignado una contraseña al exportar el certificado y la clave privada). Haga clic en **Aceptar**. Si la importación del certificado se realizó correctamente, el certificado aparecerá como una entrada en medio de la consola como una entrada en **certificados de servidor**.

4.  Asignar el certificado para que lo use HTTPS. En la parte izquierda de la consola, seleccione el **sitio web predeterminado** del servidor IIS. En la parte derecha, haga clic en **enlaces...**. En el cuadro de diálogo **enlaces del sitio** , haga clic en **Agregar...**. En el cuadro de diálogo **Agregar enlace de sitio** , en **tipo:**, seleccione **https**. Si selecciona https, podrá seleccionar el certificado que se usará para HTTPS. En **certificado SSL:**, seleccione el certificado importado para el proxy inverso. Haga clic en **Aceptar**. Después, haga clic en **cerrar**. El certificado se enlaza ahora al proxy inverso para la capa de sockets seguros (SSL) y la seguridad de la capa de transporte (TLS).
    
    <div>
    

    > [!IMPORTANT]  
    > Si recibe una advertencia al cerrar los cuadros de diálogo de enlaces que faltan certificados intermedios, debe buscar e importar el certificado de la entidad de certificación raíz de la entidad emisora y los certificados de la entidad de certificación intermedia. Consulte las instrucciones de la entidad emisora pública de la que ha solicitado el certificado y siga las instrucciones para solicitar e importar una cadena de certificados. Si ha exportado el certificado desde el servidor perimetral, puede exportar el certificado de la entidad emisora raíz y los certificados de CA intermedios asociados con el servidor perimetral. Importe el certificado de la entidad emisora raíz en el almacén de entidades emisoras de certificados raíz de confianza (no se debe confundir con el almacén de usuario) en el almacén de entidades de certificación intermedias del equipo.

    
    </div>

5.  En la parte izquierda de la consola, debajo del nombre del servidor IIS, haga clic con el botón secundario en granjas de **servidores** y haga clic en **crear granja de servidores...**.
    
    <div>
    

    > [!NOTE]  
    > Si no ve el nodo de las granjas de <STRONG>servidores</STRONG> , tendrá que instalar el enrutamiento de solicitudes de aplicación. Para obtener más información, consulte <A href="lync-server-2013-setting-up-reverse-proxy-servers.md">configuración de servidores proxy inversos para Lync Server 2013</A>.

    
    </div>
    
    En el cuadro de diálogo **crear granja de servidores** del nombre de una **granja**de servidores, escriba un nombre (puede ser un nombre descriptivo para fines de identificación) para la primera dirección URL. Haga clic en **Siguiente**.

6.  En el cuadro de diálogo **Agregar servidor** en **dirección de servidor**, escriba el nombre de dominio completo (FQDN) de los servicios web externos en el servidor front-end. Los nombres que se usarán aquí para fines de ejemplo son los mismos que se usan en la sección de planificación del proxy inverso, [Resumen de certificados: proxy inverso en Lync Server 2013](lync-server-2013-certificate-summary-reverse-proxy.md). En referencia al planeamiento de proxy inverso, escribemos `webext.contoso.com`el nombre completo. Confirme que la casilla de verificación situada junto a **conectado** está seleccionada. Haga clic en **Agregar** para agregar el servidor al grupo de servidores web para esta configuración.
    
    <div>
    

    > [!WARNING]  
    > Lync Server usa equilibradores de carga de hardware para el director de grupo y los servidores front-end para el tráfico HTTP y HTTPS. Solo deberá suministrar un FQDN al agregar un servidor a la granja de servidores de IIS ARR. El FQDN será el servidor front-end o Director en las configuraciones de servidores no agrupados, o el FQDN del equilibrador de carga de hardware configurado para los grupos de servidores. El único método admitido para equilibrar la carga de tráfico HTTP y HTTPS es mediante el uso de equilibradores de carga de hardware.

    
    </div>

7.  En el cuadro de diálogo **Agregar servidor** , haga clic en **Configuración avanzada...**. Se abrirá un cuadro de diálogo para definir el enrutamiento de solicitudes de aplicación de solicitudes al FQDN configurado. El propósito es redefinir qué puerto se usa cuando IIS ARR procesa la solicitud.
    
    De forma predeterminada, el puerto HTTP de destino debe definirse como 8080. Haga clic en junto al **httpPort actual 80** y establezca el valor en **8080**. Haga clic en junto al **httpsPort actual 443** y establezca el valor en **4443**. Deje el parámetro **Weight** en 100. Si es necesario, puede redefinir los pesos para una regla determinada una vez que tiene las estadísticas de línea base. Haga clic en **Finalizar** para completar esta parte de la configuración de la regla.

8.  Es posible que vea un cuadro de diálogo de reescritura de reglas que le informa de que el administrador de IIS puede crear una regla de reescritura de dirección URL para enrutar todas las solicitudes entrantes al conjunto de servidores automáticamente. Haga clic en **Sí**. Ajuste las reglas manualmente, pero si selecciona Sí, se establece la configuración inicial..

9.  Haga clic en el nombre del conjunto de servidores que acaba de crear. En la **granja de servidores** de la vista características del administrador de IIS, haga doble clic en **caché**. Anule la selección de **Habilitar caché de disco**. Haga clic en **aplicar** en el lado derecho.

10. Haga clic en el nombre del conjunto de servidores. En la **granja de servidores** de la vista características del administrador de IIS, haga doble clic en **proxy**. En la página Configuración de proxy, cambie el valor de **tiempo de espera (segundos)** a un valor adecuado para su implementación. Haga clic en **aplicar** para guardar el cambio.
    
    <div>
    

    > [!IMPORTANT]  
    > El valor de tiempo de espera del proxy es un número que variará de una implementación a la de implementación. Debe supervisar la implementación y modificar el valor de la mejor experiencia para los clientes. Es posible que pueda configurar el valor como mínimo como 200. Si admite clientes móviles de Lync en su entorno, debe establecer el valor en 960 para permitir el tiempo de espera de las notificaciones de inserción de Office 365 que tengan un valor de tiempo de espera de 900. Es muy probable que tenga que aumentar el valor de tiempo de espera para evitar desconexiones de cliente cuando el valor es demasiado bajo o disminuir el número si las conexiones a través del proxy no se desconectan y se devuelven mucho después de que el cliente se haya desconectado. La supervisión y la alineación básica de lo que es normal para su entorno es la única forma precisa de determinar dónde se encuentra la configuración adecuada para este valor.

    
    </div>

11. Haga clic en el nombre del conjunto de servidores. En **granja de servidores** en la vista características del administrador de IIS, haga doble clic en **reglas de enrutamiento**. En el cuadro de diálogo reglas de enrutamiento, en enrutamiento, desactive la casilla que se encuentra junto a habilitar descarga SSL. Si la opción para borrar la casilla no está disponible, seleccione la casilla de verificación **usar URL de reescritura para inspeccionar las solicitudes entrantes**. Haga clic en **aplicar** para guardar los cambios.
    
    <div>
    

    > [!WARNING]  
    > No se admite la descarga de SSL por parte del proxy inverso.

    
    </div>

12. Repita los pasos 5-11 para cada dirección URL que deba pasar a través del proxy inverso. Una lista común sería la siguiente:
    
      - Servicios web del servidor front-end externo: webext.contoso.com (ya configurado por el paso inicial)
    
      - Director de servicios Web externo para Director: webdirext.contoso.com (opcional si se implementa un director)
    
      - Dirección URL simple: meet.contoso.com
    
      - Marcado de dirección URL simple: dialin.contoso.com
    
      - Dirección URL de detección automática de Lync: lyncdiscover.contoso.com
    
      - URL de Office Web Apps Server: officewebapps01.contoso.com
        
        <div>
        

        > [!IMPORTANT]  
        > La dirección URL del servidor de Office Web Apps usará una dirección de httpsPort diferente. En el paso 7, define <STRONG>httpsPort</STRONG> como <STRONG>443</STRONG> y <STRONG>httpPort</STRONG> como puerto <STRONG>80</STRONG>. El resto de parámetros de configuración son iguales.

        
        </div>

13. En la parte izquierda de la consola, haga clic en el nombre del servidor IIS. En el medio de la consola, busque **URL Rewrite** en **IIS**. Haga doble clic en la dirección URL de reescritura para abrir la configuración de la URL de reescritura de reglas. Debería ver las reglas de cada granja de servidores que creó en los pasos anteriores. Si no lo hace, confirme que hizo clic en el nombre del **servidor IIS** inmediatamente debajo del nodo de la **Página de inicio** en la consola del administrador de Internet Information Server.

14. En el cuadro de diálogo de reescritura de **direcciones URL** , con webext.contoso.com como ejemplo, el nombre completo de la regla tal como se muestra es **ARR\_\_webext.contoso.com loadbalance\_SSL**.
    
      - Haga doble clic en la regla para abrir el cuadro de diálogo **Editar regla de entrada** .
    
      - Haga clic en **Agregar...** en el cuadro de diálogo **condiciones** .
    
      - En la **entrada de condición** **Agregar condición** : escriba **{http\_host}**. (Mientras escribe, aparece un cuadro de diálogo que le permitirá seleccionar la condición). en **comprobar si la cadena de entrada:** seleccione **coincide con el patrón**. En el **** tipo **\*** de entrada de patrón. Se debe seleccionar **ignorar mayúsculas y minúsculas** . Haga clic en **Aceptar**.
    
      - Desplácese hacia abajo en el cuadro de diálogo **Editar regla de entrada** para ubicar el cuadro de diálogo de **acción** . **Tipo de acción:** debe establecerse en enrutar **a granja de servidores**, **esquema:** establecer en **https://**, **granja de servidores:** establezca la dirección URL a la que se aplica esta regla. Para este ejemplo, debe establecerse en **webext.contoso.com**. **Path:** se establece en **/{R: 0}**
    
      - Haga clic en **aplicar** para guardar los cambios. Haga clic en **volver a reglas** para volver a las reglas de reescritura de URL.

15. Repita el procedimiento definido en el paso 14 para cada una de las reglas de reescritura de SSL que haya definido, una por dirección URL de granja de servidores.
    
    <div>
    

    > [!WARNING]  
    > De forma predeterminada, las reglas HTTP también se crean y se indican con nombres parecidos a las reglas de SSL. Para nuestro ejemplo actual, la regla HTTP se denomina <STRONG>ARR_webext. contoso. com _loadbalance</STRONG>. No se necesitan modificaciones en estas reglas y se pueden ignorar con seguridad.

    
    </div>

</div>

<div>

## <a name="to-modify-the-properties-of-the-web-publishing-rule-in-tmg-2010"></a>Para modificar las propiedades de la regla de publicación web en TMG 2010

1.  Haga clic en **Inicio**, seleccione **programas**, **Microsoft Forefront TMG**y, a continuación, haga clic en **Administración de Forefront TMG**.

2.  En el panel izquierdo, expanda **ServerName**y, a continuación, haga clic en **Directiva de Firewall**.

3.  En el panel de detalles, haga clic con el botón secundario en la regla de publicación del servidor Web que creó en el procedimiento anterior (por ejemplo, LyncServerExternalRule) y, a continuación, haga clic en **propiedades**.

4.  En la página **propiedades** , en la pestaña **de** , haga lo siguiente:
    
      - En la lista **esta regla se aplica a tráfico de estas fuentes** , haga clic en **cualquier lugar**y luego haga clic en **quitar**.
    
      - Haga clic en **Agregar**.
    
      - En **Agregar entidades de red**, expanda **redes**, haga clic en **externa**, haga clic en **Agregar**y, a continuación, haga clic en **cerrar**.

5.  En la pestaña **para** , asegúrese de que la casilla **reenviar el encabezado de host original en lugar de la real** está activada.

6.  En la pestaña **puente** , seleccione la casilla de verificación redirigir la **solicitud al puerto SSL** y, a continuación, especifique el puerto **4443**.

7.  En la pestaña **nombre público** , agregue las direcciones URL simples (por ejemplo, meet.contoso.com y Dialin.contoso.com).

8.  Haga clic en **aplicar** para guardar los cambios y, a continuación, haga clic en **Aceptar**.

9.  Haga clic en **aplicar** en el panel de detalles para guardar los cambios y actualizar la configuración.

</div>

<div>

## <a name="to-modify-the-properties-of-the-web-publishing-rule-in-iis-arr"></a>Para modificar las propiedades de la regla de publicación web en IIS ARR

1.  Haga clic en **Inicio**, seleccione **programas**, seleccione **herramientas administrativas**y, a continuación, haga clic en **Administrador de Internet Information Services (IIS)**.

2.  En la parte izquierda de la consola, haga clic en el nombre del servidor IIS.

3.  En el medio de la consola, busque **URL Rewrite** en **IIS**. Haga doble clic en la dirección URL de reescritura para abrir la configuración de la URL de reescritura de reglas.

4.  Haga doble clic en la regla que necesita modificar. Realice sus modificaciones, según sea necesario, en **coincidencia con la dirección URL**, **condiciones**, **variables de servidor** o **acción**.

5.  Haga clic en **aplicar** para confirmar los cambios. Haga clic en **volver a reglas** para modificar otras reglas o cierre la consola del **Administrador de IIS** si ha terminado de realizar los cambios.

</div>

</div>

<span> </span>

</div>

</div>

</div>

