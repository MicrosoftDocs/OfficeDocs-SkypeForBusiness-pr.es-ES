---
title: 'Configurar regiones de red para control de admisión de llamadas en Lync Server 2013'
TOCTitle: Configurar regiones de red para el control de admisión de llamadas en Lync Server 2013
ms:assetid: ea3ff988-dd5a-4bc4-bec5-39a0fb09793a
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg399051(v=OCS.15)
ms:contentKeyID: 48277058
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configurar regiones de red para el control de admisión de llamadas en Lync Server 2013

 

_**Última modificación del tema:** 2012-09-21_

> [!IMPORTANT]  
> Si ya ha creado regiones de red para E9-1-1 o para el desvío de medios, puede modificar las regiones de red existentes mediante la adición de parámetros específicos de control de admisión de llamadas con el cmdlet Set-<strong>Set-CsNetworkRegion</strong>. Para ver un ejemplo de cómo modificar una región de red, consulte <a href="lync-server-2013-create-or-modify-a-network-region.md">Crear o modificar una región de red en Lync Server 2013</a>.



*Las regiones de red* son los concentradores de red o redes troncales que se usan en la configuración del control de admisión de llamadas, de E9-1-1 y del desvío de medios. Siga estos procedimientos para crear regiones de red que se correspondan con las regiones de red del ejemplo de topología de red para controlar la admisión de llamadas. Para consultar el ejemplo de topología de red, visite [Ejemplo: Recopilación de los requisitos de la organización para el servicio de control de admisión de llamadas en Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) en la documentación sobre planificación.

La topología de red de ejemplo para el control de admisión de llamadas tiene tres regiones: Norteamérica, EMEA y APAC. Cada región tiene un sitio central especificado. Para la región de Norteamérica, el sitio central designado se denomina CHICAGO. En el procedimiento siguiente se muestra un ejemplo de cómo puede usar el cmdlet **New-CsNetworkRegion** para crear la región de Norteamérica.


> [!NOTE]
> En el siguiente procedimiento, se usa Shell de administración de Lync Server para crear una región de red. Para más información sobre el uso del Panel de control de Lync Server para crear una región de red, consulte <A href="lync-server-2013-create-or-modify-a-network-region.md">Crear o modificar una región de red en Lync Server 2013</A>.



## Para crear una región de red para el control de admisión de llamadas

1.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Shell de administración de Lync Server**.

2.  Para cada región que necesite crear, ejecute el cmdlet **New-CsNetworkRegion**. Por ejemplo, para crear la región de Norteamérica, ejecute:
    
        New-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "All North America Locations"

3.  Repita el segundo paso para crear regiones de red de EMEA y APAC.

