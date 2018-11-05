---
title: "Lync Server 2013: Publicación de Office Web Apps Server con un servidor proxy inverso"
TOCTitle: Publicación de Office Web Apps Server con un servidor proxy inverso
ms:assetid: 0babe39f-c4b9-46f0-995a-33dc99c2be03
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ204665(v=OCS.15)
ms:contentKeyID: 48274401
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Publicación de Office Web Apps Server con un servidor proxy inverso en Lync Server 2013

 

_**Última modificación del tema:** 2013-02-25_

Si desea que los usuarios externos (es decir, los usuarios que inician sesión desde fuera del firewall de la organización) tengan acceso a las presentaciones de PowerPoint de Office Web Apps Server, entonces deberá utilizar Office Web Apps Server y un servidor proxy inverso, como Microsoft Forefront Threat Management Gateway. Eso también quiere decir que necesitará crear y configurar una regla de publicación de sitio web, la cual garantizará que los usuarios puedan conectarse al servidor. Si no necesita proporcionar acceso a usuarios externos, entonces no necesita configurar esta regla.

Para configurar una regla de publicación de sitios web en Forefront Threat Management Gateway, complete el siguiente procedimiento:

1.  Haga clic en **Inicio**, en **Todos los programas**, en **Microsoft Forefront TMG** y, a continuación, en **Administración de Forefront TMG**.

2.  En Forefront TMG, haga clic con el botón secundario en **Directiva de firewall**, elija **Nueva** y, a continuación, haga clic en **Regla de publicación de sitio web**.

3.  En el Asistente de nueva regla de publicación web, en la página **Bienvenido al Asistente de nueva regla de publicación web**, escriba un nombre para su nueva regla en el cuadro **nombre de regla de publicación web** (por ejemplo, **Regla del servidor Office Web Apps**) y luego haga clic en **Siguiente**.

4.  En la página **Especificar acción de regla**, seleccione **Permitir** y luego haga clic en **Siguiente**.

5.  En la página **Tipo de publicación**, seleccione **Publicar un único sitio web o un equilibrador de carga** y, a continuación, haga clic en **Siguiente**.

6.  En la página **Seguridad de conexión de servidor**, seleccione **Usar SSL para conectarse al servidor web o conjunto de servidores publicado** y, a continuación, haga clic en **Siguiente**.

7.  En la página **Detalles internos de publicación**, escriba el FQDN de su servidor Office Web Apps (por ejemplo, **officewebapps01.contoso.com**) en el cuadro **Nombre de sitio interno** y luego haga clic en **Siguiente**. El nombre ingresado en el cuadro **Nombre de sitio interno** debe aparecer en el campo Asunto o el campo Nombre alternativo de asunto del certificado que ha asignado al servidor Office Web Apps.

8.  En la página **Detalles internos de publicación**, escriba **/\*** en el cuadro **Ruta (opcional)** y luego haga clic en **Siguiente**. La sintaxis /\* garantizará que se publiquen todas las carpetas y subcarpetas del sitio.

9.  En la página **Detalles de nombre público**, seleccione **Este nombre de dominio (escríbalo a continuación)** de la lista desplegable **Aceptar peticiones para** y luego escriba el nombre de dominio completo de su servidor Office Web Apps en el cuadro Nombre público. Este nombre deberá ser el nombre utilizado para acceder a su sitio web. Por ejemplo, si se accede a su sitio web utilizando la dirección URL http://officewebapps01.contoso.com, entonces deberá introducir **officewebapps01.contoso.com** en el cuadro **Nombre público**.

10. Después, haga clic en **Siguiente**.

11. En la página **Seleccionar escucha de web**, haga clic en **Nuevo**.

12. En el Asistente para nueva definición de escucha de web, escriba un nombre para la nueva escucha de web (por ejemplo, **SSL**) en el cuadro **Nombre de escucha de web** y luego haga clic en **Siguiente**.

13. En la página **Seguridad de la conexión de cliente**, seleccione **Requerir conexiones seguras SSL con los clientes** y, a continuación, haga clic en **Siguiente**.

14. En la página **Direcciones IP de escucha de web**, seleccione **Externa**, seleccione **Interna** y, a continuación, haga clic en **Siguiente**.

15. En la página **Certificados SSL de escucha**, seleccione **Usar un único certificado para esta escucha de web** y, a continuación, haga clic en **Seleccionar certificado**.

16. En el cuadro de diálogo **Seleccionar certificado**, seleccione el certificado que utilizará para esta escucha de web y, a continuación, haga clic en **Seleccionar**.

17. En la página **Certificados SSL de escucha**, haga clic en **Siguiente**.

18. En la página **Configuración de autenticación**, seleccione **Sin autenticación** de la lista desplegable **Seleccionar cómo los clientes proporcionarán credenciales a Forefront TMG** y, a continuación, haga clic en **Siguiente**.

19. En la página **Configuración de inicio de sesión único**, haga clic en **Siguiente**.

20. En la página **Finalización del Asistente de nueva escucha de web**, revise el resumen de las elecciones de configuración que ha realizado. Cuando esté listo, haga clic en **Finalizar**.

21. En la página **Seleccionar escucha de web**, haga clic en **Siguiente**.

22. En la página **Delegación de la autenticación**, seleccione **Sin delegación, pero el cliente puede autenticar directamente** de la lista desplegable **Seleccionar el método usado por Forefront TMG para autenticarse en el servidor web publicado** y, a continuación, haga clic en **Siguiente**.

23. En la página **Conjuntos de usuarios**, confirme que aparezcan listados los conjuntos de usuarios apropiados. De manera predeterminada, esto es el conjunto de usuarios **Todos los usuarios**. Haga clic en **Agregar** para agregar otros conjuntos de usuarios que haya definido. Cuando haya terminado, haga clic en **Siguiente**.

24. En la página **Finalización del Asistente de nueva regla de publicación web**, haga clic en **Finalizar**.

Tenga en cuenta que hacer clic en **Finalizar** no implica que haya completado el proceso; es decir, esto no aplica automáticamente ni habilita la nueva regla. En cambio, necesitará hacer clic en el botón **Aplicar** que aparecerá en la interfaz de usuario de Forefront TMG. Al hacer clic en **Aplicar** aparecerá el cuadro de diálogo **Descripción de cambio de configuración**. Haga clic en **Aplicar** en ese cuadro de diálogo para habilitar la nueva regla de publicación.

Una vez que se ha aplicado su nueva regla, necesitará realizarle algunas modificaciones pequeñas para garantizar que los usuarios puedan utilizar las nuevas funcionalidades de presentación de PowerPoint. Para lograr eso, realice el siguiente procedimiento:

1.  En Forefront TMG, haga clic con el botón secundario en el nombre de la nueva regla de publicación y, a continuación, haga clic en **Propiedades**.

2.  En el cuadro de diálogo **Propiedades**, en la pestaña **Para**, seleccione la opción **Reenviar el encabezado de host original en lugar del real**.

3.  En la pestaña **Tráfico**, haga clic en **Filtrar** y, a continuación, haga clic en **Configurar HTTP**.

4.  En el cuadro de diálogo **Configuración de la directiva de HTTP para la regla**, desactive la casilla **Verificar normalización** y, a continuación, haga clic en **Aceptar**.

5.  En el cuadro de diálogo **Propiedades**, haga clic en **Aceptar**.

6.  En Forefront TMG, haga clic en **Aplicar** para habilitar los cambios. Cuando se abra el cuadro de diálogo **Descripción de cambio de configuración**, haga clic en **Aplicar**.

Una vez completada la instalación, puede probar el Servidor Office Web Apps mediante los procedimientos del tema [Comprobación de la configuración de Office Web Apps Server en Lync Server 2013](lync-server-2013-validating-the-configuration-of-office-web-apps-server.md).

