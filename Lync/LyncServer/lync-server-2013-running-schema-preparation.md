---
title: 'Lync Server 2013: Ejecutar la preparación del esquema'
TOCTitle: Ejecutar la preparación del esquema
ms:assetid: 9d02bdb1-ff29-417a-bcce-b068b31207d8
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg412729(v=OCS.15)
ms:contentKeyID: 48276144
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Ejecutar la preparación del esquema de Active Directory en Lync Server 2013

 

_**Última modificación del tema:** 2016-12-08_

Puede utilizar el programa de instalación o los cmdlets de Shell de administración de Lync Server para preparar el esquema de Active Directory. El cmdlet que permite extender el esquema de Active Directory es **Install-CsAdServerSchema**.


> [!NOTE]
> El cmdlet de preparación del esquema ( <STRONG>Install-CsAdServerSchema</STRONG>) debe tener acceso al maestro de esquema, que requiere que el servicio del Registro remoto esté en ejecución y que la clave del Registro remoto esté habilitada. Si el servicio del Registro remoto no se puede habilitar en el maestro de esquema, puede ejecutar el cmdlet de forma local en el maestro de esquema. Para más información sobre el acceso remoto al Registro, consulte el artículo 314837 de Microsoft Knowledge Base: "Cómo administrar el acceso remoto al Registro" en <A href="http://go.microsoft.com/fwlink/?linkid=125769%26clcid=0xc0a">http://go.microsoft.com/fwlink/?linkid=125769&amp;clcid=0xC0A</A>.



Una vez preparado el esquema, compruebe manualmente que la división del esquema se haya replicado antes de continuar con la preparación del bosque. Para obtener información detallada, consulte [Comprobar la replicación de esquemas de Active Directory en Lync Server 2013](lync-server-2013-verifying-schema-replication.md).

## Para preparar el esquema del bosque actual durante la instalación

1.  Inicie sesión en un servidor del bosque como miembro del grupo Administradores de esquema y con derechos de administrador en el maestro de esquema.

2.  Desde el medio o la carpeta de instalación de Lync Server 2013, ejecute Setup.exe para iniciar el Asistente para la implementación.

3.  Si se le pide que instale el Paquete redistribuible de Microsoft Visual C++, haga clic en **Sí** .

4.  El cuadro de diálogo de instalación de Lync Server 2013 le pide una ubicación para instalar los archivos de Lync Server. Elija la ubicación predeterminada o haga clic en **Examinar** para buscar la ubicación que prefiera y, a continuación, en **Instalar** .

5.  En la página Contrato de licencia, active **Acepto los términos del contrato de licencia** y haga clic en **Aceptar** .

6.  El instalador instala los componentes principales de Lync Server.

7.  Cuando el Asistente para la implementación esté listo, haga clic en **Preparar Active Directory** y espere hasta que se determine el estado de implementación.

8.  En **Paso 1: Preparar el esquema** , haga clic en **Ejecutar** .

9.  En la página **Preparar el esquema** , haga clic en **Siguiente** .

10. En la página **Ejecución de comandos** , busque **Estado de la tarea: completado** y, a continuación, haga clic en **Ver registro** .

11. En la columna **Acción** , expanda **Preparar el esquema** , compruebe que el resultado de la ejecución sea **\<Correcto\>** al final de cada tarea para asegurarse de que la preparación del esquema finalizó correctamente, cierre el registro y, a continuación, haga clic en **Finalizar** .

12. Espere a que la replicación de Active Directory finalice o fuerce la replicación.

13. Compruebe manualmente que los cambios realizados en el esquema se hayan replicado al resto de controladores de dominio. Para obtener información detallada, consulte [Comprobar la replicación de esquemas de Active Directory en Lync Server 2013](lync-server-2013-verifying-schema-replication.md).

## Para usar cmdlets en la preparación del esquema del bosque actual

1.  Inicie sesión en un equipo del bosque como miembro del grupo Administradores de esquema y con derechos de administrador en el maestro de esquema.

2.  Instale los componentes principales de Lync Server de la siguiente manera:
    
    1.  En el medio o la carpeta de instalación de Lync Server 2013, ejecute Setup.exe para iniciar la Asistente para la implementación de Lync Server.
    
    2.  Si se le pide que instale el Paquete redistribuible de Microsoft Visual C++, haga clic en **Sí** .
    
    3.  El cuadro de diálogo de instalación de Lync Server 2013 le pide una ubicación para instalar los archivos de Lync Server. Elija la ubicación predeterminada o haga clic en **Examinar** para buscar la ubicación que prefiera y, a continuación, en **Instalar** .
    
    4.  En la página Contrato de licencia, active **Acepto los términos del contrato de licencia** y haga clic en **Aceptar** . El instalador instala los componentes principales de Lync Server 2013.

3.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Shell de administración de Lync Server**.

4.  Ejecute:
    
        Install-CsAdServerSchema [-Ldf <directory where the .ldf file is located>] 
    
    Si no especifica el parámetro Ldf, el valor predeterminado será la ruta de instalación de Lync Server 2013 que se lee en el registro.
    
    Por ejemplo:
    
        Install-CsAdServerSchema -Ldf "C:\Program Files\Microsoft Lync Server 2013\Deployment\Setup"

5.  Use el siguiente cmdlet para comprobar que la preparación del esquema ha finalizado correctamente.
    
        Get-CsAdServerSchema 
    
    Este cmdlet devuelve un valor de **SCHEMA\_VERSION\_STATE\_CURRENT** si la preparación del esquema se ha realizado correctamente.

6.  Espere a que la replicación de Active Directory finalice o fuerce la replicación.

7.  Compruebe manualmente que los cambios realizados en el esquema se hayan replicado al resto de controladores de dominio. Para obtener información detallada, consulte [Comprobar la replicación de esquemas de Active Directory en Lync Server 2013](lync-server-2013-verifying-schema-replication.md).

## Vea también

#### Tareas

[Comprobar la replicación de esquemas de Active Directory en Lync Server 2013](lync-server-2013-verifying-schema-replication.md)  

#### Conceptos

[Preparación del esquema de Active Directory en Lync Server 2013](lync-server-2013-preparing-the-active-directory-schema.md)

