---
title: 'Lync Server 2013: configurar las reglas de publicación web para un solo grupo interno'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure web publishing rules for a single internal pool
ms:assetid: 86ff4b2a-1ba9-46a2-a175-8b19e00a49dd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429712(v=OCS.15)
ms:contentKeyID: 48184725
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: adf6a1d777e16827f41d9a795fde54fca49750e1
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204637"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-web-publishing-rules-for-a-single-internal-pool-in-lync-server-2013"></a>Configurar las reglas de publicación web para un solo grupo de servidores interno en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-07-07_

Microsoft Forefront Threat Management Gateway 2010 y enrutamiento de solicitudes de aplicaciones de Internet Information Server (IIS ARR) usa reglas de publicación web para publicar recursos internos, como una dirección URL de reunión, a los usuarios de Internet.

Además de las direcciones URL de los servicios web para los directorios virtuales, también debe crear reglas de publicación para direcciones URL sencillas, la dirección URL de LyncDiscover y el servidor de Office Web Apps. Para cada URL sencilla, debe crear una regla individual en el proxy inverso que apunte a dicha URL sencilla.

Si va a implementar la movilidad y usar la detección automática, debe crear una regla de publicación para la URL del servicio Detección automática externa. La detección automática también requiere reglas de publicación para la dirección URL externa de servicios Web de Lync Server para el grupo de directores y el grupo de servidores front-end. Para obtener información detallada sobre cómo crear las reglas de publicación web para la detección automática, consulte [configuración del proxy inverso para movilidad en Lync Server 2013](lync-server-2013-configuring-the-reverse-proxy-for-mobility.md).

Realice los siguientes procedimientos para crear las reglas de publicación web.

<div>


> [!NOTE]  
> En estos procedimientos se presupone que ha instalado la edición Standard Edition de Forefront Threat Management Gateway (TMG) 2010 o que ha instalado y configurado Internet Information Server con la extensión de enrutamiento de solicitud de aplicación (IIS ARR). Puede usar TMG o IIS ARR.



</div>

<div>

## <a name="to-create-a-web-server-publishing-rule-on-the-computer-running-tmg-2010"></a>Para crear una regla de publicación de servidor web en el equipo que ejecuta TMG 2010

1.  Haga clic en **Inicio**, diríjase a **Programas**, haga clic en **Microsoft Forefront TMG** y, a continuación, haga clic en **Administración de Forefront TMG**.

2.  En el panel izquierdo, expanda **NombreDeServidor**, haga clic con el botón secundario en **Directiva de firewall**, elija **Nueva** y, a continuación, haga clic en **Regla de publicación de sitio web**.

3.  En la página **Asistente para nueva regla de publicación de web**, escriba un nombre para mostrar para la regla de publicación (por ejemplo, ReglaDescargasWebLyncServer).

4.  En la página **Seleccionar acción de regla**, seleccione **Permitir**.

5.  En la página **Tipo de publicación**, seleccione **Publicar un único sitio web o un equilibrador de carga**.

6.  En la página **Seguridad de conexión de servidor**, seleccione **Usar SSL para conectar al servidor web o la granja de servidores publicados**.

7.  En la página **Detalles internos de publicación**, escriba el nombre de dominio completo (FQDN) de la granja de servidores web internos que hospeda su contenido de reuniones y de la Libreta de direcciones en el cuadro **Nombre interno del sitio**.
    
    <div>
    

    > [!NOTE]  
    > Si el servidor interno es un servidor Standard Edition, este FQDN corresponde al servidor Standard Edition. Si el servidor interno es un grupo de servidores front-end, el FQDN es una IP virtual (VIP) de equilibrador de carga de hardware que equilibra la carga de los servidores de la granja de servidores web internos. El servidor TMG debe poder resolver el FQDN como la dirección IP del servidor web interno. Si el servidor de TMG no puede resolver el FQDN en la dirección IP correcta, puede seleccionar <STRONG>usar un nombre de equipo o una dirección IP para conectarse al servidor publicado</STRONG>y, a continuación, en el cuadro <STRONG>dirección IP</STRONG> <STRONG>o nombre de equipo</STRONG> , escriba la dirección IP del servidor Web interno. Si lo hace así, asegúrese de que el puerto 53 esté abierto en el servidor TMG y de que pueda alcanzar un servidor DNS que resida en la red perimetral. También puede usar entradas en el archivo de hosts local para facilitar la resolución de nombres.

    
    </div>

8.  En la página **detalles internos de publicación** , en el cuadro **ruta de acceso (opcional)** , escriba ** / ** como la ruta de acceso de la carpeta que se va a publicar.
    
    <div>
    

    > [!NOTE]  
    > En el asistente para publicar un sitio web solo se puede especificar una ruta de acceso. Las rutas adicionales se agregarán mediante la modificación de las propiedades de la regla.

    
    </div>

9.  En la página **Detalles de nombre público**, confirme que se haya seleccionado **Este nombre de dominio** en la opción **Aceptar peticiones para**, y escriba el FQDN de la granja de servicios web externos en el cuadro **Nombre público**.

10. En la página **Seleccionar escucha de web**, haga clic en **Nueva** para abrir el Asistente para nueva definición de escucha de web.

11. En la página **Este es el Asistente para nueva escucha de web**, escriba el nombre de la escucha de web en el cuadro **Nombre de la escucha de web** (por ejemplo, ServidoresWebLyncServer).

12. En la página **Seguridad de la conexión de cliente**, seleccione **Requerir conexiones seguras SSL con los clientes**.

13. En la página **Direcciones IP de escucha de web**, seleccione **Externa** y, a continuación, haga clic en **Seleccionar direcciones IP**.

14. En la página **Selección de IP de la escucha externa**, seleccione **Direcciones IP especificadas en el equipo de Forefront TMG en la red seleccionada**, seleccione la dirección IP correspondiente y haga clic en **Agregar**.

15. En la página **Certificados SSL de escucha**, seleccione **Asignar un certificado a cada dirección IP**, seleccione la dirección IP asociada al FQDN web externo y haga clic en **Seleccionar certificado**.

16. En la página **Seleccionar certificado**, seleccione el certificado que coincida con los nombres públicos especificados en el paso 9 y haga clic en **Seleccionar**.

17. En la página **Configuración de autenticación**, seleccione **Sin autenticación**.

18. En la página **Configuración de inicio de sesión único**, haga clic en **Siguiente**.

19. En la página **Finalización del Asistente para nueva escucha de web**, compruebe que la configuración de **Escucha de web** es correcta y haga clic en **Finalizar**.

20. En la página **Delegación de la autenticación**, seleccione **Sin delegación, pero el cliente se puede autenticar directamente**.

21. En la página **Conjunto de usuarios**, haga clic en **Siguiente**.

22. En la página **Finalización del Asistente para nueva regla de publicación de web**, compruebe que los parámetros de la regla de publicación de web sean correctos y, a continuación, haga clic en **Finalizar**.

23. Haga clic en **Aplicar** en el panel de detalles para guardar los cambios y actualizar la configuración.

</div>

<div>

## <a name="to-create-a-web-server-publishing-rule-on-the-computer-running-iis-arr"></a>Para crear una regla de publicación de servidor Web en el equipo que ejecuta IIS ARR

1.  Enlace el certificado que va a usar para el proxy inverso en el protocolo HTTPS. Haga clic en **Inicio**, seleccione **programas**, seleccione **herramientas administrativas**y, a continuación, haga clic en **Administrador de Internet Information Services (IIS)**.
    
    <div>
    

    > [!NOTE]  
    > Puede encontrar ayuda adicional, capturas de pantalla y orientación sobre la implementación y la configuración de IIS ARR en el artículo de NextHop <A href="https://go.microsoft.com/fwlink/?linkid=293391">mediante el uso de IIS ARR como proxy inverso para Lync Server 2013</A>.

    
    </div>

2.  Si aún no lo ha hecho, importe el certificado que va a usar para el proxy inverso. En el **Administrador de Internet Information Services (IIS)**, haga clic en el nombre del servidor de proxy inverso en el tamaño del lado izquierdo de la consola. En la mitad de la consola, en **IIS** , busque los **certificados de servidor**. Haga clic con el botón secundario en **certificados de servidor** y seleccione **abrir característica**.

3.  En la parte derecha de la consola, haga clic en **Importar..**.. Escriba la ruta de acceso y el nombre de archivo del certificado con la extensión o haga clic en **...** para buscar el certificado. Seleccione el certificado y haga clic en **abrir**. Proporcione la contraseña usada para proteger la clave privada (si ha asignado una contraseña al exportar el certificado y la clave privada). Haga clic en **Aceptar**. Si la importación del certificado se ha realizado correctamente, el certificado aparecerá como una entrada en la mitad de la consola como entrada en los **certificados de servidor**.

4.  Asignar el certificado para su uso con HTTPS. En la parte izquierda de la consola, seleccione el **sitio web predeterminado** del servidor IIS. En la parte derecha, haga clic en **enlaces...**. En el cuadro de diálogo **enlaces de sitios** , haga clic en **Agregar..**.. En el cuadro de diálogo **Agregar enlace de sitio** , en **tipo:**, seleccione **https**. La selección de https le permitirá seleccionar el certificado que se usará para HTTPS. En **certificado SSL:**, seleccione el certificado que importó para el proxy inverso. Haga clic en **Aceptar**. A continuación, haga clic en **cerrar**. El certificado se enlaza ahora al proxy inverso para la capa de sockets seguros (SSL) y la seguridad de la capa de transporte (TLS).
    
    <div>
    

    > [!IMPORTANT]  
    > Si recibe una advertencia al cerrar los cuadros de diálogo de enlaces que faltan los certificados intermedios, deberá buscar e importar el certificado de la entidad de certificación raíz de la entidad de certificación pública y los certificados de CA intermedios. Consulte las instrucciones de la entidad de certificación pública desde la que solicitó el certificado y siga las instrucciones para solicitar e importar una cadena de certificados. Si exportó el certificado desde el servidor perimetral, puede exportar el certificado de la entidad de certificación raíz y los certificados de CA intermedia asociados con el servidor perimetral. Importe el certificado de la CA raíz en el almacén de entidades de certificación raíz de confianza del equipo (no debe confundirse con el almacén de usuario) en el almacén de entidades de certificación intermedias del equipo.

    
    </div>

5.  En la parte izquierda de la consola, debajo del nombre del servidor IIS, haga clic con el botón secundario en **granjas de servidores** y haga clic en **crear granja de servidores...**
    
    <div>
    

    > [!NOTE]  
    > Si no ve el nodo <STRONG>granjas de servidores</STRONG> , debe instalar el enrutamiento de solicitud de aplicación. Para obtener más información, consulte <A href="lync-server-2013-setting-up-reverse-proxy-servers.md">configuración de servidores proxy inversos para Lync Server 2013</A>.

    
    </div>
    
    En el cuadro de diálogo **crear granja** de servidores del nombre de la **granja de servidores**, escriba un nombre (puede ser un nombre descriptivo con fines de identificación) para la primera dirección URL. Haga clic en **Siguiente**.

6.  En el cuadro de diálogo **Agregar servidor** en **dirección de servidor**, escriba el nombre de dominio completo (FQDN) de los servicios web externos en el servidor front-end. Los nombres que se usarán aquí para fines de ejemplo son los mismos que se usan en la sección de planeación para el proxy inverso, el proxy inverso de certificados inverso [en Lync Server 2013](lync-server-2013-certificate-summary-reverse-proxy.md). Al hacer referencia a la planificación del proxy inverso, `webext.contoso.com`escribimos el FQDN. Confirme que la casilla de verificación situada junto a **en línea** está seleccionada. Haga clic en **Agregar** para agregar el servidor al grupo de servidores web para esta configuración.
    
    <div>
    

    > [!WARNING]  
    > Lync Server usa equilibradores de carga de hardware para agrupar el director y los servidores front-end para el tráfico HTTP y HTTPS. Solo deberá proporcionar un FQDN cuando agregue un servidor a la granja de servidores de IIS ARR. El FQDN será el servidor front-end o el Director en las configuraciones de servidores no agrupados, o el FQDN del equilibrador de carga de hardware configurado para los grupos de servidores. El único método admitido para equilibrar la carga del tráfico HTTP y HTTPS es mediante equilibradores de carga de hardware.

    
    </div>

7.  En el cuadro de diálogo **Agregar servidor** , haga clic en **Configuración avanzada..**.. Se abrirá un cuadro de diálogo para definir el enrutamiento de solicitudes de aplicación para las solicitudes al FQDN configurado. El objetivo es redefinir el puerto que se usa cuando IIS ARR procesa la solicitud.
    
    De forma predeterminada, el puerto HTTP de destino debe definirse como 8080. Haga clic en junto al **httpPort 80** actual y establezca el valor en **8080**. Haga clic en junto al **httpsPort 443** actual y establezca el valor en **4443**. Deje el parámetro **Weight** en 100. Si es necesario, puede redefinir los pesos para una regla determinada una vez que tiene las estadísticas de línea base. Haga clic en **Finalizar** para completar esta parte de la configuración de la regla.

8.  Es posible que vea un cuadro de diálogo de reescritura de reglas que le informa de que el administrador de IIS puede crear una regla de reescritura de dirección URL para redirigir todas las solicitudes entrantes a la granja de servidores automáticamente. Haga clic en **Sí**. Las reglas se ajustarán manualmente, pero si se selecciona Sí, se establecerá la configuración inicial..

9.  Haga clic en el nombre de la granja de servidores que acaba de crear. En **granja de servidores** de la vista características del administrador de IIS, haga doble clic en **almacenamiento en caché**. Anule la selección de **Habilitar caché de disco**. Haga clic en **aplicar** en el lado derecho.

10. Haga clic en el nombre de la granja de servidores. En **granja de servidores** de la vista características del administrador de IIS, haga doble clic en **proxy**. En la página Configuración de proxy, cambie el valor de **tiempo de espera (segundos)** a un valor apropiado para su implementación. Haga clic en **aplicar** para guardar el cambio.
    
    <div>
    

    > [!IMPORTANT]  
    > El valor de tiempo de espera de proxy es un número que variará de una implementación a una implementación. Debe supervisar la implementación y modificar el valor de la mejor experiencia para los clientes. Es posible que pueda establecer el valor como mínimo como 200. Si va a admitir clientes móviles de Lync en su entorno, debe establecer el valor en 960 para permitir el tiempo de espera de notificaciones de inserción desde Office 365 que tenga un valor de tiempo de espera de 900. Es muy probable que necesite aumentar el valor de tiempo de espera para evitar desconexiones de clientes cuando el valor es demasiado bajo o disminuir el número si las conexiones a través del proxy no se desconectan y se devuelven mucho después de que el cliente se desconecte. La supervisión y la alineación de base, que es la normal para el entorno, es la única forma precisa de determinar si la configuración correcta es para este valor.

    
    </div>

11. Haga clic en el nombre de la granja de servidores. En **granja de servidores** de la vista características del administrador de IIS, haga doble clic en **reglas de enrutamiento**. En el cuadro de diálogo reglas de enrutamiento, en enrutamiento, desactive la casilla junto a habilitar la descarga de SSL. Si la posibilidad de desactivar la casilla de verificación no está disponible, marque la casilla de verificación **usar reescritura de URL para inspeccionar las solicitudes entrantes**. Haga clic en **aplicar** para guardar los cambios.
    
    <div>
    

    > [!WARNING]  
    > No se admite la descarga de SSL por parte del proxy inverso.

    
    </div>

12. Repita los pasos 5-11 para cada dirección URL que deba pasar a través del proxy inverso. Una lista común sería la siguiente:
    
      - Servicios web del servidor front-end externo: webext.contoso.com (ya configurado por el recorrido inicial)
    
      - Servicios Web de Director externo para Director: webdirext.contoso.com (opcional si se implementa un director)
    
      - Dirección URL sencilla cumplir: meet.contoso.com
    
      - Marcado de dirección URL simple: dialin.contoso.com
    
      - Dirección URL de detección automática de Lync: lyncdiscover.contoso.com
    
      - Dirección URL de Office Web Apps Server: officewebapps01.contoso.com
        
        <div>
        

        > [!IMPORTANT]  
        > La dirección URL del servidor de Office Web Apps usará una dirección de httpsPort diferente. En el paso 7, defina <STRONG>httpsPort</STRONG> como <STRONG>443</STRONG> y <STRONG>httpPort</STRONG> como puerto <STRONG>80</STRONG>. El resto de las opciones de configuración son iguales.

        
        </div>

13. En la parte izquierda de la consola, haga clic en el nombre del servidor IIS. En la mitad de la consola, busque **URL Rewrite** en **IIS**. Haga doble clic en reescribir URL para abrir la configuración de las reglas de reescritura de URL. Debe ver las reglas para cada granja de servidores que creó en los pasos anteriores. Si no lo hace, asegúrese de hacer clic en el nombre del **servidor IIS** inmediatamente debajo del nodo **Página de inicio** en la consola del administrador de Internet Information Server.

14. En el cuadro de diálogo de **reescritura de direcciones URL** , con webext.contoso.com como ejemplo, el nombre completo de la regla tal como se muestra es **\_ARR webext.contoso.com\_loadbalance\_SSL**.
    
      - Haga doble clic en la regla para abrir el cuadro de diálogo **Editar regla de entrada** .
    
      - Haga clic en **Agregar...** en el cuadro de diálogo **condiciones** .
    
      - En la **entrada de condición** de **Agregar condición** :, escriba **{http\_host}**. (A medida que escribe, aparece un cuadro de diálogo que le permitirá seleccionar la condición). en **comprobar si la cadena de entrada:** selecciona **coincide con el patrón**. En el **** tipo **\*** de entrada de patrón. Se debe seleccionar **omitir mayúsculas y minúsculas** . Haga clic en **Aceptar**.
    
      - Desplácese hacia abajo en el cuadro de diálogo **Editar regla de entrada** para buscar el cuadro de diálogo de **acción** . **Tipo de acción:** debe establecerse en **enrutar a granja de servidores**, **esquema:** set en **https://**, **granja de servidores:** establezca en la dirección URL a la que se aplica esta regla. Para este ejemplo, debe establecerse en **webext.contoso.com**. **Path:** se establece en **/{R: 0}**
    
      - Haga clic en **aplicar** para guardar los cambios. Haga clic en **volver a reglas** para volver a las reglas de reescritura de direcciones URL.

15. Repita el procedimiento definido en el paso 14 para cada una de las reglas de reescritura de SSL que haya definido, una por dirección URL de granja de servidores.
    
    <div>
    

    > [!WARNING]  
    > De forma predeterminada, las reglas HTTP también se crean y se indican mediante nombres similares a las reglas de SSL. En nuestro ejemplo actual, la regla HTTP se denominaría <STRONG>ARR_webext. contoso. com_loadbalance</STRONG>. No es necesario realizar modificaciones en estas reglas, por lo que se pueden ignorar sin problemas.

    
    </div>

</div>

<div>

## <a name="to-modify-the-properties-of-the-web-publishing-rule-in-tmg-2010"></a>Para modificar las propiedades de la regla de publicación web en TMG 2010

1.  Haga clic en **Inicio**, elija **programas**, seleccione **Microsoft Forefront TMG**y, a continuación, haga clic en administración de **Forefront TMG**.

2.  En el panel izquierdo, expanda **NombreDeServidor** y haga clic en **Directiva de firewall**.

3.  En el panel de detalles, haga clic con el botón secundario en la regla de publicación de servidor web que ha creado en el procedimiento anterior (por ejemplo, ReglaExternaLyncServer) y, a continuación, haga clic en **Propiedades**.

4.  En la página **Propiedades**, en la pestaña **Desde**, haga lo siguiente:
    
      - En la lista **Esta regla se aplica al tráfico de estos orígenes**, haga clic en **En cualquier lugar** y, a continuación, haga clic en **Quitar**.
    
      - Haga clic en **Agregar**.
    
      - En **Agregar entidades de red**, expanda **Redes**, haga clic en **Externa**, haga clic en **Agregar** y, a continuación, haga clic en **Cerrar**.

5.  En la pestaña **Para**, compruebe que está activada la casilla **Reenviar el encabezado de host original en lugar del real**.

6.  En la pestaña **Protocolo de puente**, active la casilla **Redirigir la solicitud al puerto SSL** y, a continuación, especifique el puerto **4443**.

7.  En la pestaña **Nombre público**, agregue las URL sencillas (por ejemplo, meet.contoso.com y dialin.contoso.com).

8.  Haga clic en **Aplicar** para guardar los cambios y, a continuación, haga clic en **Aceptar**.

9.  Haga clic en **Aplicar** en el panel de detalles para guardar los cambios y actualizar la configuración.

</div>

<div>

## <a name="to-modify-the-properties-of-the-web-publishing-rule-in-iis-arr"></a>Para modificar las propiedades de la regla de publicación web en IIS ARR

1.  Haga clic en **Inicio**, seleccione **programas**, seleccione **herramientas administrativas**y, a continuación, haga clic en **Administrador de Internet Information Services (IIS)**.

2.  En la parte izquierda de la consola, haga clic en el nombre del servidor IIS.

3.  En la mitad de la consola, busque **URL Rewrite** en **IIS**. Haga doble clic en reescribir URL para abrir la configuración de las reglas de reescritura de URL.

4.  Haga doble clic en la regla que debe modificar. Realice las modificaciones que sean necesarias en la **dirección URL**, **las condiciones**, **las variables de servidor** o la **acción**de coincidencia.

5.  Haga clic en **aplicar** para confirmar los cambios. Haga clic en **volver a reglas** para modificar otras reglas o cierre la consola del **Administrador de IIS** si ha terminado con los cambios.

</div>

</div>

<span> </span>

</div>

</div>

</div>

