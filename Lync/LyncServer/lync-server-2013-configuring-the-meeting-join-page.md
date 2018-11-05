---
title: 'Lync Server 2013: Configuración de la página de participación en reuniones'
TOCTitle: Configuración de la página de participación en reuniones
ms:assetid: 45880423-47f4-49af-b825-cbd8e3fc1046
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ204861(v=OCS.15)
ms:contentKeyID: 48275099
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuración de la página de participación en reuniones en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

Cuando un usuario hace clic en un vínculo de reunión de una convocatoria de reunión, la página de participación en la reunión detecta si ya hay un cliente de Lync 2013 instalado en el equipo del usuario. Si hay uno instalado, el cliente se abre y se une a la reunión. Si no hay instalado un cliente, de forma predeterminada se abre la versión 2013 de Lync Web App.

Puede modificar el comportamiento de la página para unirse a la reunión si desea permitir que los usuarios se unan a reuniones con Office Communicator 2007 R2 o Operador de Lync 2010. Estas opciones de configuración se han quitado del Panel de control de Lync Server 2013, pero puede configurarlas con el cmdlet de Set-CsWebServiceConfiguration.

### Parámetros de Set-CsWebServiceConfiguration de la página para unirse a la reunión

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Parámetro Set-CsWebServiceConfiguration</th>
<th>Descripción</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ShowJoinUsingLegacyClientLink</p></td>
<td><p>Si se establece en True, los usuarios que se unan a la reunión con una aplicación de cliente distinta de Lync tendrán la oportunidad de unirse a la reunión usando Office Communicator 2007 R2. El valor predeterminado es False.</p></td>
</tr>
<tr class="even">
<td><p>ShowAlternateJoinOptionsExpanded</p></td>
<td><p>Si se establece en True, se expanden y se muestran automáticamente a los usuarios opciones alternativas para participar en una conferencia en línea (como Office Communicator 2007 R2). Si se establece en False (valor predeterminado), estas opciones también se encuentran disponibles, pero el usuario debe mostrar la lista de opciones de forma manual.</p></td>
</tr>
</tbody>
</table>


## Para configurar la página para unirse a la reunión con el Shell de administración de Lync Server 2013

1.  Abra el Shell de administración de Lync Server 2013: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y en **Shell de administración de Lync Server**.

2.  Para ver las opciones de configuración del servicio web, ejecute el cmdlet siguiente:
    
        Get-CsWebServiceConfiguration

3.  Ejecute el siguiente comando con los parámetros establecidos en True o False, según cuál haya sido su preferencia (para más información sobre los parámetros de este cmdlet [Set-CsWebServiceConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsWebServiceConfiguration), vea la documentación del Shell de administración de Lync Server 2013):
    
        Set-CsWebServiceConfiguration -Identity global -ShowJoinUsingLegacyClientLink $True

## Vea también

#### Otros recursos

[Set-CsWebServiceConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsWebServiceConfiguration)

