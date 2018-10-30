---
title: Creación o modificación de sitios de red
TOCTitle: Creación o modificación de sitios de red
ms:assetid: 358aa08a-c5bc-45fc-8017-19e6202f88c5
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg520975(v=OCS.15)
ms:contentKeyID: 48274901
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Creación o modificación de sitios de red

 

_**Última modificación del tema:** 2012-10-08_

Los sitios de red son las oficinas o ubicaciones configuradas dentro de cada región de una implementación de Enhanced 9-1-1 o control de admisión de llamadas (CAC). Puede usar Panel de control de Microsoft Lync Server 2013 para configurar sitios y asociarlos con regiones. Por ejemplo, una región de red para Norteamérica se podría asociar con sitios de red como Chicago, Redmond y Vancouver. Debe crearse un sitio de red CAC para cada sitio de una organización, incluso aunque no tenga limitaciones de ancho de banda. En Panel de control de Lync Server, puede crear, modificar y eliminar sitios de red. Utilice los procedimientos siguientes para crear o modificar un sitio de red. Para obtener más detalles sobre la eliminación de un sitio de red existente, vea [Eliminación de un sitio de red existente](lync-server-2013-deleting-an-existing-network-site.md).

## Para crear un sitio de red

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Configuración de red** y, a continuación, en **Sitio**.

4.  En la página **Sitio**, haga clic en **Nuevo**.

5.  En **Sitio nuevo**, escriba un nombre para este sitio en el campo **Nombre**.
    

    > [!NOTE]
    > Los nombres de sitios deben ser únicos en la implementación de Lync Server 2013.



6.  En la lista desplegable **Región**, seleccione una región de red para asociarla con este sitio.

7.  (Opcional) Si desea definir limitaciones de ancho de banda en las llamadas de audio o vídeo para este sitio, seleccione el perfil de directiva de ancho de banda con la configuración adecuada en la lista desplegable **Directiva de ancho de banda**.
    

    > [!NOTE]
    > Puede ver la información detallada de los perfiles de directivas de ancho de banda disponibles o crear uno nuevo en la página <STRONG>Perfil de directiva</STRONG> del grupo <STRONG>Configuración de red</STRONG>. Para obtener información detallada, consulte <A href="lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md">Creación o modificación de perfiles de directivas de ancho de banda</A>.



8.  (Opcional) Si desea proporcionar parámetros de ubicación para este sitio, seleccione una directiva de ubicación de la lista desplegable **Directiva de ubicación**.
    

    > [!NOTE]
    > La directiva de ubicación asigna al sitio un Enhanced 9-1-1 (E9-1-1) específico y parámetros de ubicación de cliente. Puede ver la información detallada de las directivas de ubicación disponibles o crear una nueva desde la página <STRONG>Directiva de ubicación</STRONG> del grupo <STRONG>Configuración de red</STRONG>. Para obtener más información, consulte <A href="lync-server-2013-viewing-location-policy-information.md">Visualización de la información de una directiva de ubicación</A>.



9.  (Opcional) Escriba un valor en el campo **Descripción** para proporcionar más información acerca de este sitio más allá de lo que se pueda deducir de su nombre.

10. Haga clic en **Confirmar**.
    

    > [!NOTE]
    > No use la tabla <STRONG>Subredes asociadas</STRONG> al crear un sitio de red nuevo. Al crear o modificar la subred, asocie una subred con un sitio. Para obtener información detallada, consulte <A href="lync-server-2013-create-or-modify-network-subnets.md">Crear o modificar subredes de red</A>.



## Para modificar un sitio de red

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Configuración de red** y, a continuación, en **Sitio**.

4.  En la página **Sitio**, haga clic en el sitio que desea modificar.

5.  En el menú **Editar**, haga clic en **Mostrar detalles**.

6.  En la página **Editar sitio**, puede modificar la descripción, la región, el perfil de directiva de ancho de banda y la directiva de ubicación asociados con el sitio. Para obtener más información, consulte la sección "Para crear un sitio de red" que aparece anteriormente en este tema.

7.  Haga clic en **Confirmar**.

No es posible modificar la tabla **Subredes asociadas** de esta página. La lista de subredes asociadas solo es de referencia, por lo que debe conocer qué subredes se verán afectadas cuando modifique la configuración del sitio.

## Para eliminar un sitio de red

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Configuración de red** y, a continuación, en **Sitio**.

4.  En la página **Sitio**, haga clic en el sitio que desea eliminar.
    

    > [!NOTE]
    > Puede eliminar más de un sitio en la misma operación. Para hacerlo, pulse CTRL y seleccione varios sitios manteniendo pulsada la tecla CTRL. O bien, para seleccionar todos los sitios, haga clic en <STRONG>Seleccionar todo</STRONG> en el menú <STRONG>Editar</STRONG>.



5.  En el menú **Editar**, haga clic en **Eliminar**.

6.  Haga clic en **Aceptar**.
    
    > [!WARNING]  
    > No se puede eliminar un sitio de red si está asociado con la subred de una red. Si intenta quitar un sitio asociado a una subred, recibirá un mensaje de error. Para ver si un sitio está asociado con alguna subred, haga clic en el sitio y, a continuación, haga clic en <strong>Mostrar detalles</strong> en el menú <strong>Editar</strong>.
    


## Vea también

#### Tareas

[Eliminación de un sitio de red existente](lync-server-2013-deleting-an-existing-network-site.md)  

#### Otros recursos

[New-CsNetworkSite](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsNetworkSite)  
[Set-CsNetworkSite](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsNetworkSite)  
[Remove-CsNetworkSite](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsNetworkSite)  
[Get-CsNetworkSite](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsNetworkSite)

