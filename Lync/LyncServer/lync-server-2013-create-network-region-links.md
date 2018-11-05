---
title: Crear vínculos de regiones de red en Lync Server 2013
TOCTitle: Crear vínculos de regiones de red en Lync Server 2013
ms:assetid: f8163910-8935-475d-88a2-3aa44feb9dbe
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg413047(v=OCS.15)
ms:contentKeyID: 48277212
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Crear vínculos de regiones de red en Lync Server 2013

 

_**Última modificación del tema:** 2012-10-19_

Las regiones de una red se vinculan mediante conexiones de red WAN físicas. Un *vínculo de región de red* crea un vínculo entre dos regiones configuradas para el control de admisión de llamadas y establece los límites de ancho de banda en el tráfico de audio y vídeo entre estas regiones.

Para más información sobre cómo trabajar con vínculos de región de red, consulte la documentación del Shell de administración de Lync Server para los cmdlets siguientes:

  - [New-CsNetworkRegionLink](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsNetworkRegionLink)

  - [Get-CsNetworkRegionLink](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsNetworkRegionLink)

  - [Set-CsNetworkRegionLink](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsNetworkRegionLink)

  - [Remove-CsNetworkRegionLink](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsNetworkRegionLink)

La topología de ejemplo tiene un vínculo entre las regiones de Norteamérica y APAC, y uno entre las regiones de EMEA y APAC. Cada uno de estos vínculos tiene una restricción de ancho de banda WAN, como se explica en la tabla Información sobre el ancho de banda de vínculos de regiones de la sección [Ejemplo: Recopilación de los requisitos de la organización para el servicio de control de admisión de llamadas en Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) en la documentación sobre planeación.

## Para crear vínculos de región de red mediante el Shell de administración de Communications Server

1.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Shell de administración de Lync Server**.

2.  Ejecute el cmdlet New-CsNetworkRegionLink para crear vínculos de región de red y aplicar los correspondientes perfiles de directiva de ancho de banda. Por ejemplo, ejecute lo siguiente:
    
    ```
    New-CsNetworkRegionLink -NetworkRegionLinkID NA-EMEA-LINK -NetworkRegionID1 NorthAmerica -NetworkRegionID2 EMEA -BWPolicyProfileID 50Mb_Link
    ```
    
    ```
    New-CsNetworkRegionLink -NetworkRegionLinkID EMEA-APAC-LINK -NetworkRegionID1 EMEA -NetworkRegionID2 APAC -BWPolicyProfileID 25Mb_Link
    ```

## Para crear vínculos de región de red mediante el Panel de control de Lync Server

1.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

2.  En la barra de navegación izquierda, haga clic en **Configuración de red**.

3.  Haga clic en el botón de navegación **Vínculo de región**.

4.  Haga clic en **Nuevo**.

5.  En la página **Nuevo vínculo de región**, haga clic en **Nombre** y asigne un nombre al vínculo de región de red.

6.  Haga clic en **Región de red \#1** y, en la lista, seleccione la región de red que desea vincular con Región de red \#2.

7.  Haga clic en **Región de red \#2** y, en la lista, seleccione la región de red que desea vincular con Región de red \#1.

8.  También puede hacer clic en **Directiva de ancho de banda** y seleccionar el perfil de directiva de ancho de banda que desea aplicar al vínculo de región de red.
    

    > [!NOTE]
    > Aplique una directiva de ancho de banda únicamente si el vínculo de región de red tiene restricciones de ancho de banda y desea usar control de admisión de llamadas para controlar el tráfico de medios en ese vínculo.



9.  Haga clic en **Confirmar**.

10. Para terminar de crear vínculos de región de red para la topología, repita los pasos del 4 al 9 con parámetros para otras regiones.