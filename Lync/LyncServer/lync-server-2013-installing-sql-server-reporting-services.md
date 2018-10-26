---
title: Instalación de SQL Server Reporting Services
TOCTitle: Instalación de SQL Server Reporting Services
ms:assetid: 638a1d0c-1ac7-4735-83f2-4df3d03c7cf9
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ204957(v=OCS.15)
ms:contentKeyID: 48275465
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Instalación de SQL Server Reporting Services

 

_**Última modificación del tema:** 2012-06-20_

Si tiene intención de usar los informes de supervisión de Microsoft Lync Server 2013 (vaya la siguiente sección si desea obtener más información), antes deberá instalar SQL Server Reporting Services. Esto puede realizarse al mismo tiempo que instala Microsoft SQL Server o con posterioridad. Si no ha instalado SQL Server, siga las instrucciones suministradas anteriormente en esta documentación. Al instalar SQL Server, asegúrese de que selecciona Reporting Services en la página Selección de características, ya que de este modo se instalará SQL Server Reporting Services.

Si ya tiene instalado SQL Server pero no SQL Server Reporting Services, puede agregar esta característica siguiendo las instrucciones pertinentes de SQL Server 2008 R2 o SQL Server 2012, según proceda.

Siga estos pasos para confirmar que Reporting Services se ha instalado correctamente:

1.  Si ejecuta Microsoft SQL Server 2008 R2, haga clic sucesivamente en **Inicio**, **Todos los programas**, **Microsoft SQL Server 2008 R2**, **Herramientas de configuración** y **Administrador de configuración de Reporting Services**.
    
    Si ejecuta Microsoft SQL Server 2012, haga clic sucesivamente en **Inicio**, **Todos los programas**, **Microsoft SQL Server 2012**, **Herramientas de configuración** y **Administrador de configuración de Reporting Services**.

2.  En el cuadro de diálogo **Conexión de configuración de Reporting Services**, compruebe que el cuadro **Nombre del servidor** refleja el nombre del servidor y, asimismo, que el cuadro **Instancia del servidor de informes** refleja el nombre de la instancia de SQL Server en la que están los datos de supervisión. Haga clic en **Conectar**.

El panel Estado del servidor de informes del Administrador de configuración de Reporting Services debe dejar constancia de que SQL Server Reporting Services está instalado y que Reporting Services está ejecutándose: el estado que debe indicar es **Iniciado**, mientras que el botón **Iniciar**debe aparecer atenuado y no disponible. Si Reporting Services no estás ejecutándose, haga clic en **Iniciar** para iniciar el servicio.

Haga lo siguiente si no aparece ninguna base de datos al lado de la etiqueta Nombre de la base de datos del servidor de informes:

1.  Haga clic en **Base de datos** en el Administrador de configuración de Reporting Services.

2.  Haga clic en **Cambiar base de datos** en el panel Base de datos del servidor de informes.

3.  En el panel Acción del Asistente para configuración de bases de datos del servidor de informes, seleccione **Crear una nueva base de datos del servidor de informes** y haga clic en **Siguiente**.

4.  En el panel Servidor de bases de datos del mismo asistente, confirme que la información de los cuadros **Nombre del servidor**, **Tipo de autenticación** y **Nombre de usuario** es correcta. Haga clic en **Probar conexión** para comprobar que se puede establecer una conexión con el servidor de base de datos y haga clic en **Siguiente**.

5.  En el panel Base de datos del asistente, acepte los valores predeterminados en **Nombre de la base de datos**, **Idioma** y **Modo del servidor de informes** y haga clic en **Siguiente**.

6.  En el panel Credenciales del asistente, confirme que la información de la lista desplegable **Tipo de autenticación** y de los cuadros **Nombre de usuario** y **Contraseña** es correcta y haga clic en **Siguiente**.

7.  En el panel Resumen del asistente, haga clic en **Siguiente**.

8.  En el panel Avanzar y finalizar del asistente, haga clic en **Finalizar**.

Para comprobar que se han configurado las direcciones URL de Reporting Services, haga clic en **Dirección URL del servicio web**. Deberán aparecer una o más direcciones URL bajo el encabezado **Direcciones URL del servicio web del servidor de informes**. Haga clic en cada una de ellas para constatar que accede a la página principal de la instalación local de SQL Server Reporting Services.

