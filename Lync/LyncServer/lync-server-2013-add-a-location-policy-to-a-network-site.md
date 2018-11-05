---
title: Agregar una directiva de ubicación a un sitio de red en Lync Server 2013
TOCTitle: Agregar una directiva de ubicación a un sitio de red en Lync Server 2013
ms:assetid: 43bfab8a-3d6b-4ca4-8425-879fd910502e
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg425936(v=OCS.15)
ms:contentKeyID: 48275119
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Agregar una directiva de ubicación a un sitio de red en Lync Server 2013

 

_**Última modificación del tema:** 2013-02-24_

En los siguientes ejemplos se muestra cómo agregar a un sitio de red existente la directiva de ubicación **Redmond** definida en [Crear directivas de ubicación en Lync Server 2013](lync-server-2013-create-location-policies.md) y cómo crear un sitio de red nuevo que use la directiva de ubicación **Redmond**.

Para obtener información detallada sobre cómo trabajar con sitios de red, consulte la documentación del Shell de administración de Lync Server relativa a los siguientes cmdlet:

  - **New-CsNetworkSite**

  - **Get-CsNetworkSite**

  - **Set-CsNetworkSite**

  - **Remove-CsNetworkSite**

## Para asignar una directiva de ubicación a un sitio de red existente

1.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Shell de administración de Lync Server**.

2.  Ejecute los siguientes cmdlets para modificar un sitio de red existente.
    
    Asigne la directiva de ubicación con la etiqueta **Redmond** a un sitio de red existente denominado **Redmond**.
    
        Set-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"

## Para asignar una directiva de ubicación a un nuevo sitio de red

1.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Shell de administración de Lync Server**.

2.  Ejecute el siguiente cmdlet para crear un sitio de red.
    
    Cree el sitio de red en la región de red y asígnele la directiva de ubicación con la etiqueta **Redmond**.
    
        New-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"

