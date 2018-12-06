---
title: Quitar BackCompatSite
TOCTitle: Quitar BackCompatSite
ms:assetid: 039650e3-541b-45c2-a682-c4fa08423118
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ204637(v=OCS.15)
ms:contentKeyID: 48274272
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Quitar BackCompatSite

 

_**Última modificación del tema:** 2012-09-28_

Una vez que se desactivaron todos los grupos de servidores y se desinstalaron todos los servidores perimetrales, ejecute el asistente para la combinación del Generador de topologías a fin de quitar **BackCompatSite**.

## Para quitar el sitio BackCompat del Generador de topologías

1.  Abra una implementación existente del Generador de topologías.

2.  En el menú **Acción**, haga clic en **Combinar topología de 2007**.

3.  Haga clic en **Siguiente** para continuar.

4.  En la página **Especificar servidor perimetral heredado**, asegúrese de que la lista de servidores perimetrales esté vacía. Si no lo está, utilice el botón **Quitar** para quitar todos los servidores perimetrales heredados y, a continuación, haga clic en **Siguiente**.
    
    ![Asistente de topología de combinación, página Especificar configuración perimetral](images/JJ204637.fb35a59a-711e-4259-b177-7311df1fed3c(OCS.15).jpg "Asistente de topología de combinación, página Especificar configuración perimetral")  

5.  En la página **Especificar puerto SIP interno**, haga clic en **Siguiente**.

6.  En la página **Resumen**, haga clic en **Siguiente** para empezar a combinar las topologías con el fin de quitar el sitio heredado.

7.  En la columna **Estado**, compruebe que el valor sea **Correcto** y haga clic en **Finalizar** para cerrar el asistente.

8.  En el panel izquierdo de Topology Builder, expanda BackCompatSite y compruebe que no se muestre ningún servidor.

9.  Haga clic con el botón secundario en **BackCompatSite** y, a continuación, haga clic en **Eliminar**.

10. En el **Generador de topologías**, seleccione el primer nodo **Lync Server**.

11. En el menú **Acciones**, seleccione **Publicar topología** y luego haga clic en **Siguiente**.

12. Cuando el **Asistente para publicación** haya finalizado, haga clic en **Finalizar** para cerrar el asistente.

