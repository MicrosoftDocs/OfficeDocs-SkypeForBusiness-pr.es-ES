---
title: Configurar la página de participación en la reunión
TOCTitle: Configurar la página de participación en la reunión
ms:assetid: a87319b7-3124-4262-8f9d-18138870ee2d
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ205145(v=OCS.15)
ms:contentKeyID: 48276288
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configurar la página de participación en la reunión

 

_**Última modificación del tema:** 2015-03-09_

Cuando un usuario hace clic en un vínculo de una convocatoria de reunión, la página para unirse a la reunión detecta si ya hay un cliente de Lync 2013 instalado en el equipo del usuario. Si hay uno instalado, ese cliente se abre y se une a la reunión y, si no lo hay, se abre de manera predeterminada la versión 2013 de Microsoft Lync Web App.

Puede modificar el comportamiento de la página para unirse a la reunión si desea permitir que los usuarios participen de reuniones con Office Communicator 2007 R2 o Operador de Lync 2010. Estas opciones de configuración se quitaron del Panel de control de Lync Server 2013, pero puede establecerlas con el cmdlet CsWebServiceConfiguration.

### Parámetros de CsWebServiceConfiguration de la página para unirse a la reunión

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Parámetro de CsWebServiceConfiguration</th>
<th>Descripción</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ShowJoinUsingLegacyClientLink</p></td>
<td><p>Si se establece en True, los usuarios que se unan a una reunión con una aplicación cliente que no sea Lync tendrán la oportunidad de unirse a la reunión con Office Communicator 2007 R2. El valor predeterminado es False.</p></td>
</tr>
<tr class="even">
<td><p>ShowAlternateJoinOptionsExpanded</p></td>
<td><p>Si se establece en True, se expanden y se muestran automáticamente a los usuarios opciones alternativas para participar en una conferencia en línea (como Office Communicator 2007 R2). Si se establece en False (valor predeterminado), estas opciones también se encuentran disponibles, pero el usuario debe mostrar la lista de opciones de forma manual.</p></td>
</tr>
</tbody>
</table>


## Para configurar la página para unirse a la reunión con el Shell de administración de Lync Server 2013

1.  Abra el Shell de administración de Lync Server 2013: haga clic en **Inicio** , **Todos los programas** , **Microsoft Lync Server 2013** y en **Shell de administración de Lync Server**.

2.  Ejecute el siguiente cmdlet:
    
        Get-CsWebServiceConfiguration
    
    Este cmdlet devuelve las opciones de configuración del servicio web.

3.  Ejecute el siguiente comando con los parámetros establecidos en True o False, según cuál haya sido su preferencia (para más información sobre los parámetros de este cmdlet, vea la documentación del Shell de administración de Lync Server 2013):
    
        Set-CsWebServiceConfiguration -Identity global -ShowJoinUsingLegacyClientLink $True

