---
title: Importación de los paquetes de administración de Lync Server 2013
TOCTitle: Importación de los paquetes de administración de Lync Server 2013
ms:assetid: 846287e1-660f-453f-bdba-b2137b5f0ea1
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ205052(v=OCS.15)
ms:contentKeyID: 48275884
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Importación de los paquetes de administración de Lync Server 2013

 

_**Última modificación del tema:** 2016-12-08_

Puede extender las capacidades de System Center Operations Manager al instalar paquetes de administración (software que establece qué elementos System Center Operations Manager pueden supervisar y cómo deben ser supervisados y cómo se activan e informan las alertas). Lync Server 2013 incluye dos paquetes de administración System Center Operations Manager que proporciona las siguientes capacidades:

  - El paquete de componentes y administración de usuario (Microsoft.LS.2013.Monitoring.ComponentAndUser.mp) hace un seguimiento de los problemas de Lync Server incluidos en los registros de eventos, registrados por contadores de rendimiento o incluidos en las bases de datos de registro de detalles de llamadas (CDR) o de calidad de la experiencia (QoE). Para problemas críticos, System Center Operations Manager puede configurarse para que notifique inmediatamente a los administradores por correo electrónico, mensajería instantánea o mensaje de texto (SMS). SMS es la tecnología usada para enviar mensajes de texto desde un dispositivo móvil a otro).
    

    > [!NOTE]
    > Para obtener detalles acerca de la configuración de la notificación de Operations Manager, vea Configuración de las notificaciones en la Biblioteca TechNet en <A href="http://go.microsoft.com/fwlink/?linkid=268785%26clcid=0xc0a">http://go.microsoft.com/fwlink/?linkid=268785&amp;clcid=0xC0A</A>.



  - El paquete de administración de supervisión activa (Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp) prueba de forma proactiva los componentes claves de Lync Server como el inicio de sesión en el sistema, el intercambio de mensajes instantáneos o las llamadas desde un teléfono ubicado en una red telefónica conmutada (RTC). Estas pruebas se desarrollan usando los cmdlets de transacción sintética Lync Server. Por ejemplo, puede usar el cmdlet **Test-CsIM** para simular una conversación por mensaje instantáneo (IM) entre un par de usuarios de prueba. Si esta conversación de mensajes simulados falla, se genera una alerta.

Debe importar los paquetes de administración. Si no importa los paquetes de administración, no puede utilizar el Operations Manager para supervisar los eventos Lync Server o ejecutar transacciones sintéticas Lync Server.

El paquete de componentes y administración de usuario se utiliza para supervisar Lync Server 2013. Si se encuentra en un escenario de coexistencia, donde tiene Lync Server 2013 y Lync Server 2010 instalados, debe continuar usando los paquetes de administración de Lync Server 2010 para sus computadoras Lync Server 2010.


> [!NOTE]
> Los paquetes de administración para Lync Server 2010 incluyen el paquete de administración de supervisión Lync Server 2010 y el paquete de administración de supervisión de chat grupal Lync Server 2010.



Puede usar una de las siguientes herramientas para importar los paquetes de administración:

  - **System Center Operations Manager**   Con este método, usa el Operations Manager para agregar supervisión para Lync Server.

  - **Operations Manager Shell**   Puede usar el Shell Operations Manager para importar directamente o resolver problemas que puede encontrar cuando importa los paquetes de administración mediante la consola de System Center Operations Manager.

## Importar los paquetes de administración mediante el System Center Operations Manager

1.  Descargue los archivos Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp y Microsoft.LS.2013.Monitoring.ComponentAndUser.mp.

2.  En System Center Operations Manager, haga clic en **Administración**.

3.  En el panel **Administración**, haga clic con el botón secundario en **Paquetes de administración** y luego haga clic en **Importar paquetes de administración**.

4.  En el cuadro de diálogo **Seleccionar paquetes de administración**, haga clic en **Agregar** y luego en **Agregar desde el disco**.

5.  en el cuadro de diálogo **Conexión del catálogo en línea**, haga clic en **Cancelar** para evitar que Operations Manager se publique en línea para ver si existen dependencias para los paquetes de administración Lync Server. Si está utilizando System Center Operations Manager 2012, haga clic en **No**.

6.  En el cuadro de diálogo **Seleccionar paquetes de administración a importar**, encuentre y seleccione los archivos **Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp** y **Microsoft.LS.2013.Monitoring.ComponentAndUser.mp** y luego haga clic en **Abrir**. para seleccionar varios archivos en el cuadro de diálogo haga clic en el primer archivo, mantenga presionada la tecla Ctrl y haga clic en el segundo archivo.

7.  En el cuadro de diálogo **Seleccionar paquetes de administración**, haga clic en **Instalar**. Si obtiene un mensaje de error y no se puede producir la instalación, que generalmente significa que los archivos del paquete de administración se encuentran en una carpeta protegida por el control de cuentas de usuario de Windows. Si esto sucede, copie los archivos a una carpeta diferente y luego reinicie el proceso de importación e instalación.

8.  En el cuadro de diálogo **Seleccionar paquetes de administración**, haga clic en **Cerrar**. Tenga en cuenta que el proceso de instalación e importación puede requerir algunos minutos para completarse.

## Importar los paquetes de administración mediante el Shell Operations Manager

En general es más fácil importar los paquetes de administración mediante el uso de Operations Manager. Sin embargo, si se produce un error y no se puede producir la instalación, la consola no siempre proporciona informes adecuados de errores. En comparación, el Shell Operations Manager proporciona información detallada. Si está usando Operations Manager y encuentra problemas importando un paquete de administración, importe el paquete al usar el Shell Operations Manager. El Shell Operations Manager proporciona más información que puede ayudarlo a determinar por qué falló la importación.

Si está usando System Center Operations Manager 2007 R2, complete el siguiente procedimiento:

1.  Haga clic en **Inicio**, **Programas**, **System Center Operations Manager 2007 R2** y luego en **Operations Manager Shell**.

2.  En el Shell Operations Manager, escriba el siguiente comando en el símbolo del sistema, usando la ruta actual para su copia del archivo Microsoft.LS.2013.Monitoring.ActiveMonitoring.mpn y luego presione ENTRAR:
    
        MPImport.exe D:\MP\Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp

3.  Después de importar el primer paquete de administración, repita el proceso usando la ruta a su copia del archivo Microsoft.LS.2013.Monitoring.ComponentAndUser.mp:
    
        MPImport.exe D:\MP\Microsoft.LS.2013.Monitoring.ComponentAndUser.mp

4.  Cierre el Shell Operations Manager.

Si está usando System Center Operations Manager 2012, complete este procedimiento:

1.  Haga clic en **Iniciar**, **Programas**, **Microsoft System Center 2012**, **Operations Manager** y luego en **Operations Manager Shell**.

2.  En el Shell Operations Manager, escriba el siguiente comando en el símbolo del sistema, usando la ruta actual para su copia del archivo Microsoft.LS.2013.Monitoring.ActiveMonitoring.mpn y luego presione ENTRAR:
    
        Import-SCOMManagementPack -FullName "D:\MP\ Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp"

3.  Después de haber importado el primer paquete de administración, repita el proceso usando la ruta a su copia del archivo Microsoft.LS.2013.Monitoring.ComponentAndUser.mp:
    
        Import-SCOMManagementPack -FullName "D:\MP\ Microsoft.LS.2013.Monitoring.ComponentAndUser.mp"

