---
title: Configuración de vínculos de regiones de red
TOCTitle: Configuración de vínculos de regiones de red
ms:assetid: 952bc93e-e6aa-4539-85c7-2b15f14eb382
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg182551(v=OCS.15)
ms:contentKeyID: 48276063
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuración de vínculos de regiones de red

 

_**Última modificación del tema:** 2012-11-01_

Puede configurar vínculos entre dos regiones de red como parte del control de admisión de llamadas. Las regiones de una red se vinculan mediante conexiones de red de área extensa (WAN) físicas. Puede usar Panel de control de Lync Server para definir un vínculo entre dos regiones de red y establecer las limitaciones de ancho de banda en conexiones de audio y vídeo entre estas regiones. Para obtener más información sobre cómo eliminar un vínculo de regiones de red existente, consulte [Eliminación de vínculos de región de red](lync-server-2013-deleting-network-region-links.md).

## Para crear un vínculo de región de red

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Configuración de red** y, a continuación, en **Vínculo regional**.

4.  En la página **Vínculo regional**, haga clic en **Nuevo**.

5.  En **Vínculo regional nuevo**, escriba un valor en el campo **Nombre**.
    

    > [!NOTE]
    > Este valor debe ser único en la implementación de Lync Server 2013.



6.  En la lista desplegable **Región de red nº 1**, seleccione una de las dos regiones que se van a vincular.

7.  En la lista desplegable **Región de red nº 2**, seleccione la otra región que se va a vincular. Es preciso que esta región sea distinta a la región que se seleccionó en Región de red nº 1.

8.  (Opcional) Si desea establecer limitaciones de ancho de banda en llamadas de audio o vídeo entre estas regiones, seleccione un perfil de directiva de ancho de banda en la lista desplegable **Directiva de ancho de banda**.

9.  Haga clic en **Confirmar**.

## Para modificar un vínculo de región de red

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Configuración de red** y, a continuación, en **Vínculo regional**.

4.  En la página **Vínculo regional**, haga clic en el vínculo regional que desea modificar.

5.  En el menú **Editar**, haga clic en **Mostrar detalles**.

6.  En **Editar vínculo regional** puede modificar las regiones que están vinculadas o el perfil de directiva de ancho de banda para este vínculo.

7.  Haga clic en **Confirmar**.

## Vea también

#### Tareas

[Eliminación de vínculos de región de red](lync-server-2013-deleting-network-region-links.md)  

#### Otros recursos

[New-CsNetworkRegionLink](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsNetworkRegionLink)  
[Set-CsNetworkRegionLink](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsNetworkRegionLink)  
[Remove-CsNetworkRegionLink](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsNetworkRegionLink)  
[Get-CsNetworkRegionLink](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsNetworkRegionLink)
