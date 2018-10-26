---
title: Configuración de las opciones de intervalo de puertos de medios
TOCTitle: Configuración de las opciones de intervalo de puertos de medios
ms:assetid: 2c4b7c0b-0dce-48f4-a489-336d6e526f7c
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ204770(v=OCS.15)
ms:contentKeyID: 48274777
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuración de las opciones de intervalo de puertos de medios

 

_**Última modificación del tema:** 2015-03-09_

La configuración del intervalo de puerto de medios puede afectar significativamente el rendimiento del cliente y debe configurarse. Puede configurar estos parámetros utilizando Shell de administración de Lync Server.

### Configuración de intervalo de puerto de medios

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Configuración</th>
<th>Descripción</th>
<th>cmdlet Shell de administración de Lync Server</th>
<th>Parámetros del cmdlet</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Portrange\Enabled</p></td>
<td><p>Especifica si el cliente debe usar los intervalos de puertos enviados por el servidor para medios y señalización. Se usa en combinación con los subvalores MinMediaPort y MaxMediaPort.</p></td>
<td><p><strong>CsConferencingConfiguration</strong></p></td>
<td><p>ClientMediaPortRangeEnabled</p></td>
</tr>
<tr class="even">
<td><p>Portrange\MinMediaPort</p></td>
<td><p>Especifica el número inicial de puerto que debe usarse para medios. Se combina con MaxMediaPort para especificar el intervalo de puertos. El intervalo mínimo recomendado es 40 puertos.</p></td>
<td><p><strong>CsConferencingConfiguration</strong></p></td>
<td><p>ClientMediaPort (representa el número inicial de puerto que debe usarse para los medios de cliente)</p></td>
</tr>
<tr class="odd">
<td><p>Portrange\MaxMediaPort</p></td>
<td><p>Especifica el número más alto de puerto que debe usarse para medios. Se combina con MinMediaPort para especificar el intervalo de puertos. El intervalo mínimo recomendado es 40 puertos.</p></td>
<td><p><strong>CsConferencingConfiguration</strong></p></td>
<td><p>ClientMediaPortRange (indica el número total de puertos disponibles para los medios de cliente; el valor predeterminado es 40)</p></td>
</tr>
</tbody>
</table>


## Configuración de parámetros del intervalo de puerto de medios

1.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Shell de administración de Lync Server**.

2.  Ejecute el siguiente cmdlet:
    
        Get-CsConferencingConfiguration
    
    Este cmdlet devuelve las opciones de configuración de la conferencia.

3.  Ejecute el siguiente cmdlet con los parámetros y valores que desea cambiar (para obtener información detallada sobre los parámetros de este cmdlet, consulte la documentación de Shell de administración de Lync Server):
    
        Set-CsConferencingConfiguration
    

    > [!NOTE]
    > Puede crear conjuntos adicionales de opciones de configuración de conferencias para sitios específicos. Use el cmdlet <STRONG>New- CsConferencingConfiguration</STRONG> con una identidad de sitio. Al crear nuevas opciones de configuración de conferencia para sitios, la configuración del sitio tiene preferencia sobre la configuración global. Para obtener información detallada, consulte la documentación del Shell de administración de Lync Server.


