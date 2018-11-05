---
title: Restaurar, supervisar o archivar datos
TOCTitle: Restaurar, supervisar o archivar datos
ms:assetid: 60118526-13bb-4b03-803e-6ffae219d436
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Hh202175(v=OCS.15)
ms:contentKeyID: 52061690
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Restaurar, supervisar o archivar datos

 

_**Última modificación del tema:** 2013-02-18_

La restauración de los datos de archivado y supervisión no es necesaria para que Lync Server vuelva a funcionar correctamente después de un error. Sin embargo, si los datos de archivado y supervisión son esenciales para su organización, se recomienda restaurarlos después de volver a crear las bases de datos.

El siguiente procedimiento describe cómo usar SQL Server Management Studio para restaurar datos de archivado o supervisión.

## Para restaurar datos de archivado o supervisión de un archivo de copia de seguridad

1.  Inicie sesión en el servidor que va a restaurar como miembro del grupo Administradores en el equipo local o un grupo con derechos de usuario equivalentes.

2.  Para abrir SQL Server Management Studio, haga clic en **Inicio**, en **Todos los programas**, en **Microsoft SQL Server 2012** o **Microsoft SQL Server 2008 R2** y, a continuación, en **SQL Server Management Studio**.

3.  En **Conectar al servidor**, conéctese a la instancia de SQL Server indicando al menos el nombre del servidor y la información de autenticación.

4.  En **Explorador de objetos**, haga clic con el botón secundario del mouse en **Bases de datos** y, a continuación, haga clic en **Restaurar base de datos**.

5.  En **Seleccionar una página**, haga clic en **General** y, a continuación, en **Base de datos de destino**, seleccione el nombre de la base de datos de la siguiente forma:
    
      - Para un Base de datos de archivado, seleccione **LcsLog**.
    
      - Para una base de datos de registros de detalles de las llamadas (CDR), seleccione **LcsCDR**.
    
      - Para una base de datos de calidad de la experiencia (QoE), seleccione **QoEMetrics**.

6.  Haga clic en **Dispositivos de origen**.

7.  En **Seleccionar los conjuntos de copia de seguridad que se van a restaurar**, haga clic en el archivo de copia de seguridad y, a continuación, haga clic en **Restaurar**.

8.  En **Seleccionar una página**, haga clic en **Opciones**, compruebe que la ruta del archivo de datos y la ruta del registro se encuentran en la carpeta correcta y, a continuación, haga clic en **Aceptar**.

## Para asegurarse de que las listas de control de acceso (ACL) son correctas

1.  Expanda **Bases de datos**, expanda la base de datos de archivado o supervisión, expanda **Seguridad** y, a continuación, expanda **Usuarios**.

2.  Compruebe que el grupo de dominio RTCComponentUniversalServices existe como usuario.

3.  Si RTCComponentUniversalServices no existe en **Usuarios**, siga estos pasos:
    
    1.  Haga clic con el botón secundario del mouse en **Usuarios** y, a continuación, haga clic en **Nuevo usuario**.
    
    2.  En **Nombre de inicio de sesión**, escriba el nombre del grupo que falta, RTCComponentUniversalServices.
    
    3.  En **Miembros del rol de base de datos**, seleccione el permiso **ServerRole** y, a continuación, haga clic en **Aceptar**.
    

    > [!NOTE]
    > No será necesario reiniciar el servicio de archivado o supervisión.


