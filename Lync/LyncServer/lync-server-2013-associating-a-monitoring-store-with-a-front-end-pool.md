---
title: "Asociación de almacén de supervisión a servidores front-end en Lync Server 2013"
TOCTitle: Asociación de un almacén de supervisión a un grupo de servidores front-end
ms:assetid: d3a20d5e-3f24-4cff-bc9b-4f84fea30e6b
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ205271(v=OCS.15)
ms:contentKeyID: 48276767
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Asociación de un almacén de supervisión a un grupo de servidores front-end en Lync Server 2013

 

_**Última modificación del tema:** 2013-04-22_

En Microsoft Lync Server 2013, los datos de supervisión solo se pueden recopilar en grupos de servidores front-end que se han asociado a un almacén de supervisión. Normalmente se define un grupo de servidores front-end en el Generador de topologías. Para asociar un almacén de supervisión a un grupo de servidores front-end nuevo, seleccione la opción **Supervisión (registros detallados de llamadas y registro de métrica de Calidad de la experiencia)** en la página **Seleccionar características** del Asistente para definir nuevo grupo de servidores front-end. Recuerde que si selecciona esta opción, también debe especificar un almacén SQL para completar el asistente. Ahora bien, no es obligatorio que este almacén exista en el momento que ejecute el asistente. Es decir, asocie primero un grupo de servidores a un almacén de supervisión y después instale y configure el almacén.

O bien, asocie un grupo de servidores front-end ya existente a un almacén de supervisión nuevo o diferente ejecutando el procedimiento siguiente:

1.  Haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y **Generador de topologías de Lync Server**.

2.  En el cuadro de diálogo **Generador de topologías**, seleccione **Descargar topología de la implementación existente** y después haga clic en **Aceptar**.

3.  En el cuadro de diálogo **Guardar como**, escriba un nombre de archivo para la topología actual y después haga clic en **Guardar**. Más tarde, si tiene problemas con la nueva topología, podrá recuperar y volver a publicar la topología guardada.

4.  En el Generador de topologías, expanda **Lync Server 2013**, expanda el nombre del sitio que contiene el grupo de servidores front-end y, luego, expanda **Grupos de servidores front-end Enterprise Edition**.

5.  Haga clic con el botón secundario en el nombre del grupo de servidores que se asociará al almacén de supervisión y después haga clic en **Editar propiedades**.

6.  En el cuadro de diálogo **Editar propiedades**, en la pestaña **General**, seleccione la opción **Supervisión (métricas CDR y QoE)** y después seleccione una base de datos SQL Server ya existente en la lista desplegable **Supervisión de SQL Server Store**. (O bien, haga clic en **Nuevo** para asociar el grupo de servidores a un almacén de base de datos nuevo). Si decide usar un almacén de base de datos nuevo, en el cuadro de diálogo **Definir nuevo almacén SQL**, escriba el nombre de dominio completo del equipo de SQL Server en el cuadro **FQDN de SQL Server**. Si quiere usar la instancia de SQL Server habitual del almacén, seleccione **Instancia predeterminada**, si no, seleccione **Instancia con nombre** y escriba el nombre de la instancia en el cuadro **Instancia con nombre**.
    
    El cuadro de diálogo **Editar propiedades** también le da la opción de crear un reflejo de SQL para la base de datos de supervisión (un reflejo de SQL permite mantener dos copias de las bases de datos de supervisión, una copia almacenada en el PC del almacén de supervisión y otra en el PC del reflejo de SQL). Para habilitar el reflejo, seleccione **Esta instancia de SQL está en una relación de reflejo** y escriba el número de puerto del servidor de reflejo en el cuadro **Número de puerto de reflejo**.

7.  En el cuadro de diálogo **Editar propiedades**, haga clic en **Aceptar**.

Después de asociar el almacén de supervisión al grupo de servidores front-end, publique la nueva topología antes de que los cambios entren en vigor. Para publicar la nueva topología, ejecute los pasos siguientes en el Generador de topologías:

1.  Haga clic en **Acción**, seleccione **Topología** y haga clic en **Publicar**.

2.  En el Asistente para publicar topología, en la página **Publicar la topología**, haga clic en **Siguiente**.

3.  En la página **Asistente de publicación completado**, haga clic en **Finalizar**.

Después de publicar la topología, instale la base de datos de supervisión en el PC que hospedará el almacén de supervisión. Instale la base de datos de supervisión usando el Shell de administración de Lync Server y Windows PowerShell. Para instalar la base de datos localmente, (es decir, para instalar la base de datos en el mismo PC que el Shell de administración de Lync Server), inicie el shell de administración en el PC adecuado, escriba el comando siguiente y presione ENTRAR:

    Install-CsDatabase -LocalDatabases

Cuando ejecute el comando anterior, Install-CsDatabase leerá la topología de Lync Server actual, determinará qué bases de datos deben instalarse en el PC local e instalará y configurará automáticamente las bases de datos.

Para instalar la base de datos en un PC remoto (es decir, en un PC que no sea el PC en el que se ejecute el shell de administración), incluya al menos dos parámetros: el parámetro ConfiguredDatabases y el parámetro SqlServerFqdn. Estos parámetros indican al cmdlet Install-CsDatabase que recupere la topología de Lync Server e instale y configure las bases de datos necesarias en el PC especificado por el parámetro SqlServerFqdn. El parámetro SqlServerFqdn debe usar un valor que represente el nombre de dominio completo del PC donde se vayan a instalar las bases de datos.

Por ejemplo, este comando instala la base de datos de supervisión en el PC atl-sql-001.litwareinc.com:

    Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn atl-sql-001.litwareinc.com

O bien, instale la base de datos de supervisión ejecutando el Asistente para implementación de Lync Server en el PC que hospedará el almacén de supervisión. Para ello, inicie sesión en el PC pertinente y ejecute el procedimiento siguiente:

1.  Haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, a continuación, haga clic en **Asistente para la implementación de Lync Server**.

2.  En el Asistente para la implementación, haga clic en **Instalar o actualizar sistema Lync Server**.

3.  En la página **Implementar**, en **Paso 2: configuración o supresión de componentes de Lync Server**, haga clic en **Ejecutar de nuevo**.

4.  En el Asistente de instalación de los componentes de Lync Server, en la página **Instalar componentes de Lync Server**, haga clic en **Siguiente**.

5.  En la página **Especificar ruta de acceso de archivos MSI**, escriba la ruta de acceso al archivo Ocscore.msi (un archivo incluido para los medios de instalación de Lync Server) y luego haga clic en **Siguiente**.

6.  En la página **Ejecución de comandos**, haga clic en **Finalizar**.

Para asegurarse de que todos los servicios de Lync Server necesarios se hayan iniciado, haga clic en **Ejecutar**, bajo el encabezado **Paso 4: Iniciar servicios** en la página **Implementar**

