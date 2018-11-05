---
title: "Uso de MS SQL Server 2008 R2 como base de datos de System Center Operations Manager"
TOCTitle: "Ut. de Microsoft SQL Server 2008 R2 comme BD System Center Operations Manager"
ms:assetid: 0efe76da-8854-499e-bdc7-3623244a8e85
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ687969(v=OCS.15)
ms:contentKeyID: 49888888
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Uso de Microsoft SQL Server 2008 R2 como base de datos de System Center Operations Manager

 

_**Última modificación del tema:** 2013-07-29_

Para utilizar SQL Server 2008 R2 como su base de datos back-end, complete los pasos que se detallan en este tema.

## Configuración de SQL Server 2008 R2 y SQL Server Reporting Services

Antes de empezar a instalar System Center Operations Manager debe realizar dos cambios a su configuración de SQL Server 2008 R2 y SQL Server Reporting Services. (Estos cambios solo son necesarios si utiliza SQL Server 2008 R2 como su base de datos de Operations Manager). Primero, haga lo siguiente en el equipo que hospedará su base de datos de Operations Manager:

1.  Haga clic en **Inicio** y luego haga clic en **Ejecutar**.

2.  En el cuadro de diálogo **Ejecutar**, escriba **C:\\Program Files\\Microsoft SQL Server\\ MSRS10\_50.ARCHINST\\Reporting Services\\ReportServer** y luego presione ENTRAR.

3.  En la carpeta **ReportServer**, abra el archivo **rsreportserver.config** en Notepad o cualquier otro editor de texto.

4.  Cerca del comienzo del archivo verá una serie de nodos "Add Key". Encuentre la entrada que comienza diciendo **\<Add Key="SecureConnectionLevel"** y establezca el valor en **0**:
    
        <Add Key="SecureConnectionLevel" Value="0"/>

5.  Guarde el archivo **rsreportserver.config** y luego cierre el editor de texto.

Después de actualizar el archivo de configuración del servidor de informes debe asignar el certificado correcto a SQL Server Reporting Services. Para ello:

1.  Haga clic en **Inicio**, en **Todos los programas**, en **Microsoft SQL Server 2008 R2**, en **Herramientas de configuración** y, a continuación, haga clic en **Administrador de configuración de Reporting Services**.

2.  En el cuadro de diálogo **Conexión de configuración de Reporting Services**, asegúrese de que el nombre de su servidor aparece en el cuadro **Nombre del servidor**. Seleccione la instancia SQL Server que hospedará su base de datos de Operations Manager (por ejemplo, **ARCHINST**) de la lista desplegable **Instancia del servidor de informes** y luego haga clic en **Conectar**.

3.  En el Administrador de configuración de Reporting Services, haga clic en **Dirección URL del servicio web**.

4.  En la página **Dirección URL del servicio web**, seleccione el certificado que se usará para Reporting Services de la lista desplegable **Certificado SSL** y luego haga clic en **Aplicar**. Después de unos segundos, verá un par de direcciones URL debajo de **Direcciones URL del servicio web del servidor de informes**.

5.  Haga clic en ambas direcciones URL para verificar que puede acceder a SQL Server Reporting Services.

6.  Cierre el Administrador de configuración de Reporting Services.

## Creación de una base de datos de System Center Operations Manager para utilizar con SQL Server 2008 R2

Si quiere configurar System Center Operations Manager para que use una base de datos SQL Server 2008 R2, necesitará crear "manualmente" la base de datos de Operations Manager en el equipo que tenga SQL Server 2008 R2. (Nuevamente, estos pasos no son necesarios si usa SQL Server 2005 o SQL Server 2008 como base de datos back-end).

Para crear manualmente una base de datos de Operations Manager realice lo siguiente:

1.  En los medios de configuración de System Center Operations Manager 2007 R2, en la carpeta SupportTools\\AMD64, haga doble clic en **DBCreateWizard.exe**.

2.  En el Asistente de configuración de la base de datos, en la página **Bienvenido al Asistente de configuración de la base de datos**, haga clic en **Siguiente**.

3.  En la página **Información de base de datos** deje todas las opciones de configuración como se encuentran y luego haga clic en **Siguiente**

4.  En la página **Configuración del Grupo de administración** escriba un nombre para su Grupo de administración (por ejemplo, **Supervisión de Lync Server**) en el cuadro **nombre del Grupo de administración** y luego haga clic en **Siguiente**.

5.  En la página **Informes de error de Operations Manager** haga clic en **Siguiente**.

6.  En la página **Resumen** haga clic en **Finalizar** .

## Creación de un almacén de datos de System Center Operations Manager para utilizar con SQL Server 2008 R2

Microsoft Lync Server 2013 se suministra con tres nuevos informes System Center Operations Manager:

  - **Informe de disponibilidad de escenario de principio a fin**   Este informe detalla la disponibilidad o el tiempo de funcionamiento de los servicios clave de Lync Server como el registro o la presencia.

  - **Informe de capacidad**   Utilizando información del contador de rendimiento, este informe muestra tendencias de los componentes del sistema como la disponibilidad de la memoria y el uso del procesador.

  - **Informe de componentes**   Este informe enumera los generadores de alertas principales agrupados por el componente Lync Server.

Para utilizar estos nuevos informes debe instalar un almacén de datos de System Center Operations Manager. (Un almacén de datos proporciona almacenamiento a largo plazo de datos de operaciones). Para utilizar un almacén de datos con SQL Server 2008 R2 debe realizar los siguientes pasos en el equipo que hospede su base de datos SQL Server:

1.  En los medios de configuración de System Center Operations Manager, en la carpeta Setup\\SupportTools\\AMD64, haga doble clic en **DBCreateWizard.exe**.

2.  En el Asistente de configuración de la base de datos, en la página **Bienvenido al Asistente de configuración de la base de datos**, haga clic en **Siguiente**.

3.  En la página **Información de base de datos**, seleccione **Base de datos del almacén de datos de Operations Manager** de la lista desplegable **Tipo de base de datos** y luego haga clic en **Siguiente**.

4.  En la página **Resumen** haga clic en **Finalizar** .

## Instalación de la consola System Center Operations Manager

La consola Operations Manager es la herramienta principal utilizada para administrar System Center Operations Manager. Antes de instalar la consola Operations Manager, asegúrese de que ha instalado una versión admitida de SQL Server junto con el SQL Server Reporting Service. También se recomienda que ejecute el Administrador de configuración de SQL Server's Reporting Services para verificar que Reporting Service se ha instalado y configurado correctamente.

Para instalar la consola System Center Operations Manager:

1.  En los medios de configuración de System Center Operations Manager, haga doble clic en **SetupOM.exe**.

2.  En la Instalación de System Center Operations Manager 2007 R2, haga clic en **Comprobar requisitos**.

3.  En el Visualizador de requisitos de System Center Operations Manager, seleccione los componentes de System Center que desea instalar: (**Servidor**; **Consola** y **PowerShell**) y luego haga clic en **Comprobar**. Verifique que no se haya informado ningún problema de bloqueo y luego haga clic en **Cerrar**. Si se ha informado algún problema de bloqueo, corrija el problema y luego haga clic en **Comprobar** para volver a ejecutar la comprobación de requisitos.

4.  En la Instalación de System Center Operations Manager, haga clic en **Instalar Operations Manager**.

5.  En el Asistente de instalación de System Center Operations Manager, en la página **Bienvenido al Asistente de instalación de System Center Operations Manager**, haga clic en **Siguiente**.

6.  En la página **Contrato de licencia de usuario final**, seleccione **Acepto los términos del contrato de licencia** y, a continuación, haga clic en **Siguiente**.

7.  En la página **Registro del producto**, escriba su nombre en el cuadro **Nombre de usuario** y el nombre de su organización en el cuadro **Organización**. Escriba su clave de producto de System Center Operations Manager en el cuadro **Introduzca su clave de CD de 25 dígitos** y luego haga clic en **Siguiente**.

8.  En la página **Instalación personalizada** seleccione las opciones de System Center que desea instalar y luego haga clic en **Siguiente**. Debe seleccionar **Servidor de administración**, **Interfaces de usuario** y **Consola web** para su instalación. **Base de datos** no debería seleccionarse ni instalarse.

9.  En la página **Instancia del servidor de base de datos SC**, verifique que el nombre del equipo en el que están instaladas las bases de datos de Operations Manager aparezca en el cuadro **Servidor de base de datos de System Center**. Haga clic en **Siguiente**.

10. En la página **Cuenta de acción de los servidores de administración**, seleccione **Cuenta de equipo local o del dominio** y luego introduzca los valores apropiados en los cuadros **Cuenta de usuario**, **Contraseña** y **Equipo local o del dominio**. Haga clic en **Siguiente**.

11. En la página **Cuenta de servicio de configuración y SDK**, seleccione **Cuenta de equipo local o del dominio** y luego introduzca los valores apropiados en los cuadros **Cuenta de usuario**, **Contraseña** y **Equipo local o del dominio**. Haga clic en **Siguiente**.

12. En la página **Informes de error de Operations Manager** haga clic en **Siguiente**.

13. En la página **Programa para la mejora de la experiencia del usuario** haga clic en **Siguiente**.

14. En la página **Listo para instalar el programa**, haga clic en **Instalar**.

15. En la página **Completar la instalación de System Center Operations Manager**, desactive las casillas **Clave de cifrado de copias de seguridad** y **Iniciar la consola** y luego haga clic en **Finalizar**.

16. En la Instalación de System Center Operations Manager, haga clic en **Salir**.

## Instalación de System Center Reporting Services

Después de instalar y configurar la consola System Center Operations Manager debe instalar System Center Reporting Services. Si está utilizando SQL Server 2008 R2 como su base de datos back-end Operations Manager, eso significa que debe primero hacer un cambio temporario al grupo de seguridad asociado con SQL Server Reporting Services. Si utiliza SQL Server 2008 R2, debe realizar lo siguiente:

1.  Haga clic en **Inicio**, elija **Herramientas administrativas** y, a continuación, haga clic en **Administrador de servidores**.

2.  En Administrador de servidores, expanda **Configuración**, expanda **Usuarios y grupos locales** y, a continuación, haga clic en **Grupos**.

3.  Ubique el siguiente grupo, en el que atl-sc-001 representa el nombre de su equipo y ARCHINST representa la instancia SQL Server para la base de datos de System Center: **SQLServerReportServerUser$atl-sc-001$MSRS10\_50.ARCHINST**.

4.  Haga clic con el botón secundario en el grupo y, a continuación, haga clic en **Cambiar nombre**. Cambie el nombre del grupo eliminando **\_50** del nombre del grupo. Por ejemplo: **SQLServerReportServerUser$atl-sc-001$MSRS10.ARCHINST**.

5.  Cierre el Administrador de servidores.

Ahora está listo para instalar System Center Reporting Services. Para ello:

1.  En los medios de configuración de System Center Operations Manager 2007 R2, haga doble clic en **SetupOM.exe**.

2.  En la Instalación de System Center Operations Manager 2007 R2, haga clic en **Instalar Operations Manager Reporting**.

3.  En el Asistente de instalación de Reporting de System Center Operations Manager 2007 R2, en la página **Bienvenido a la Instalación de Operations Manager Reporting**, haga clic en **Siguiente**.

4.  En la página **Contrato de licencia de usuario final**, seleccione **Acepto los términos del contrato de licencia** y, a continuación, haga clic en **Siguiente**.

5.  En la página **Registro del producto**, asegúrese de que su nombre y el nombre de la organización aparecen en los cuadros **Nombre de usuario** y **Organización** y luego haga clic en **Siguiente**.

6.  En la página **Instalación personalizada**, haga clic en **Reporting Server** y seleccione **Este componente y todos los componentes que dependan de él se instalarán en el disco duro local**. Haga clic en **Almacén de datos** y seleccione **Este componente no estará disponible** y luego haga clic en **Siguiente**.

7.  En la página **Conectarse con el servidor de administración raíz**, escriba el nombre de su servidor de administración raíz Operations Manager en el cuadro **Servidor de administración raíz** y luego haga clic en **Siguiente**.

8.  En la página **Conectarse con el almacén de datos de Operations Manager**, escriba la instancia de SQL Server en la que se encuentra su almacén de datos en el cuadro **Instancia de SQL Server**. (Si su almacén de datos se encuentra en la instancia Predeterminado escriba simplemente el nombre del servidor; por ejemplo: atl-sql-001). Verifique que el nombre de la base de datos **OperationsManagerDW** aparezca en el cuadro **Nombre** y que el puerto **1433** aparezca en el cuadro **puerto de SQL Server**. Haga clic en **Siguiente**.

9.  En la página **Instancia de SQL Server Reporting**, seleccione su servidor de SQL Server Reporting de la lista desplegable**Introduzca el servidor de SQL Server Reporting Services** y luego haga clic en **Siguiente**.

10. En la página **Cuenta de escritura de almacén de datos**, introduzca el nombre y la contraseña del usuario al que se le asignarán inicialmente permisos de escritura en el almacén de datos en los cuadros **Cuenta de usuario** y **Contraseña**. Seleccione el dominio del usuario de la lista desplegable **Dominio** y luego haga clic en **Siguiente**.

11. En la página **Cuenta de lectura de datos**, introduzca el nombre y la contraseña de la cuenta de usuario que se utilizará cuando SQL Reporting Services realice consultas en el almacén de datos en los cuadros **Cuenta de usuario** y **Contraseña**. Seleccione el dominio de la cuenta de la lista desplegable **Dominio** y luego haga clic en **Siguiente**.

12. En la página **Informes de datos operativos**, haga clic en **Siguiente**.

13. En la página **Actualización de Microsoft**, haga clic en **Siguiente** .

14. En la página **Listo para instalar el programa**, haga clic en **Instalar**.

15. En la página **Finalización del Asistente de instalación de los componentes de Operations Manager Reporting**, haga clic en **Finalizar** .

16. En la Instalación de System Center Operations Manager 2007 R2, haga clic en **Salir**.

Una vez que se haya instalado System Center Reporting, utilice el siguiente procedimiento para restablecer el nombre del grupo de seguridad asociado con SQL Server Reporting. Nuevamente, este procedimiento solo es necesario si utiliza SQL Server:

1.  Haga clic en **Inicio**, elija **Herramientas administrativas** y, a continuación, haga clic en **Administrador de servidores**.

2.  En Administrador de servidores, expanda **Configuración**, expanda **Usuarios y grupos locales** y, a continuación, haga clic en **Grupos**.

3.  Ubique el siguiente grupo, en el que atl-sc-001 representa el nombre de su equipo y ARCHINST representa la instancia SQL Server para las bases de datos de archivado y supervisión: **SQLServerReportServerUser$atl-sc-001$MSRS10.ARCHINST**.

4.  Haga clic con el botón secundario en el grupo y, a continuación, haga clic en **Cambiar nombre**. Cambie el nombre del grupo agregando **\_50** al final del nombre del grupo, justo antes del nombre de instancia SQL Server. Por ejemplo: **SQLServerReportServerUser$atl-sc-001$MSRS10\_50.ARCHINST**.

5.  Cierre el Administrador de servidores.

Si la Consola de operaciones de System Center está abierta, necesitará cerrar la aplicación y volver a abrirla; si no hace esto, la pestaña **Elaboración de informes** no aparecerá en la interfaz de usuario de la Consola de operaciones. Tenga en cuenta que, después de reiniciar la Consola de operaciones por primera vez, podría tomar varios minutos antes de que todos los Informes de supervisión aparezcan en la pestaña **Elaboración de informes**.

