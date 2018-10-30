---
title: Eliminar la asociación de servidores de archivado
TOCTitle: Eliminar la asociación de servidores de archivado
ms:assetid: dabac157-71ee-4afe-b0b6-4a083d165ffb
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ721903(v=OCS.15)
ms:contentKeyID: 49889759
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Eliminar la asociación de servidores de archivado

 

_**Última modificación del tema:** 2012-10-04_

Para quitar una Servidor de archivado, debe cambiar o borrar la dependencia en el Grupo de servidores front-end, la Servidor front-end, el Aplicación de sucursal con funciones de supervivencia y la Servidor de sucursal con funciones de supervivencia asociados. Edite las propiedades del Grupo de servidores front-end, la Servidor front-end, el Aplicación de sucursal con funciones de supervivencia y la Servidor de sucursal con funciones de supervivencia para quitar la dependencia. Tras borrar la dependencia y eliminar el servidor de Generador de topologías, se le notifica que también se eliminará el objeto de almacén de base de datos asociado de Generador de topologías.

## Para quitar la asociación del servidor de archivado

1.  Abra el servidor front-end de Lync Server 2013, abra el Generador de topologías.

2.  Desplácese hasta el nodo de Lync Server 2010.

3.  En Generador de topologías, despliegue **Grupos de servidores front-end Enterprise Edition**, **Servidores front-end Standard Edition** o **Sitios de sucursal**, dependiendo de dónde se haya definido la Servidor de archivado.

4.  Si tiene Servidor de sucursal con funciones de supervivencia asociado, expanda **Sitios de sucursal**, expanda el nombre del sitio de sucursal y después **Aplicaciones de sucursal con funciones de supervivencia**.
    

    > [!NOTE]
    > <STRONG>Aplicaciones de sucursal con funciones de supervivencia</STRONG> en la interfaz de usuario se aplica a Servidor de sucursal con funciones de supervivencia y a Aplicación de sucursal con funciones de supervivencia.



5.  Haga clic con el botón secundario del mouse en el grupo de servidores, servidor o dispositivo asociados con la Servidor de archivado y después haga clic en **Editar propiedades**.

6.  En **Editar propiedades**, en **General**, en **Asociaciones**, desactive la casilla **Asociar servidor de archivado** y después haga clic en **Aceptar**.

7.  Repita el paso anterior con cualquier otro grupo de servidores, servidor o dispositivo asociados con la Servidor de archivado que quiera quitar.

8.  Haga clic con el botón secundario del mouse en Servidor de archivado y después haga clic en **Eliminar**.

9.  En **Eliminar almacenes dependientes**, haga clic en **Aceptar**.

10. Publique la topología, compruebe el estado de replicación y después ejecute el Asistente para la implementación de Lync Server según sea necesario.

