---
title: Conectar un grupo de servidores piloto a servidores perimetrales heredados
TOCTitle: Conectar un grupo de servidores piloto a servidores perimetrales heredados
ms:assetid: c3b67220-5705-47f6-852e-415204f3626c
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ721875(v=OCS.15)
ms:contentKeyID: 49889669
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Conectar un grupo de servidores piloto a servidores perimetrales heredados

 

_**Última modificación del tema:** 2012-09-29_

Después de implementar Lync Server 2013, debe configurar una ruta de federación para el sitio. Si desea usar la ruta federada de Lync Server 2010, configure Lync Server 2013 para que use dicha ruta.

Para que el sitio de Lync Server 2013 use el Director y el servidor perimetraesl de la implementación de Lync Server 2010, use el Generador de topologías para asociar el grupo de servidores perimetrales heredado.

## Para asociar el grupo de servidores perimetrales heredado con el Generador de topologías:

1.  Abrir **Generador de topologías**.

2.  Seleccione el sitio, que se encuentra justo debajo del nodo **Lync Server**.

3.  En el menú **Acciones** , haga clic en **Editar propiedades** .

4.  En el panel izquierdo, seleccione **Ruta de federación**.

5.  En **Asignación de ruta de federación del sitio** , seleccione **Habilitar federación SIP** y el Director de Lync Server 2010, o el servidor perimetral de Lync Server 2010 si no aparece ningún Director en la lista.
    
    ![Editar propiedades, página Ruta de federación](images/JJ721875.5f1d04c3-c724-426d-b27d-3fe89c6c5cfb(OCS.15).jpg "Editar propiedades, página Ruta de federación")  

6.  Haga clic en **Aceptar** para cerrar la página **Editar propiedades** .

7.  En el Generador de topologías, bajo el nodo de Lync Server 2013, navegue hasta **Servidor Standard Edition** o **Grupos de servidores front-end Enterprise Edition** , haga clic con el botón secundario en el grupo y haga clic en **Editar propiedades** .

8.  En **Asociaciones** , active la casilla situada junto a **Grupo de servidores perimetrales asociados (para componentes multimedia)** .

9.  En la lista, seleccione el servidor perimetral heredado.
    
    ![Cuadro de diálogo Editar propiedades, selección de servidores perimetrales heredados](images/JJ721875.feae8156-540e-4804-bb0a-2b5736ec2900(OCS.15).jpg "Cuadro de diálogo Editar propiedades, selección de servidores perimetrales heredados")  

10. Haga clic en **Aceptar** para cerrar la página **Editar propiedades** .

11. En el **Generador de topologías** , seleccione el nodo superior, **Lync Server**.

12. En el menú **Acción** , haga clic en **Publicar topología** y en **Siguiente** .

13. Cuando el **asistente para publicación** haya finalizado, haga clic en **Finalizar** .

