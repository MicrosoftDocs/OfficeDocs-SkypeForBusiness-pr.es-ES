---
title: Conectar el grupo piloto a servidores perimetrales heredados
TOCTitle: Conectar el grupo piloto a servidores perimetrales heredados
ms:assetid: 9ed13c41-f3ab-4e1d-beb6-a00152c541e2
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ205136(v=OCS.15)
ms:contentKeyID: 48276155
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Conectar el grupo piloto a servidores perimetrales heredados

 

_**Última modificación del tema:** 2012-10-02_

Tras implementar Lync Server 2013, no se ha configurado una ruta de federación para este sitio. Para usar la ruta federada que está usando Office Communications Server 2007 R2, Lync Server 2013 debe estar configurado para usar esta ruta.

Para habilitar el sitio de Lync Server 2013 para que use el Director y el servidor perimetral del BackCompatSite, use el Generador de topologías para asociar el grupo perimetral heredado.

## Para asociar el grupo de servidores perimetrales heredado con el Generador de topologías:

1.  Abra la topología del grupo piloto en Topology Builder.

2.  Seleccione su sitio de Lync Server 2013.

3.  En el menú **Acción** , haga clic en **Editar propiedades** .

4.  En **Asignación de ruta de federación del sitio**, seleccione **Habilitar federación SIP** y el Director de Office Communications Server 2007 R2 o el servidor perimetral de Office Communications Server 2007 R2 si no aparece ningún Director en la lista.
    
    ![Cuadro de diálogo Editar propiedades, página Ruta de federación](images/JJ205136.bc13014b-3578-4d9e-9ff7-bdd09130b676(OCS.15).jpg "Cuadro de diálogo Editar propiedades, página Ruta de federación")  

5.  Haga clic en **Aceptar** para cerrar la página **Editar propiedades** .

6.  En el Generador de topologías, bajo el nodo de Lync Server 2013, navegue hasta **Servidor Standard Edition** o **Grupos de servidores front-end Enterprise Edition** , haga clic con el botón secundario en el grupo y haga clic en **Editar propiedades** .

7.  En **Asociaciones** , active la casilla situada junto a **Grupo de servidores perimetrales asociados (para componentes multimedia)** .

8.  En la lista, seleccione la interfaz del servidor perimetral de la BackCompatSite.
    
    ![Cuadro de diálogo Editar propiedades, página General](images/JJ205136.75045212-03ca-4b82-8337-5dacb487094f(OCS.15).jpg "Cuadro de diálogo Editar propiedades, página General")  

9.  Haga clic en **Aceptar** para cerrar la página **Editar propiedades** .

10. En el **Generador de topologías**, seleccione el nodo superior, **Lync Server** .

11. En el menú **Acción** , haga clic en **Publicar topología** y en **Siguiente** .

12. Cuando el **asistente para publicación** haya finalizado, haga clic en **Finalizar** .

