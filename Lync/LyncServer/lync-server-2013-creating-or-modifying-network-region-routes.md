---
title: Creación o modificación de rutas de regiones de red
TOCTitle: Creación o modificación de rutas de regiones de red
ms:assetid: 76993daa-76c2-4cec-8363-de8aebef0145
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg521016(v=OCS.15)
ms:contentKeyID: 48275707
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Creación o modificación de rutas de regiones de red

 

_**Última modificación del tema:** 2012-10-08_

Todas las regiones dentro de una configuración del servicio de control de admisión de llamadas (CAC) deben poder obtener acceso de alguna forma a todas las demás regiones. Mientras que los vínculos regionales establecen las limitaciones de ancho de banda de las conexiones entre regiones y también representan los vínculos físicos, las rutas determinan la ruta de acceso vinculada que atravesará la conexión de una región a otra. Puede usar el Panel de control de Lync Server para configurar rutas regionales de red. Desde el Panel de control de Lync Server, puede crear, modificar o eliminar una ruta regional de red. Consulte este tema para crear o modificar una ruta regional de red. Para más información sobre cómo eliminar rutas de una región de red existente, vea [Eliminación de rutas de región de red existentes](lync-server-2013-deleting-existing-network-region-routes.md).

## Para crear una ruta regional de red

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Configuración de red** y, a continuación, en **Ruta regional**.

4.  En la página **Ruta regional**, haga clic en **Nueva**.

5.  En **Nueva ruta regional**, escriba un valor en el campo **Nombre**.
    

    > [!NOTE]
    > Este valor debe ser único en la implementación de Microsoft Lync Server 2013.



6.  En la lista desplegable **Región de red nº 1**, seleccione una de las dos regiones que se conectan mediante esta ruta.

7.  En la lista desplegable **Región de red nº 2**, seleccione la otra región para esta ruta. Es preciso que esta región sea distinta de la que se seleccionó en la Región de red nº 1.

8.  Use el cuadro de lista **Vínculos de región de red** para agregar vínculos de red a la ruta. Haga clic en el botón **Agregar** para mostrar la página **Vínculo regional**. Haga clic en un vínculo regional para agregarlo a esta ruta y, a continuación, haga clic en **Aceptar**.
    

    > [!NOTE]
    > Haga clic otra vez en el botón <STRONG>Agregar</STRONG> para añadir más vínculos, o seleccione un vínculo y haga clic en <STRONG>Eliminar</STRONG> para eliminarlo.



9.  Haga clic en **Confirmar**.

## Para modificar una ruta regional de red

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Configuración de red** y, a continuación, en **Ruta regional**.

4.  En la página **Ruta regional**, haga clic en la ruta regional que desea modificar.

5.  En el menú **Editar**, haga clic en **Mostrar detalles**.

6.  En **Editar ruta regional**, puede modificar las regiones agregadas a esta ruta y los vínculos regionales asociados a la misma.

7.  Haga clic en **Confirmar**.

## Vea también

#### Tareas

[Eliminación de rutas de región de red existentes](lync-server-2013-deleting-existing-network-region-routes.md)

