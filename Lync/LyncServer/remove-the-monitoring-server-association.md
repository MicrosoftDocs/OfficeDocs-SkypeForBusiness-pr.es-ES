---
title: Eliminar la asociación de servidores de supervisión
TOCTitle: Eliminar la asociación de servidores de supervisión
ms:assetid: c45b22ae-fc06-484a-a05b-735bd1bb7448
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ721877(v=OCS.15)
ms:contentKeyID: 49889672
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Eliminar la asociación de servidores de supervisión

 

_**Última modificación del tema:** 2012-10-04_

Para quitar Servidor de supervisión, debe cambiar o borrar la dependencia en los Grupo de servidores front-end, Servidor front-end, Aplicación de sucursal con funciones de supervivencia y Servidor de sucursal con funciones de supervivencia asociados. Cambie las propiedades de Grupo de servidores front-end, Servidor front-end, Aplicación de sucursal con funciones de supervivencia y Servidor de sucursal con funciones de supervivencia para quitar la dependencia. Tras borrar la dependencia y eliminar el servidor de Generador de topologías, se le notificará que también va a eliminarse el objeto de almacenamiento de base de datos asociado de Generador de topologías.

## Para quitar la asociación del Servidor de supervisión:

1.  Abra el servidor front-end de Lync Server 2013, abra el Generador de topologías.

2.  Desplácese hasta el nodo de Lync Server 2010.

3.  En Generador de topologías, despliegue **Grupos de servidores front-end Enterprise Edition**, **Servidores front-end Standard Edition** o **Sitios de sucursal**, dependiendo de dónde se haya definido la Servidor de supervisión.

4.  Si tiene Servidor de sucursal con funciones de supervivencia asociado, expanda **Sitios de sucursal** , expanda el nombre del sitio de sucursal y después **Aplicaciones de sucursal con funciones de supervivencia** .
    

    > [!NOTE]
    > <STRONG>Aplicaciones de sucursal con funciones de supervivencia</STRONG> en la interfaz de usuario se aplica a Servidor de sucursal con funciones de supervivencia y a Aplicación de sucursal con funciones de supervivencia.



5.  Haga clic con el botón derecho en el grupo de servidores, servidor o dispositivo asociados con la Servidor de supervisión y después haga clic en **Editar propiedades**.

6.  En **Editar propiedades** , bajo **General** y **Asociaciones** , desactive la casilla **Asociar servidor de supervisión** y haga clic en **Aceptar** .

7.  Repita el paso anterior para cualquier otro grupo, servidor o dispositivo asociado con Servidor de supervisión.

8.  Haga clic con el botón derecho en Servidor de supervisión y después haga clic en **Eliminar**.

9.  En **Eliminar almacenes dependientes** , haga clic en **Aceptar** .

10. Publique la topología, compruebe el estado de la replicación y ejecute Asistente para la implementación de Lync Server según sea necesario.

