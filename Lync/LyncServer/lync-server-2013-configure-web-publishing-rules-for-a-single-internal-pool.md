---
title: "Configurar las reglas de publicación web para un solo grupo de servidores interno"
TOCTitle: Configurar las reglas de publicación web para un solo grupo de servidores interno
ms:assetid: 86ff4b2a-1ba9-46a2-a175-8b19e00a49dd
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg429712(v=OCS.15)
ms:contentKeyID: 48275913
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configurar las reglas de publicación web para un solo grupo de servidores interno en Lync Server 2013

 

_**Última modificación del tema:** 2016-12-08_

Microsoft Forefront Threat Management Gateway 2010 y el enrutamiento de solicitud de aplicaciones de Internet Information Server (IIS ARR) emplean reglas de publicación web para publicar recursos internos como, por ejemplo, la URL de una reunión, para los usuarios de Internet.

Además de las URL de servicios web de los directorios virtuales, debe crear también reglas de publicación para direcciones URL sencillas, la dirección URL de LyncDiscover y el Servidor Office Web Apps. Para cada URL sencilla, debe crear una regla individual en el proxy inverso que apunte a dicha URL sencilla.

Si va a implementar la movilidad y usar la detección automática, debe crear una regla de publicación para la URL del servicio Detección automática externa. La detección automática también requiere reglas de publicación para la URL externa de servicios web de Lync Server para su Grupo de directores y Grupo de servidores front-end. Para más información sobre cómo crear reglas de publicación para la detección automática, vea [Configuración del proxy inverso para movilidad en Lync Server 2013](lync-server-2013-configuring-the-reverse-proxy-for-mobility.md).

Realice los siguientes procedimientos para crear las reglas de publicación web.


> [!NOTE]
> Para estos procedimientos, se presupone que ha instalado Forefront Threat Management Gateway (TMG) 2010 Standard Edition o que ha instalado y configurado la extensión de Internet Information Server con enrutamiento de solicitud de aplicaciones (IIS ARR). Puede usar TMG o IIS ARR.



## Para crear una regla de publicación de servidor web en el equipo que ejecuta TMG 2010

1.  Haga clic en **Inicio** , diríjase a **Programas** , haga clic en **Microsoft Forefront TMG** y, a continuación, haga clic en **Administración de Forefront TMG** .

2.  En el panel izquierdo, expanda **NombreDeServidor** , haga clic con el botón secundario en **Directiva de firewall** , elija **Nueva** y, a continuación, haga clic en **Regla de publicación de sitio web** .

3.  En la página **Asistente para nueva regla de publicación de web** , escriba un nombre para mostrar para la regla de publicación (por ejemplo, ReglaDescargasWebLyncServer).

4.  En la página **Seleccionar acción de regla** , seleccione **Permitir** .

5.  En la página **Tipo de publicación** , seleccione **Publicar un único sitio web o un equilibrador de carga** .

6.  En la página **Seguridad de conexión de servidor** , seleccione **Usar SSL para conectar al servidor web o la granja de servidores publicados** .

7.  En la página **Detalles internos de publicación** , escriba el nombre de dominio completo (FQDN) de la granja de servidores web internos que hospeda su contenido de reuniones y de la Libreta de direcciones en el cuadro **Nombre interno del sitio** .
    

    > [!NOTE]
    > Si el servidor interno es un servidor Standard Edition, este FQDN corresponde al servidor Standard Edition. Si el servidor interno es un grupo de servidores front-end, el FQDN es una IP virtual (VIP) de equilibrador de carga de hardware que equilibra la carga de los servidores de la granja de servidores web internos. El servidor TMG debe poder resolver el FQDN como la dirección IP del servidor web interno. Si el servidor TMG no es capaz de resolver el FQDN como la dirección IP correspondiente, puede seleccionar <STRONG>Usar un nombre de equipo o dirección IP para conectar al servidor publicado</STRONG> y, a continuación, escribir la dirección IP del servidor web interno en el cuadro <STRONG>Nombre de equipo o</STRONG> <STRONG>Dirección IP</STRONG> . Si lo hace así, asegúrese de que el puerto 53 esté abierto en el servidor TMG y de que pueda alcanzar un servidor DNS que resida en la red perimetral. También puede usar entradas en el archivo de hosts local para facilitar la resolución de nombres.



8.  En la página **Detalles internos de publicación** , en el cuadro **Ruta de acceso (opcional)** , escriba **/\*** como la ruta de la carpeta que se va a publicar.
    

    > [!NOTE]
    > En el asistente para publicar un sitio web solo se puede especificar una ruta de acceso. Las rutas adicionales se agregarán mediante la modificación de las propiedades de la regla.



9.  En la página **Detalles de nombre público** , confirme que se haya seleccionado **Este nombre de dominio** en la opción **Aceptar peticiones para** , y escriba el FQDN de la granja de servicios web externos en el cuadro **Nombre público** .

10. En la página **Seleccionar escucha de web** , haga clic en **Nueva** para abrir el Asistente para nueva definición de escucha de web.

11. En la página **Este es el Asistente para nueva escucha de web** , escriba el nombre de la escucha de web en el cuadro **Nombre de la escucha de web** (por ejemplo, ServidoresWebLyncServer).

12. En la página **Seguridad de la conexión de cliente** , seleccione **Requerir conexiones seguras SSL con los clientes** .

13. En la página **Direcciones IP de escucha de web** , seleccione **Externa** y, a continuación, haga clic en **Seleccionar direcciones IP** .

14. En la página **Selección de IP de la escucha externa** , seleccione **Direcciones IP especificadas en el equipo de Forefront TMG en la red seleccionada** , seleccione la dirección IP correspondiente y haga clic en **Agregar** .

15. En la página **Certificados SSL de escucha** , seleccione **Asignar un certificado a cada dirección IP** , seleccione la dirección IP asociada al FQDN web externo y haga clic en **Seleccionar certificado** .

16. En la página **Seleccionar certificado** , seleccione el certificado que coincida con los nombres públicos especificados en el paso 9 y haga clic en **Seleccionar** .

17. En la página **Configuración de autenticación** , seleccione **Sin autenticación** .

18. En la página **Configuración de inicio de sesión único** , haga clic en **Siguiente** .

19. En la página **Finalización del Asistente para nueva escucha de web** , compruebe que la configuración de **Escucha de web** es correcta y haga clic en **Finalizar** .

20. En la página **Delegación de la autenticación** , seleccione **Sin delegación, pero el cliente se puede autenticar directamente** .

21. En la página **Conjunto de usuarios** , haga clic en **Siguiente** .

22. En la página **Finalización del Asistente para nueva regla de publicación de web** , compruebe que los parámetros de la regla de publicación de web sean correctos y, a continuación, haga clic en **Finalizar** .

23. Haga clic en **Aplicar** en el panel de detalles para guardar los cambios y actualizar la configuración.

## Para crear una regla de publicación de servidor web en el equipo que ejecuta IIS ARR

1.  Enlace el certificado que usará para el proxy inverso al protocolo HTTPS. Haga clic en **Inicio** , elija **Programas** , elija **Herramientas administrativas** y, a continuación, haga clic en **Administrador de Internet Information Services (IIS)** .
    

    > [!NOTE]
    > Puede encontrar más ayuda, capturas de pantalla y orientación sobre la implementación y configuración de IIS ARR en el artículo de NextHop sobre el <A href="http://go.microsoft.com/fwlink/?linkid=293391">uso de IIS ARR como proxy inverso para Lync Server 2013</A>.



2.  Si aún no lo ha hecho, importe el certificado que usará para el proxy inverso. En el **Administrador de Internet Information Services (IIS)** , haga clic en el nombre del servidor de proxy inverso del lado izquierdo de la consola. En medio de la consola debajo de **IIS** localice **Certificados de servidor** . Haga clic con el botón secundario en **Certificados de servidor** y seleccione **Abrir característica** .

3.  En el lado derecho de la consola, haga clic en **Importar** . Escriba la ruta de acceso y el nombre de archivo del certificado con la extensión, o bien haga clic en **…** para buscar el certificado. Seleccione el certificado y haga clic en **Abrir** . Proporcione la contraseña utilizada para proteger la clave privada (si asignó una contraseña al exportar el certificado y la clave privada). Haga clic en **Aceptar** . Si la importación del certificado se realizó correctamente, el certificado aparecerá como una entrada en medio de la consola como una entrada en **Certificados de servidor** .

4.  Asigne el certificado que usará HTTPS. En el lado izquierdo de la consola, seleccione el **Sitio web predeterminado** del servidor IIS. En el lado derecho, haga clic en **Enlaces** . En el diálogo **Enlaces de sitios** , haga clic en **Agregar** . En el diálogo **Agregar enlace de sitio** debajo de **Tipo** , seleccione **https** . Si selecciona https, podrá seleccionar el certificado para usar en https. En **Certificado SSL** , seleccione el certificado que importó para el proxy inverso. Haga clic en **Aceptar** . A continuación, haga clic en **Cerrar** . El certificado ahora está enlazado al proxy inverso para la Capa de sockets seguros (SSL) y la Seguridad de la capa de transporte (TLS).
    
    > [!IMPORTANT]  
    > Si recibe una advertencia al cerrar los diálogos de enlaces intermedios para los certificados faltantes, necesita encontrar e importar el certificado de autoridad de raíz de la entidad de certificación (CA) pública y todos los certificados intermedios de la CA. Consulte las instrucciones en la CA pública desde la que solicitó el certificado y siga las instrucciones para solicitar e importar una cadena de certificado. Si exportó el certificado desde Servidor perimetral, puede exportar el certificado de CA raíz y todos los certificados intermedios de CA asociados con Servidor perimetral. Importe el certificado de CA raíz al almacén de entidades de certificación raíz de confianza del equipo (no debe confundirse con el almacén del usuario) y los certificados intermedios al almacén de entidades de certificación intermedia del equipo.
    


5.  En el lado izquierdo de la consola debajo del nombre de servidor de IIS, haga clic con el botón secundario en **Granjas de servidores** y, a continuación, haga clic en **Crear granja de servidores** .
    

    > [!NOTE]
    > Si no ve el nodo <STRONG>Granjas de servidores</STRONG> , deberá instalar el enrutamiento de solicitud de aplicaciones. Para obtener más información, consulte <A href="lync-server-2013-setting-up-reverse-proxy-servers.md">Configuración de los servidores proxy inversos para Lync Server 2013</A>.

    
    En el diálogo **Crear granja de servidores** en **Nombre de granja de servidores** , escriba un nombre (puede ser un nombre descriptivo para fines de identificación) para la primera dirección URL. Haga clic en **Siguiente** .

6.  En el diálogo **Agregar servidor** en **Dirección del servidor** , escriba el nombre de dominio completo (FQDN) de los servicios web externos en Servidor front-end. Los nombres que se usarán aquí para fines ilustrativos son los mismos que se usan en la sección Planeación para el proxy inverso, [Resumen de certificado - Proxy inverso en Lync Server 2013](lync-server-2013-certificate-summary-reverse-proxy.md). Al referirnos a la planeación del proxy inverso, escribimos el FQDN `webext.contoso.com`. Confirme que la casilla junto a **En línea** está activada. Haga clic en **Agregar** para agregar el servidor al grupo de servidores web para esta configuración.
    
    > [!WARNING]  
    > Lync Server usa equilibradores de carga de hardware para agrupar Director y Servidores front-end para el tráfico HTTP y HTTPS. Solo proporcionará un FQDN al agregar un servidor a la granja de servidores de IIS ARR. El FQDN será el Servidor front-end o Director en configuraciones de servidor no agrupadas, o bien el FQDN del equilibrador de carga del hardware configurado para grupos de servidores. El único método admitido para equilibrar la carga del tráfico HTTP y HTTPS es mediante equilibradores de carga de hardware.
    


7.  En el diálogo **Agregar servidor** , haga clic en **Configuración avanzada** . Se abrirá un diálogo para definir el enrutamiento de solicitud de aplicaciones para las solicitudes al FQDN configurado. El propósito es redefinir el puerto que se usa cuando se procesa la solicitud mediante IIS ARR.
    
    De manera predeterminada, el puerto HTTP de destino se debe definir como 8080. A continuación, haga clic en el **httpPort 80** actual y establezca el valor en **8080** . A continuación, haga clic en el **httpsPort 443** actual y establezca el valor en **4443** . Deje el parámetro **weight** en 100. Si es necesario, puede redefinir el peso para una regla determinada una vez que tenga estadísticas de línea base. Haga clic en **Finalizar** para completar esta parte de la configuración de la regla.

8.  Es posible que vea un diálogo de reglas de reescritura que le informe que el Administrador de IIS puede crear una regla de reescritura de dirección URL para enrutar todas las solicitudes entrantes a la granja de servidores automáticamente. Haga clic en **Sí** . Puede ajustar las reglas de forma manual, pero si selecciona Sí, se establecerá la configuración inicial.

9.  Haga clic en el nombre de la granja de servidores que acaba de crear. En **Granja de servidores** en Vista Características del Administrador de IIS, haga doble clic en **Almacenando en caché** . Desactive **Habilitar caché de disco** . Haga clic en **Aplicar** en el lado derecho.

10. Haga clic en el nombre de la granja de servidores. En **Granja de servidores** en Vista Características del Administrador de IIS, haga doble clic en **Proxy**. En la página de configuración de proxy, cambie el valor de **Tiempo de espera (segundos)** a un valor adecuado para su implementación. Haga clic en **Aplicar** para guardar el cambio.
    
    > [!IMPORTANT]  
    > El valor de tiempo de espera de proxy es un número que puede variar de una implementación a otra. Debe supervisar su implementación y modificar el valor para lograr la mejor experiencia para los clientes. Puede establecer el valor tan bajo como 200. Si admite a los clientes móviles de Lync en su entorno, debe establecer el valor en 960 para permitir el tiempo de espera de las notificaciones de inserción de Office 365 que tienen un valor de tiempo de espera de 900. Es muy probable que necesite aumentar el valor de tiempo de espera para evitar que el cliente se desconecte cuando el valor sea demasiado bajo o disminuirlo si las conexiones a través del proxy no se desconectan y se borran mucho tiempo después de que el cliente se ha desconectado. La supervisión y la línea base de lo que es normal para el entorno es el único método preciso para determinar dónde está el parámetro correcto para este valor.
    


11. Haga clic en el nombre de la granja de servidores. En **Granja de servidores** en Vista Características del Administrador de IIS, haga doble clic en **Reglas de enrutamiento** . En el diálogo Reglas de enrutamiento debajo de Enrutamiento, desactive la casilla junto a Habilitar descarga de SSL. Si la opción para desactivar la casilla no está disponible, active la casilla para **Usar URL Rewrite para inspeccionar solicitudes entrantes** . Haga clic en **Aplicar** para guardar los cambios.
    
    > [!CAUTION]  
    > No se admite la descarga de SSL mediante el proxy inverso.
    


12. Repita los pasos 5 a 11 para cada URL que deba pasar a través del proxy inverso. Una lista común sería la siguiente:
    
      - Servicios web externos de Servidor front-end: webext.contoso.com (ya están configurados por el tutorial inicial)
    
      - Servicios web externos de Director para Director: webdirext.contoso.com (opcional si se implementa un Director)
    
      - URL sencilla de reunión: meet.contoso.com
    
      - URL sencilla de acceso telefónico: dialin.contoso.com
    
      - URL de detección automática de Lync: lyncdiscover.contoso.com
    
      - URL del servidor de Office Web Apps: officewebapps01.contoso.com
        
        > [!IMPORTANT]  
        > La dirección URL de Servidor Office Web Apps usará otra dirección httpsPort. En el paso 7, debe definir <strong>httpsPort</strong> como <strong>443</strong> y <strong>httpPort</strong> como el puerto <strong>80</strong> . Las demás opciones de configuración son las mismas.
        


13. En el lado izquierdo de la consola, haga clic en el nombre de servidor de IIS. En medio de la consola, localice **URL Rewrite** debajo de **IIS** . Haga doble clic en URL Rewrite para abrir la configuración de las reglas de URL Rewrite. Debe ver reglas para cada granja de servidores que haya creado en los pasos anteriores. Si no es así, confirme que haya hecho clic en el nombre del **Servidor IIS** inmediatamente abajo del nodo de la **Página de inicio** en la consola del Administrador de Internet Information Server.

14. En el diálogo **URL Rewrite** , que usa webext.contoso.com como ejemplo, el nombre completo de la regla tal como se muestra es **ARR\_webext.contoso.com\_loadbalance\_SSL** .
    
      - Haga doble clic en la regla para abrir el diálogo **Editar regla entrante** .
    
      - Haga clic en **Agregar** en el diálogo **Condiciones** .
    
      - En **Agregar condición** en **Entrada de condición** escriba **{HTTP\_HOST}** . (Mientras escribe, aparecerá un diálogo que le permitirá seleccionar la condición). En **Comprobar su la cadena de entrada** seleccione **Coincide con el patrón** . En **Entrada de patrón** escriba **\*** . La casilla **Omitir mayúsculas y minúsculas** debe estar activada. Haga clic en **Aceptar** .
    
      - Desplácese hacia abajo en el diálogo **Editar regla entrante** para localizar el diálogo **Acción** . **Tipo de acción** debe establecerse en **Enrutar a la granja de servidores** , **Esquema** se establece en **https://** , **Granja de servidores** se establece en la dirección URL a la que se aplica esta regla. Para este ejemplo, debe establecerse en **webext.contoso.com** . **Ruta de acceso** se establece en **/{R:0}**
    
      - Haga clic en **Aplicar** para guardar los cambios. Haga clic en **Volver a Reglas** para volver a las reglas de URL Rewrite.

15. Repita el procedimiento definido en el paso 14 para cada regla de reescritura de SSL que haya definido, una por URL de granja de servidores.
    
    > [!WARNING]  
    > De manera predeterminada, las reglas HTTP se crean también y se indican por medio de nombres similares a las reglas SSL. Para el ejemplo actual, la regla HTTP se denominaría <strong>ARR_webext.contoso.com_loadbalance</strong> . No se necesitan modificaciones para estas reglas y se pueden omitir de forma segura.
    


## Para modificar las propiedades de la regla de publicación de web en TMG 2010

1.  Haga clic en **Inicio** , diríjase a **Programas** , haga clic en **Microsoft Forefront TMG** y, a continuación, haga clic en **Administración de Forefront TMG** .

2.  En el panel izquierdo, expanda **NombreDeServidor** y haga clic en **Directiva de firewall** .

3.  En el panel de detalles, haga clic con el botón secundario en la regla de publicación de servidor web que ha creado en el procedimiento anterior (por ejemplo, ReglaExternaLyncServer) y, a continuación, haga clic en **Propiedades** .

4.  En la página **Propiedades** , en la pestaña **Desde** , haga lo siguiente:
    
      - En la lista **Esta regla se aplica al tráfico de estos orígenes** , haga clic en **En cualquier lugar** y, a continuación, haga clic en **Quitar** .
    
      - Haga clic en **Agregar** .
    
      - En **Agregar entidades de red** , expanda **Redes** , haga clic en **Externa** , haga clic en **Agregar** y, a continuación, haga clic en **Cerrar** .

5.  En la pestaña **Para** , compruebe que está activada la casilla **Reenviar el encabezado de host original en lugar del real** .

6.  En la pestaña **Protocolo de puente** , active la casilla **Redirigir la solicitud al puerto SSL** y, a continuación, especifique el puerto **4443** .

7.  En la pestaña **Nombre público** , agregue las URL sencillas (por ejemplo, meet.contoso.com y dialin.contoso.com).

8.  Haga clic en **Aplicar** para guardar los cambios y, a continuación, haga clic en **Aceptar** .

9.  Haga clic en **Aplicar** en el panel de detalles para guardar los cambios y actualizar la configuración.

## Para modificar las propiedades de la regla de publicación de web en IIS ARR

1.  Haga clic en **Inicio** , elija **Programas** , elija **Herramientas administrativas** y, a continuación, haga clic en **Administrador de Internet Information Services (IIS)** .

2.  En el lado izquierdo de la consola, haga clic en el nombre de servidor de IIS.

3.  En medio de la consola, localice **URL Rewrite** debajo de **IIS** . Haga doble clic en URL Rewrite para abrir la configuración de las reglas de URL Rewrite.

4.  Haga doble clic en la regla que necesite modificar. Haga sus modificaciones, según sea necesario, en **Coincidir URL** , **Condiciones** , **Variables del servidor** o **Acción** .

5.  Haga clic en **Aplicar** para confirmar los cambios. Haga clic en **Volver a Reglas** para modificar otras reglas, o bien cierre la consola del **Administrador de IIS** si ha terminado de realizar cambios.

