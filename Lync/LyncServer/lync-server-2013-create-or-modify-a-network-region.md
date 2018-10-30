---
title: 'Lync Server 2013: Crear o modificar una región de red'
TOCTitle: Crear o modificar una región de red
ms:assetid: bf7a3dc4-71a2-4559-a547-d90305d4f904
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg412933(v=OCS.15)
ms:contentKeyID: 48276532
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Crear o modificar una región de red en Lync Server 2013

 

_**Última modificación del tema:** 2012-10-19_

Las *regiones de red* son concentradores de red o redes troncales que se usan en la configuración del control de admisión de llamadas, E9-1-1 y del desvío de medios. Siga estos procedimientos para crear o modificar regiones de red. Por ejemplo, si ha creado regiones de red para una característica de Voz, no necesitará crear nuevas regiones de red puesto que otras características de Voz avanzadas de la versión Enterprise usarán esas mismas regiones. Sin embargo, sí que es posible que deba modificar una región de red existente para aplicar una configuración específica de una característica. Por ejemplo, si ha creado regiones de red para E9-1-1 (que no requieren ningún sitio centralizado) y, a continuación, implementa el control de admisión de llamadas, deberá modificar las definiciones de región de red para especificar un sitio centralizado. Para más detalles, consulte [Configurar regiones de red para el control de admisión de llamadas en Lync Server 2013](lync-server-2013-configure-network-regions-for-cac.md).


> [!NOTE]
> Cualquier requisito específico de la característica para las definiciones de región de red está documentado en los temas sobre implementación para la característica.



Para más información sobre cómo trabajar con regiones de red, consulte la documentación del Shell de administración de Lync Server para los cmdlets siguientes:

  - [New-CsNetworkRegion](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsNetworkRegion)

  - [Get-CsNetworkRegion](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsNetworkRegionLink)

  - [Set-CsNetworkRegion](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsNetworkRegion)

  - [Remove-CsNetworkRegion](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsNetworkRegion)

## Crear una región de red

Cree una región de red que sirva para el control de admisión de llamadas, E9-1-1 o el desvío de medios.

## Para crear una región de red con el Shell de administración de Lync Server

1.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Shell de administración de Lync Server**.

2.  Ejecute el cmdlet New-CsNetworkRegion para crear regiones de red:
    
        New-CsNetworkRegion -Identity <String> -CentralSite <String>
    
    Por ejemplo:
    
        New-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "All North America Locations"
    
    En este ejemplo, ha creado una región de red denominada “NorthAmerica” que está asociada a un sitio central con identificador de sitio CHICAGO.

3.  Para terminar de crear regiones de red para la topología, repita el paso 2 con parámetros para cada región de red.

## Para crear una región de red mediante el Panel de control de Lync Server

1.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

2.  En la barra de navegación izquierda, haga clic en **Configuración de red** .

3.  Haga clic en **Región**

4.  Haga clic en **Nuevo** .

5.  En la página **Región nueva** , haga clic en **Nombre** y escriba un nombre para la región de red.

6.  Haga clic en **Sitio central** y haga clic en un sitio central de la lista.

7.  Si lo desea, también puede hacer clic en **Descripción** y aportar más información que describa este sitio de red.

8.  Haga clic en **Confirmar** .

9.  Para terminar de crear regiones de red para la topología, repita los pasos del 4 al 8 con parámetros para otras regiones.

## Modificar una región de red

Modifique la configuración de una región de red existente para adaptar los cambios en la información básica de región o los cambios que requiere una nueva característica.

## Para modificar una región de red con el Shell de administración de Lync Server

1.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Shell de administración de Lync Server**.

2.  Ejecute el cmdlet Set-CsNetworkRegion para modificar una región de red existente:
    
        Set-CsNetworkRegion -Identity <String> -CentralSite <String>
    
    Por ejemplo:
    
        Set-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "North American Region"
    
    En este ejemplo, ha modificado una región de red existente denominada “NorthAmerica” (creada mediante los procedimientos descritos anteriormente en este tema) cambiando la descripción. Si ya existía una descripción para la región “NorthAmerica”, este comando la sobrescribirá con este valor; si no se había definido ninguna descripción, el comando la definirá.

3.  Para modificar otras regiones de red, repita el paso 2 con parámetros para otras regiones.

## Para modificar una región de red mediante el Panel de control de Lync Server

1.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

2.  En la barra de navegación izquierda, haga clic en **Configuración de red** .

3.  Haga clic en el botón de navegación **Región** .

4.  En la tabla, haga clic en la región de red que desee modificar.

5.  Haga clic en **Editar** y, a continuación, en **Mostrar detalles…** .

6.  En la página **Editar región** , modifique los valores de la configuración de esta región de red, según corresponda.

7.  Haga clic en **Confirmar** .

8.  Para terminar de modificar regiones de red, repita los pasos del 4 al 7 con parámetros para otras regiones.

