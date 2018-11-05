---
title: "Conf de Lync Server 2013 pour le fonctionnement avec Office Web Apps Server"
TOCTitle: "Conf de Lync Server 2013 pour le fonctionnement avec Office Web Apps Server"
ms:assetid: 6231e519-9010-4ff9-b5a6-b5859c2b3e11
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ204944(v=OCS.15)
ms:contentKeyID: 48275472
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuración de Lync Server 2013 para funcionar con Office Web Apps Server

 

_**Última modificación del tema:** 2013-04-22_

Office Web Apps Server debe estar implementado y configurado para poder configurar Lync Server 2013 para que use dicho servidor. Consulte la **guía para implementar Office Web Apps y Office Web Apps Server** para obtener información detallada sobre cómo instalar y configurar un único Office Web Apps Server o toda una granja de Office Web Apps Server, si precisa de una alta disponibilidad.

Tras instalar Office Web Apps Server y configurar la granja de servidores web correctamente, es necesario configurar Lync Server para que se comunique con el nuevo servidor; para ello, hay que agregar la dirección URL de descubrimiento de Office Web Apps Server a la topología de Lync Server. Realice lo siguiente para agregar Office Web Apps Server a su topología:

1.  Haga clic sucesivamente en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y **Generador de topologías de Lync Server**.

2.  En el cuadro de diálogo **Generador de topologías**, seleccione **Descargar topología de la implementación existente** y haga clic en **Aceptar**.

3.  En el cuadro de diálogo **Guardar topología como**, escriba el nombre del documento de topología (por ejemplo, **PreWebAppsServerTopology**) en el cuadro **Nombre de archivo** y, después, haga clic en **Guardar**. Esta topología se podrá recuperar y volver a publicar más adelante si detecta algún problema en ella.

4.  En el Generador de topologías, expanda **Lync Server 2013**, el nombre de su sitio y **Grupos de servidores front-end Enterprise Edition**, haga clic con el botón secundario en uno de los grupos de servidores y, luego, haga clic en **Editar propiedades**.

5.  En la pestaña **General** del cuadro de diálogo **Editar propiedades**, busque el encabezado **Asociar Office Web Apps Server** y haga clic en **Nuevo** (o seleccione un Office Web Apps Server de la lista desplegable).

6.  En el cuadro de diálogo **Definir nuevo Office Web Apps Server**, escriba el nombre de dominio completo (FQDN) del equipo de Office Web Apps Server en el cuadro **FQDN de Office Web Apps Server**; al hacerlo, la dirección URL de descubrimiento de Office Web Apps Server deberá aparecer automáticamente en el cuadro **Dirección URL de descubrimiento de Office Web Apps Server**.
    
    En caso de que Office Web Apps Server esté instalado localmente y en la misma zona de red que Lync Server 2013, la opción **Office Web Apps Server se implementa en una red externa (esto es, perimetral/Internet)** no debe estar seleccionada.
    
    Si Office Web Apps Server está implementado fuera del firewall interno, seleccione la opción **Office Web Apps Server se implementa en una red externa (esto es, perimetral/Internet)**.

7.  Haga clic en **Aceptar** en el cuadro de diálogo **Definir nuevo Office Web Apps Server** y, después, haga clic en **Aceptar** en el cuadro de diálogo **Editar propiedades**. La dirección URL de descubrimiento de Office Web Apps aparecerá como una de las asociaciones del grupo de servidores.

Este proceso deberá repetirse con cada grupo de servidores que tenga que asociarse a Office Web Apps Server.

Una vez que haya agregado la dirección URL de descubrimiento a la topología, deberá publicar dicha topología actualizada. Para ello, haga lo siguiente en el Generador de topologías:

1.  Haga clic en **Acción** y, después, en **Publicar topología**.

2.  En la página **Publicar la topología** del asistente Publicar topología, haga clic en **Siguiente**.

3.  En la página **Asistente para publicación completado**, haga clic en **Finalizar**.

4.  Cierre el Generador de topologías.

