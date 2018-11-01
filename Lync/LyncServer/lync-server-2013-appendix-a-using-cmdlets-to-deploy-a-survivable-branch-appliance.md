---
title: 'Lync Server 2013: Apéndice A: Usar cmdlets para implementar una aplicación de sucursal con funciones de supervivencia'
TOCTitle: 'Apéndice A: Usar cmdlets para implementar una aplicación de sucursal con funciones de supervivencia'
ms:assetid: 796a26cf-7ec9-453b-8757-6153a6dd86c5
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398598(v=OCS.15)
ms:contentKeyID: 48275749
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Apéndice A: Usar cmdlets para implementar una aplicación de sucursal con funciones de supervivencia en Lync Server 2013

 

_**Última modificación del tema:** 2012-10-07_

En este tema se describe cómo implementar una Aplicación de sucursal con funciones de supervivencia con el Shell de administración de Lync Server. Realice este procedimiento en el sitio central.

## Para implementar una Aplicación de sucursal con funciones de supervivencia de forma remota

1.  Siga los pasos indicados en [Agregar sitios de sucursal a la topología en Lync Server 2013](lync-server-2013-add-branch-sites-to-your-topology.md) para agregar un sitio de sucursal.

2.  Vincule la sucursal con el dominio.

3.  Agregue el grupo RTCUniversalSBATechnicians al grupo de Administradores local.

4.  Reinicie el servidor e inicie sesión como miembro del grupo RTCUniversalSBATechnicians.

5.  En el Shell de administración de Lync Server, escriba los siguientes comandos, sustituyendo los marcadores de posición por la información correspondiente de su organización:
    
        Export-CsConfiguration -FileName C:\CSConfig.zip
        Import-CsConfiguration -LocalStore -FileName C:\CSConfig.zip -Verbose
        Enable-CSReplica -Verbose
        Enable-CsComputer -Verbose
        Request-CsCertificate -New -Type default -CA <YourCA> -Verbose
        Set-CsCertificate -Type Default -Thumbprint <YourCertThumbprint>
        Start-cswindowsservice -verbose

