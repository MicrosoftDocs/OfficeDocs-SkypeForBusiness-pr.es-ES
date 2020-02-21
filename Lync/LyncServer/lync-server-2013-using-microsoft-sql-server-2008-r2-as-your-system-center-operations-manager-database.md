---
title: 'Lync Server 2013: uso de Microsoft SQL Server 2008 R2 como base de datos de System Center Operations Manager'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using Microsoft SQL Server 2008 R2 as your System Center Operations Manager database
ms:assetid: 0efe76da-8854-499e-bdc7-3623244a8e85
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687969(v=OCS.15)
ms:contentKeyID: 49733555
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0001d70033aac6d7c6125bb9e4016143beefc80f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42212766"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="using-microsoft-sql-server-2008-r2-as-your-system-center-operations-manager-database-for-lync-server-2013"></a>Uso de Microsoft SQL Server 2008 R2 como base de datos de System Center Operations Manager para Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-07-29_

Para usar SQL Server 2008 R2 como base de datos back-end, complete los pasos que se detallan en este tema.

<div>

## <a name="configuring-sql-server-2008-r2-and-sql-server-reporting-services"></a>Configuración de SQL Server 2008 R2 y SQL Server Reporting Services

Antes de empezar a instalar System Center Operations Manager, debe realizar dos cambios en su SQL Server 2008 R2 y en la configuración de SQL Server Reporting Services. (Estos cambios solo son necesarios si usa SQL Server 2008 R2 como su base de datos de Operations Manager). En primer lugar, haga lo siguiente en el equipo donde se va a hospedar la base de datos de Operations Manager:

1.  Haga clic en **Inicio** y, a continuación, haga clic en **Ejecutar**.

2.  En el cuadro de diálogo **Ejecutar** , **escriba C\\: archivos\\de programa Microsoft\\ SQL\_Server MSRS10 50\\. ARCHINST\\Reporting Services ReportServer** y, a continuación, presione Entrar.

3.  En la carpeta **ReportServer**, abra el archivo **rsreportserver.config** en Notepad o cualquier otro editor de texto.

4.  Cerca del comienzo del archivo verá una serie de nodos "Add Key". Busque la entrada que comienza ** \<con Add key = "SecureConnectionLevel"** y establezca el valor en **0**:
    
        <Add Key="SecureConnectionLevel" Value="0"/>

5.  Guarde el archivo **rsreportserver.config** y luego cierre el editor de texto.

Después de actualizar el archivo de configuración del servidor de informes debe asignar el certificado correcto a SQL Server Reporting Services. Para ello:

1.  Haga clic en **Inicio**, en **todos los programas**, en **Microsoft SQL Server 2008 R2**, en **herramientas de configuración**y, a continuación, en Administrador de **configuración de Reporting Services**.

2.  En el cuadro de diálogo **Conexión de configuración de Reporting Services**, asegúrese de que el nombre de su servidor aparece en el cuadro **Nombre del servidor**. Seleccione la instancia de SQL Server que va a hospedar la base de datos de Operations Manager (por ejemplo, **ARCHINST**) en la lista desplegable **instancia del servidor de informes** y, a continuación, haga clic en **conectar**.

3.  En el Administrador de configuración de Reporting Services, haga clic en **Dirección URL del servicio web**.

4.  En la página **Dirección URL del servicio web**, seleccione el certificado que se usará para Reporting Services de la lista desplegable **Certificado SSL** y luego haga clic en **Aplicar**. Después de unos segundos, verá un par de direcciones URL debajo de **Direcciones URL del servicio web del servidor de informes**.

5.  Haga clic en ambas direcciones URL para verificar que puede acceder a SQL Server Reporting Services.

6.  Cierre el Administrador de configuración de Reporting Services.

</div>

<div>

## <a name="creating-a-system-center-operations-manager-database-for-use-with-sql-server-2008-r2"></a>Creación de una base de datos de System Center Operations Manager para usarla con SQL Server 2008 R2

Si desea configurar System Center Operations Manager para usar una base de datos de SQL Server 2008 R2, deberá "crear manualmente" la base de datos de Operations Manager en el equipo que ejecuta SQL Server 2008 R2. (De nuevo, estos pasos no son necesarios si utiliza SQL Server 2005 o SQL Server 2008 como base de datos back-end.)

Para crear manualmente una base de datos de Operations Manager, haga lo siguiente:

1.  En el medio de instalación de System Center Operations Manager 2007 R2,\\en la carpeta SupportTools AMD64, haga doble clic en **DBCreateWizard. exe**.

2.  En el Asistente de configuración de la base de datos, en la página **Bienvenido al Asistente de configuración de la base de datos**, haga clic en **Siguiente**.

3.  En la página **Información de base de datos** deje todas las opciones de configuración como se encuentran y luego haga clic en **Siguiente**

4.  En la **página Configuración del grupo de administración** , escriba un nombre para el grupo de administración (por ejemplo, supervisión de **Lync Server**) en el cuadro **nombre del grupo de administración** y, a continuación, haga clic en **siguiente**.

5.  En la página **Informes de error de Operations Manager** haga clic en **Siguiente**.

6.  En la página **Resumen** haga clic en **Finalizar **.

</div>

<div>

## <a name="creating-a-system-center-operations-manager-data-warehouse-for-use-with-sql-server-2008-r2"></a>Creación de un almacén de datos de System Center Operations Manager para usarlo con SQL Server 2008 R2

Microsoft Lync Server 2013 incluye tres nuevos informes de System Center Operations Manager:

  - **Informe de disponibilidad de escenario de principio a fin**   este informe detalla la disponibilidad o el tiempo activo para los servicios clave de Lync Server, como el registro o la presencia.

  - **Informe de capacidad**   con información de contador de rendimiento, este informe muestra las tendencias de los componentes del sistema, como la disponibilidad de la memoria y el uso del procesador.

  - **Informe de componentes**   este informe enumera los principales generadores de alertas agrupados por el componente de Lync Server.

Para poder usar estos nuevos informes, debe instalar un almacén de datos de System Center Operations Manager. (Un almacén de datos proporciona almacenamiento a largo plazo de datos de operaciones). Para usar un almacén de datos con SQL Server 2008 R2, debe llevar a cabo los siguientes pasos en el equipo que hospeda la base de datos de SQL Server:

1.  En el medio de instalación de System Center Operations Manager,\\en\\la carpeta SETUP SupportTools AMD64, haga doble clic en **DBCreateWizard. exe**.

2.  En el Asistente de configuración de la base de datos, en la página **Bienvenido al Asistente de configuración de la base de datos**, haga clic en **Siguiente**.

3.  En la página **Información de base de datos**, seleccione **Base de datos del almacén de datos de Operations Manager** de la lista desplegable **Tipo de base de datos** y luego haga clic en **Siguiente**.

4.  En la página **Resumen** haga clic en **Finalizar **.

</div>

<div>

## <a name="installing-the-system-center-operations-manager-console"></a>Instalación de la consola de System Center Operations Manager

La consola de Operations Manager es la principal herramienta que se usa para administrar System Center Operations Manager. Antes de instalar la consola de Operations Manager, asegúrese de que ha instalado una versión compatible de SQL Server junto con el servicio de informes de SQL Server. También se recomienda que ejecute el Administrador de configuración de SQL Server's Reporting Services para verificar que Reporting Service se ha instalado y configurado correctamente.

Para instalar la consola de System Center Operations Manager:

1.  En el medio de instalación de System Center Operations Manager, haga doble clic en **SetupOM. exe**.

2.  En System Center Operations Manager 2007 R2 Setup, haga clic en **comprobar requisitos previos**.

3.  En el visor de requisitos previos de System Center Operations Manager, seleccione los componentes de System Center que se van a instalar: (**servidor**; **Consola**; y **PowerShell**) y, a continuación, haga clic en **comprobar**. Verifique que no se haya informado ningún problema de bloqueo y luego haga clic en **Cerrar**. Si se ha informado algún problema de bloqueo, corrija el problema y luego haga clic en **Comprobar** para volver a ejecutar la comprobación de requisitos.

4.  En el programa de instalación de System Center Operations Manager, haga clic en **instalar Operations Manager**.

5.  En el Asistente para la instalación de System Center Operations Manager, en la página **éste es el Asistente para la instalación de System Center Operations Manager** , haga clic en **siguiente**.

6.  En la página **Contrato de licencia de usuario final**, seleccione **Acepto los términos del contrato de licencia** y, a continuación, haga clic en **Siguiente**.

7.  En la página **Registro del producto**, escriba su nombre en el cuadro **Nombre de usuario** y el nombre de su organización en el cuadro **Organización**. Escriba la clave del producto System Center Operations Manager en el cuadro **Escriba la clave del CD de 25 dígitos** y, a continuación, haga clic en **siguiente**.

8.  En la página **Instalación personalizada** seleccione las opciones de System Center que desea instalar y luego haga clic en **Siguiente**. Debe seleccionar **Servidor de administración**, **Interfaces de usuario** y **Consola web** para su instalación. **Base de datos** no debería seleccionarse ni instalarse.

9.  En la página **instancia de servidor de base de datos de SC** , compruebe que el nombre del equipo en el que están instaladas las bases de datos de Operations Manager aparece en el cuadro servidor de base de datos de **System Center** . Haga clic en **Siguiente**.

10. En la página **Cuenta de acción de los servidores de administración**, seleccione **Cuenta de equipo local o del dominio** y luego introduzca los valores apropiados en los cuadros **Cuenta de usuario**, **Contraseña** y **Equipo local o del dominio**. Haga clic en **Siguiente**.

11. En la página **Cuenta de servicio de configuración y SDK**, seleccione **Cuenta de equipo local o del dominio** y luego introduzca los valores apropiados en los cuadros **Cuenta de usuario**, **Contraseña** y **Equipo local o del dominio**. Haga clic en **Siguiente**.

12. En la página **Informes de error de Operations Manager** haga clic en **Siguiente**.

13. En la página **Programa para la mejora de la experiencia del usuario** haga clic en **Siguiente**.

14. En la página **Listo para instalar el programa**, haga clic en **Instalar**.

15. En la página **Completar la instalación de System Center Operations Manager**, desactive las casillas **Clave de cifrado de copias de seguridad** y **Iniciar la consola** y luego haga clic en **Finalizar**.

16. En el programa de instalación de System Center Operations Manager, haga clic en **salir**.

</div>

<div>

## <a name="installing-system-center-reporting-services"></a>Instalación de System Center Reporting Services

Después de instalar y configurar la consola de System Center Operations Manager, debe instalar System Center Reporting Services. Si usa SQL Server 2008 R2 como base de datos back-end de Operations Manager, significa que primero debe realizar un cambio temporal en el grupo de seguridad asociado con SQL Server Reporting Services. Si usa SQL Server 2008 R2, debe hacer lo siguiente:

1.  Haga clic en **Inicio**, elija **Herramientas administrativas** y, a continuación, haga clic en **Administrador de servidores**.

2.  En Administrador de servidores, expanda **Configuración**, expanda **Usuarios y grupos locales** y, a continuación, haga clic en **Grupos**.

3.  Busque el siguiente grupo, donde ATL-SC-001 representa el nombre de su equipo y ARCHINST representa la instancia de SQL Server para la base de datos de System Center: **SQLServerReportServerUser $ ATL-SC\_-001 $ MSRS10 50. ARCHINST**.

4.  Haga clic con el botón secundario en el grupo y, a continuación, haga clic en **Cambiar nombre**. Cambie el nombre del grupo eliminando ** \_50** del nombre del grupo. Por ejemplo: **SQLServerReportServerUser $ ATL-SC-001 $ MSRS10. ARCHINST**.

5.  Cierre el Administrador de servidores.

Ahora está listo para instalar System Center Reporting Services. Para ello:

1.  En el medio de instalación de System Center Operations Manager 2007 R2, haga doble clic en **SetupOM. exe**.

2.  En el programa de instalación de System Center Operations Manager 2007 R2, haga clic en **instalar informes de Operations Manager**.

3.  En el Asistente para la instalación de informes de System Center Operations Manager 2007 R2, en la página de **bienvenida a configuración de informes de Operations Manager** , haga clic en **siguiente**.

4.  En la página **Contrato de licencia de usuario final**, seleccione **Acepto los términos del contrato de licencia** y, a continuación, haga clic en **Siguiente**.

5.  En la página **Registro del producto**, asegúrese de que su nombre y el nombre de la organización aparecen en los cuadros **Nombre de usuario** y **Organización** y luego haga clic en **Siguiente**.

6.  En la página **Instalación personalizada**, haga clic en **Reporting Server** y seleccione **Este componente y todos los componentes que dependan de él se instalarán en el disco duro local**. Haga clic en **Almacén de datos** y seleccione **Este componente no estará disponible** y luego haga clic en **Siguiente**.

7.  En la página **Conectarse con el servidor de administración raíz**, escriba el nombre de su servidor de administración raíz Operations Manager en el cuadro **Servidor de administración raíz** y luego haga clic en **Siguiente**.

8.  En la página **Conectarse con el almacén de datos de Operations Manager**, escriba la instancia de SQL Server en la que se encuentra su almacén de datos en el cuadro **Instancia de SQL Server**. (Si su almacén de datos se encuentra en la instancia Predeterminado escriba simplemente el nombre del servidor; por ejemplo: atl-sql-001). Verifique que el nombre de la base de datos **OperationsManagerDW** aparezca en el cuadro **Nombre** y que el puerto **1433** aparezca en el cuadro **puerto de SQL Server**. Haga clic en **Siguiente**.

9.  En la página **Instancia de SQL Server Reporting**, seleccione su servidor de SQL Server Reporting de la lista desplegable**Introduzca el servidor de SQL Server Reporting Services** y luego haga clic en **Siguiente**.

10. En la página **Cuenta de escritura de almacén de datos**, introduzca el nombre y la contraseña del usuario al que se le asignarán inicialmente permisos de escritura en el almacén de datos en los cuadros **Cuenta de usuario** y **Contraseña**. Seleccione el dominio del usuario de la lista desplegable **Dominio** y luego haga clic en **Siguiente**.

11. En la página **Cuenta de lectura de datos**, introduzca el nombre y la contraseña de la cuenta de usuario que se utilizará cuando SQL Reporting Services realice consultas en el almacén de datos en los cuadros **Cuenta de usuario** y **Contraseña**. Seleccione el dominio de la cuenta de la lista desplegable **Dominio** y luego haga clic en **Siguiente**.

12. En la página **Informes de datos operativos**, haga clic en **Siguiente**.

13. En la página **Actualización de Microsoft**, haga clic en **Siguiente **.

14. En la página **Listo para instalar el programa**, haga clic en **Instalar**.

15. En la página **Finalización del Asistente de instalación de los componentes de Operations Manager Reporting**, haga clic en **Finalizar **.

16. En System Center Operations Manager 2007 R2 Setup, haga clic en **salir**.

Después de instalar los informes de System Center, use el siguiente procedimiento para restablecer el nombre del grupo de seguridad asociado con los informes de SQL Server. De nuevo, este procedimiento solo es necesario si usa SQL Server:

1.  Haga clic en **Inicio**, elija **Herramientas administrativas** y, a continuación, haga clic en **Administrador de servidores**.

2.  En Administrador de servidores, expanda **Configuración**, expanda **Usuarios y grupos locales** y, a continuación, haga clic en **Grupos**.

3.  Busque el siguiente grupo, donde ATL-SC-001 representa el nombre de su equipo y ARCHINST representa la instancia de SQL Server para las bases de datos de archivado y supervisión: **SQLServerReportServerUser $ ATL-SC-001 $ MSRS10. ARCHINST**.

4.  Haga clic con el botón secundario en el grupo y, a continuación, haga clic en **Cambiar nombre**. Cambie el nombre del grupo agregando ** \_50** al final del nombre del grupo, justo antes del nombre de la instancia de SQL Server. Por ejemplo: **SQLServerReportServerUser $ ATL-SC-001 $ MSRS10\_50. ARCHINST**.

5.  Cierre el Administrador de servidores.

Si la Consola de operaciones de System Center está abierta, necesitará cerrar la aplicación y volver a abrirla; si no hace esto, la pestaña **Elaboración de informes** no aparecerá en la interfaz de usuario de la Consola de operaciones. Tenga en cuenta que, después de reiniciar la Consola de operaciones por primera vez, podría tomar varios minutos antes de que todos los Informes de supervisión aparezcan en la pestaña **Elaboración de informes**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

