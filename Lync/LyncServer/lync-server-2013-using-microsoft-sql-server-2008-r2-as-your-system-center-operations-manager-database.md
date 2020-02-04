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
ms.openlocfilehash: 27516e7ca6c3fb70a01b7c1d245054d515ae351b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744060"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-microsoft-sql-server-2008-r2-as-your-system-center-operations-manager-database-for-lync-server-2013"></a>Uso de Microsoft SQL Server 2008 R2 como base de datos de System Center Operations Manager para Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-07-29_

Para usar SQL Server 2008 R2 como base de datos back-end, complete los pasos que se describen en este tema.

<div>

## <a name="configuring-sql-server-2008-r2-and-sql-server-reporting-services"></a>Configuración de SQL Server 2008 R2 y SQL Server Reporting Services

Antes de empezar a instalar System Center Operations Manager, debe realizar dos cambios en su SQL Server 2008 R2 y en la configuración de SQL Server Reporting Services. (Estos cambios solo son necesarios si usa SQL Server 2008 R2 como la base de datos de Operations Manager). En primer lugar, haga lo siguiente en el equipo que hospedará la base de datos de Operations Manager:

1.  Haga clic en **Inicio** y, después, en **Ejecutar**.

2.  En el cuadro de diálogo **Ejecutar** , **escriba C\\: archivos\\de programa Microsoft\\ SQL\_Server MSRS10 50\\. ARCHINST\\Reporting Services ReportServer** y, a continuación, presione Entrar.

3.  En la carpeta **ReportServer** , abra el archivo **Rsreportserver. config** en el Bloc de notas o en cualquier otro editor de texto.

4.  Cerca del principio del archivo, verá una serie de nodos "agregar clave". Busque la entrada que comienza ** \<Add key = "SecureConnectionLevel"** y establezca el valor en **0**:
    
        <Add Key="SecureConnectionLevel" Value="0"/>

5.  Guarde el archivo **Rsreportserver. config** y, a continuación, cierre el editor de texto.

Después de actualizar el archivo de configuración del servidor de informes, debe asignar el certificado correcto a SQL Server Reporting Services. Para ello:

1.  Haga clic en **Inicio**, en **todos los programas**, en **Microsoft SQL Server 2008 R2**, en **herramientas de configuración**y, por último, en Administrador de **configuración de Reporting Services**.

2.  En el cuadro de diálogo **conexión de configuración de Reporting Services** , asegúrese de que el nombre del servidor aparece en el cuadro **nombre del servidor** . Seleccione la instancia de SQL Server que hospedará la base de datos de Operations Manager (por ejemplo, **ARCHINST**) en la lista desplegable **instancia del servidor de informes** y, a continuación, haga clic en **conectar**.

3.  En el administrador de configuración de Reporting Services, haga clic en **URL de servicio Web**.

4.  En la página **dirección URL de servicio Web** , seleccione el certificado que se usará para su Reporting Services en la lista desplegable **certificado SSL** y, a continuación, haga clic en **aplicar**. Después de unos segundos, verá un par de direcciones URL en el **servicio Web del servidor de informes**.

5.  Haga clic en ambas direcciones URL para comprobar que puede obtener acceso a SQL Server Reporting Services.

6.  Cierre el administrador de configuración de Reporting Services.

</div>

<div>

## <a name="creating-a-system-center-operations-manager-database-for-use-with-sql-server-2008-r2"></a>Crear una base de datos de System Center Operations Manager para usarla con SQL Server 2008 R2

Si desea configurar System Center Operations Manager para usar una base de datos de SQL Server 2008 R2, tendrá que crear manualmente la base de datos de Operations Manager en el equipo que ejecuta SQL Server 2008 R2. (Una vez más, estos pasos no son necesarios si usa SQL Server 2005 o SQL Server 2008 como base de datos back-end).

Para crear manualmente una base de datos de Operations Manager, haga lo siguiente:

1.  En el medio de instalación de System Center Operations Manager 2007 R2,\\en la carpeta SupportTools AMD64, haga doble clic en **DBCreateWizard. exe**.

2.  En el Asistente para configuración de base de datos, en la página asistente **para configuración de base de datos** , haga clic en **siguiente**.

3.  En la página información de la **base** de datos, mantenga toda la configuración tal cual y haga clic en **siguiente** .

4.  En la **página Configuración del grupo de administración** , escriba un nombre para el grupo de administración (por ejemplo, supervisión de **Lync Server**) en el cuadro **nombre del grupo de administración** y, a continuación, haga clic en **siguiente**.

5.  En la página **informes de errores de Operations Manager** , haga clic en **siguiente**.

6.  En la página **Resumen** , haga clic en **Finalizar**.

</div>

<div>

## <a name="creating-a-system-center-operations-manager-data-warehouse-for-use-with-sql-server-2008-r2"></a>Crear un almacén de datos de System Center Operations Manager para su uso con SQL Server 2008 R2

Microsoft Lync Server 2013 viene con tres nuevos informes de System Center Operations Manager:

  - **Informe de disponibilidad de escenario de principio a fin**   este informe detalla la disponibilidad y el tiempo de actividad de los servicios clave de Lync Server, como el registro o la presencia.

  - **Informe de capacidad**   con información de contador de rendimiento, este informe muestra tendencias de componentes del sistema, como la disponibilidad de memoria y el uso del procesador.

  - **Informe de componente**   este informe enumera los principales generadores de alertas agrupados por el componente Lync Server.

Para poder usar estos nuevos informes, debe instalar un almacén de datos de System Center Operations Manager. (Un almacén de datos proporciona almacenamiento a largo plazo de datos de operaciones). Para usar un almacén de datos con SQL Server 2008 R2, debe llevar a cabo los siguientes pasos en el equipo que hospeda la base de datos de SQL Server:

1.  En el medio de instalación de System Center Operations Manager,\\en\\la carpeta SETUP SupportTools AMD64, haga doble clic en **DBCreateWizard. exe**.

2.  En el Asistente para configuración de base de datos, en la página asistente **para configuración de base de datos** , haga clic en **siguiente**.

3.  En la página **información** de la base de datos, seleccione base de datos del almacén de **datos de Operations Manager** de la lista desplegable **tipo de base** de datos y haga clic en **siguiente**.

4.  En la página **Resumen** , haga clic en **Finalizar**.

</div>

<div>

## <a name="installing-the-system-center-operations-manager-console"></a>Instalar la consola de System Center Operations Manager

La consola de Operations Manager es la principal herramienta que se usa para administrar System Center Operations Manager. Antes de instalar la consola de Operations Manager, asegúrese de que ha instalado una versión compatible de SQL Server junto con SQL Server Reporting Services. También se recomienda que ejecute el administrador de configuración de Reporting Services de SQL Server para comprobar que el servicio de informes se ha instalado y configurado correctamente.

Para instalar la consola de System Center Operations Manager:

1.  En el medio de instalación de System Center Operations Manager, haga doble clic en **SetupOM. exe**.

2.  En System Center Operations Manager 2007 R2 Setup, haga clic en **check Prerequisites**.

3.  En el visor de requisitos previos de System Center Operations Manager, seleccione los componentes de System Center que se instalarán: (**servidor**; **Consola**; y **PowerShell**) y, a continuación, haga clic en **comprobar**. Compruebe que no se han notificado problemas de bloqueo y, a continuación, haga clic en **cerrar**. Si se ha notificado un problema de bloqueo, corrija el problema y, a continuación, haga clic en **comprobar** para volver a ejecutar las pruebas de requisitos previos.

4.  En el programa de instalación de System Center Operations Manager, haga clic en **instalar Operations Manager**.

5.  En el Asistente de configuración de System Center Operations Manager, en la página **Asistente de configuración de System Center Operations Manager** , haga clic en **siguiente**.

6.  En la página **contrato de licencia para el usuario final** , seleccione Acepto **los términos del contrato de licencia** y, a continuación, haga clic en **siguiente**.

7.  En la página **registro del producto** , escriba su nombre en el cuadro Nombre de **usuario** y nombre de la organización en el cuadro **organización** . Escriba la clave de producto de System Center Operations Manager en el cuadro **Escriba la clave de CD de 25 dígitos** y, a continuación, haga clic en **siguiente**.

8.  En la página **instalación personalizada** , seleccione las opciones de System Center que se instalarán y, a continuación, haga clic en **siguiente**. Debe seleccionar **servidor de administración**, **interfaces de usuario**y **consola web** para su instalación. La **base de datos** no se debe seleccionar y no debe instalarse.

9.  En la página **instancia del servidor de base de datos SC** , compruebe que el nombre del equipo en el que están instaladas las bases de datos de Operations Manager aparece en el cuadro **System Center Database Server** . Haga clic en **Siguiente**.

10. En la página de la **cuenta de acción del servidor de administración** , seleccione **dominio o cuenta de equipo local** y, a continuación, escriba los valores correspondientes en los cuadros **cuenta de usuario**, **contraseña**y **dominio o equipo local** . Haga clic en **Siguiente**.

11. En la página de la **cuenta de servicio de configuración y SDK** , seleccione **dominio o cuenta de equipo local** y, a continuación, escriba los valores apropiados en los cuadros **cuenta de usuario**, **contraseña**y **dominio o equipo local** . Haga clic en **Siguiente**.

12. En la página **informes de errores de Operations Manager** , haga clic en **siguiente**.

13. En la página del programa de mejora de la **experiencia del cliente** , haga clic en **siguiente**.

14. En la página **listo para instalar el programa** , haga clic en **instalar**.

15. En la página **finalización del programa de instalación de System Center Operations Manager** , desactive la casilla de verificación **clave de cifrado de copia de seguridad** e **inicie la consola** y haga clic en **Finalizar**.

16. En el programa de instalación de System Center Operations Manager, haga clic en **salir**.

</div>

<div>

## <a name="installing-system-center-reporting-services"></a>Instalar System Center Reporting Services

Después de instalar y configurar la consola de System Center Operations Manager, debe instalar System Center Reporting Services. Si usa SQL Server 2008 R2 como la base de datos back-end de Operations Manager, significa que primero debe realizar un cambio temporal en el grupo de seguridad asociado con SQL Server Reporting Services. Si usa SQL Server 2008 R2, debe hacer lo siguiente:

1.  Haga clic en **Inicio**, seleccione **herramientas administrativas**y, a continuación, haga clic en **Administrador del servidor**.

2.  En Administrador del servidor, expanda **configuración**, expanda **usuarios locales y grupos**y, a continuación, haga clic en **grupos**.

3.  Busque el grupo siguiente, donde ATL-SC-001 representa el nombre de su equipo y ARCHINST representa la instancia de SQL Server para la base de datos de System Center: **SQLServerReportServerUser $ ATL-SC\_-001 $ MSRS10 50. ARCHINST**.

4.  Haga clic con el botón secundario en el grupo y haga clic en **cambiar nombre**. Cambie el nombre del grupo eliminando ** \_50** del nombre del grupo. Por ejemplo: **SQLServerReportServerUser $ ATL-SC-001 $ MSRS10. ARCHINST**.

5.  Cierre el administrador del servidor.

En este momento, está listo para instalar System Center Reporting Services. Para ello, haga lo siguiente:

1.  En el medio de instalación de System Center Operations Manager 2007 R2, haga doble clic en **SetupOM. exe**.

2.  En el programa de instalación de System Center Operations Manager 2007 R2, haga clic en **instalar informes de Operations Manager**.

3.  En el Asistente de configuración de informes de System Center Operations Manager 2007 R2, en la página de configuración de informes de la **bienvenida a Operations Manager** , haga clic en **siguiente**.

4.  En la página contrato de licencia para el **usuario final** , seleccione Acepto **las condiciones del contrato de licencia** y, a continuación, haga clic en **siguiente**.

5.  En la página **registro del producto** , asegúrese de que su nombre y el nombre de su organización aparecen en los cuadros nombre de **usuario** y **organización** y, a continuación, haga clic en **siguiente**.

6.  En la página **Configuración personalizada** , haga clic en **servidor de informes** y seleccione **este componente y todos los componentes dependientes se instalarán en la unidad de disco local**. Haga clic en **almacén de datos** y seleccione **este componente no estará disponible**y, a continuación, haga clic en **siguiente**.

7.  En la página **conectar con el servidor de administración raíz** , escriba el nombre del servidor de administración de raíz de Operations Manager en el cuadro **servidor de administración raíz** y, a continuación, haga clic en **siguiente**.

8.  En la página **conectar con el almacén de datos de Operations Manager** , escriba la instancia de SQL Server donde se encuentra el almacén de datos en el cuadro **instancia de SQL Server** . (Si el almacén de datos se encuentra en la instancia predeterminada, simplemente escriba el nombre del servidor; por ejemplo: ATL-SQL-001.) Compruebe que el nombre de la base de datos **OperationsManagerDW** aparece en el cuadro **nombre** y que el puerto **1433** aparece en el cuadro **Puerto de SQL Server** . Haga clic en **Siguiente**.

9.  En la página **instancia de SQL Server Reporting** , seleccione su SQL Server Reporting Server en la lista desplegable **entrar en el servidor de SQL Server Reporting Services** y haga clic en **siguiente**.

10. En la página de escritura de la **cuenta de almacenamiento de datos** , escriba el nombre y la contraseña del usuario al que se asignará inicialmente permisos de escritura para el almacén de datos en los cuadros cuenta de **usuario** y **contraseña** . Seleccione el dominio del usuario de la lista desplegable **dominio** y haga clic en **siguiente**.

11. En la página **cuenta de lector de datos** , escriba el nombre y la contraseña de la cuenta de usuario que se usará cuando SQL Reporting Services consulte el almacén de datos en los cuadros cuenta de **usuario** y **contraseña** . Seleccione el dominio de la cuenta en la lista desplegable **dominio** y haga clic en **siguiente**.

12. En la página **informes de datos operativos** , haga clic en **siguiente**.

13. En la página **Microsoft Update** , haga clic en **siguiente**.

14. En la página **listo para instalar el programa** , haga clic en **instalar**.

15. En la página **finalización del Asistente para la instalación de los componentes de informes de Operations Manager** , haga clic en **Finalizar**.

16. En System Center Operations Manager 2007 R2 Setup, haga clic en **Exit**.

Después de haber instalado System Center reporting, use el siguiente procedimiento para restablecer el nombre del grupo de seguridad asociado a los informes de SQL Server. De nuevo, este procedimiento solo es necesario si usas SQL Server:

1.  Haga clic en **Inicio**, seleccione **herramientas administrativas**y, a continuación, haga clic en **Administrador del servidor**.

2.  En Administrador del servidor, expanda **configuración**, expanda **usuarios locales y grupos**y, a continuación, haga clic en **grupos**.

3.  Busque el grupo siguiente, donde ATL-SC-001 representa el nombre de su equipo y ARCHINST representa la instancia de SQL Server para las bases de datos de archivado y supervisión: **SQLServerReportServerUser $ ATL-SC-001 $ MSRS10. ARCHINST**.

4.  Haga clic con el botón secundario en el grupo y haga clic en **cambiar nombre**. Cambie el nombre del grupo agregando ** \_50** al final del nombre del grupo, justo antes del nombre de la instancia de SQL Server. Por ejemplo: **SQLServerReportServerUser $ ATL-SC-001 $ MSRS10\_50. ARCHINST**.

5.  Cierre el administrador del servidor.

Si la consola de Operations System Center está abierta, tendrá que cerrar la aplicación y, a continuación, reiniciarla. Si no lo hace, la ficha **informes** no aparecerá en la interfaz de usuario de la consola de operaciones. Tenga en cuenta que, después de reiniciar la consola de operaciones por primera vez, puede demorar varios minutos en aparecer todos los informes de supervisión en la pestaña **informes** .

</div>

</div>

<span> </span>

</div>

</div>

</div>

