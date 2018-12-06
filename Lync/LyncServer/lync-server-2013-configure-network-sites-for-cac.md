---
title: "Conf. les sites réseau pour le contr. d’adm. des appels dans Lync Server 2013"
TOCTitle: "Conf. les sites réseau pour le contr. d’adm. des appels dans Lync Server 2013"
ms:assetid: afcea38f-5789-45ec-97af-c6e38364950c
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg412840(v=OCS.15)
ms:contentKeyID: 48276368
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configurar sitios de red para CAC en Lync Server 2013

 

_**Última modificación del tema:** 2012-09-05_

> [!IMPORTANT]  
> Si ya ha creado sitios de red para E9-1-1 o desvío de medios, modifique los sitios de red existentes para aplicar un perfil de directiva de ancho de banda mediante el cmdlet Set-CsNetworkSite. Como ejemplo de cómo modificar un sitio de red, consulte <a href="lync-server-2013-create-or-modify-a-network-site.md">Crear o modificar un sitio de red en Lync Server 2013</a>.



Los *sitios de red* son las oficinas o ubicaciones dentro de cada región de red de las implementaciones de desvío de medios, E9-1-1 y control de admisión de llamadas. Use los procedimientos siguientes con el fin de crear sitios de red que alineen a sitios de red en la topología de red de ejemplo para el control de admisión de llamadas. Estos procedimientos muestran cómo crear y configurar sitios de red restringidos por el ancho de banda de la WAN y que, por tanto, requieren directivas de ancho de banda que limiten el flujo de tráfico de audio o vídeo en tiempo real.

En la implementación del control de admisión de llamadas de ejemplo, la región de Norteamérica tiene seis sitios. Tres de estos sitios están restringidos por el ancho de banda de la WAN: Reno, Portland y Albuquerque. Los tres sitios restantes que *no* están restringidos por el ancho de banda de la WAN son: Nueva York, Chicago y Detroit. Como ejemplo de cómo crear o modificar los otros sitios de red, consulte [Crear o modificar un sitio de red en Lync Server 2013](lync-server-2013-create-or-modify-a-network-site.md).

Para ver la topología de red de ejemplo, consulte [Ejemplo: Recopilación de los requisitos de la organización para el servicio de control de admisión de llamadas en Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) en la documentación referente a la planeación.


> [!NOTE]
> En el siguiente procedimiento, se usa el Shell de administración de Lync Server para crear un sitio de red. Para más información sobre cómo usar el Panel de control de Lync Server para crear un sitio de red, consulte <A href="lync-server-2013-create-or-modify-a-network-site.md">Crear o modificar un sitio de red en Lync Server 2013</A>.



## Para crear sitios de red para el control de admisión de llamadas

1.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Shell de administración de Lync Server**.

2.  Ejecute el cmdlet New-CsNetworkSite para crear sitios de red y aplicar un perfil de directiva de ancho de banda adecuado a cada sitio. Por ejemplo, ejecute lo siguiente:
    
    ```
    New-CsNetworkSite -NetworkSiteID Reno -Description "NA:Branch office for sales force" -NetworkRegionID NorthAmerica -BWPolicyProfileID 10MB_Link
    ```
    ```
    New-CsNetworkSite -NetworkSiteID Portland -Description "NA:Branch office for marketing force" -NetworkRegionID NorthAmerica -BWPolicyProfileID 5MB_Link
    ```
    ```
    New-CsNetworkSite -NetworkSiteID Albuquerque -Description "NA:Branch office for SouthWest sales" -NetworkRegionID EMEA -BWPolicyProfileID 10MB_Link
    ```

3.  Para terminar de crear sitios de red para la topología de ejemplo completa, repita el paso 2 para los sitios de red restringidos por el ancho de banda en las regiones EMEA y APAC.

