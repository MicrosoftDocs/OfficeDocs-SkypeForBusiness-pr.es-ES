---
title: 'Lync Server 2013: Planeamiento de recuperación ante desastres del grupo de respuesta'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for response group disaster recovery
ms:assetid: 14e0f5dc-77cd-42cd-a9c9-4d0da38fb1cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204699(v=OCS.15)
ms:contentKeyID: 48183482
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 70622364349eb83ecbc171cb3d5bf894ba03d3f9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824564"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-response-group-disaster-recovery-in-lync-server-2013"></a>Planeamiento de recuperación ante desastres del grupo de respuesta en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-11-01_

En esta sección se describen algunas formas de preparar grupos de respuesta para la recuperación de desastres y se ofrece información general sobre el proceso de recuperación de desastres.

<div>

## <a name="preparing-for-response-group-disaster-recovery"></a>Prepararse para la recuperación de desastres de grupos de respuesta

Tenga en cuenta lo siguiente cuando prepare y lleve a cabo procedimientos de recuperación ante desastres.

<div>


> [!NOTE]  
> En un entorno de coexistencia, solo se admiten los grupos de respuesta 2013 de Lync Server para los procedimientos de recuperación ante desastres que se describen en este documento.



</div>

  - Planee la recuperación de desastres cuando realice su plan de capacidad. Para la capacidad de recuperación ante desastres, cada grupo de un grupo emparejado debe poder administrar las cargas de trabajo de todos los grupos de respuesta en ambos grupos. Para obtener más información sobre la planeación de capacidad de los grupos de respuesta, consulte [planificación de capacidad para grupo de respuesta en Lync Server 2013](lync-server-2013-capacity-planning-for-response-group.md).

  - Realice copias de seguridad periódicas de todas las configuraciones de grupos de respuesta en todos los grupos de servidores front-end en los que implementó la aplicación de grupo de respuesta mediante el procedimiento de exportación descrito en este documento. Para obtener más información, consulte [procedimientos de recuperación ante desastres de grupos de respuesta en Lync Server 2013](lync-server-2013-response-group-disaster-recovery-procedures.md). Guarde las copias de seguridad en un lugar seguro.

  - Guarde una copia de seguridad separada de todos los archivos de audio originales que usó para la aplicación de grupo de respuesta, incluidas las grabaciones y los archivos de música en suspensión. Mantenga los archivos de copia de seguridad en un lugar seguro.

  - Para la recuperación ante desastres de Lync Server 2013, toda la configuración del grupo de respuesta debe tener nombres únicos en toda la implementación. Este requisito se aplica a flujos de trabajo, colas, grupos de agentes, conjuntos de días festivos y horas de trabajo. Debe comprobar que este requisito se cumple cuando los grupos principal y de copia de seguridad siguen estando activos y antes de que usted necesite iniciar cualquier procedimiento de conmutación por error. Si se produce un conflicto de nombres al importar datos de grupo de respuesta al grupo de copia de seguridad, se produce un error en la importación. Para completar el procedimiento de importación y conmutación por error, debe resolver los conflictos de nombre al cambiar el nombre del objeto de grupo de respuesta en el grupo de copias de seguridad o mediante el cmdlet **Import-CsRgsConfiguration** con el parámetro-ResolveNameConflicts para resolver el conflicto, anexe un número de identificación único al objeto de grupo de respuesta.

  - En general, le recomendamos que realice copias de seguridad diarias pero, si tiene un gran volumen de cambios, es posible que desee programar copias de seguridad más frecuentes. La cantidad de información que puede perder en caso de que se produzca un desastre depende de la frecuencia de las copias de seguridad, así como de la frecuencia y el volumen de los cambios.

  - Es posible importar grupos de respuesta a un grupo de copia de seguridad antes de que se produzca una operación de recuperación ante desastres o de conmutación por error. Importar grupos de respuesta anticipadamente reduce el tiempo de inactividad, porque el servicio de grupo de respuesta de Lync Server se puede restaurar en el grupo de copia de seguridad tan pronto como las llamadas se enruten al grupo de copia de seguridad.
    
    <div>
    

    > [!NOTE]  
    > La aplicación de grupo de respuesta no puede comunicarse con agentes alojados en un grupo inactivo hasta que se completa la conmutación por error. Durante este tiempo, la aplicación de grupo de respuesta procesa las llamadas como si no estuvieran disponibles.

    
    </div>

</div>

<div>

## <a name="response-group-disaster-recovery-process"></a>Proceso de recuperación ante desastres de grupos de respuesta

En caso de desastre, puede recuperar grupos de respuesta con uno de los siguientes métodos de recuperación:

  - Realice la conmutación por error a un grupo de copia de seguridad y luego vuelva a la agrupación original.

  - Realice la conmutación por error a un grupo de copia de seguridad, cree un nuevo grupo con un nombre de dominio completo (FQDN) diferente y, a continuación, importe los grupos de respuesta al nuevo grupo.

Durante la fase de conmutación por error de recuperación ante desastres, los grupos de respuesta residen en varios grupos: en el grupo primario (que no está disponible) y en el grupo de copias de seguridad. Los grupos de respuesta de ambos grupos tienen el mismo nombre y el mismo propietario (el grupo principal), pero tienen diferentes padres.

Al recuperar mediante la creación de un nuevo grupo con un FQDN diferente, debe asignar el nuevo grupo como propietario de los grupos de respuesta al importarlos. La propiedad de los grupos de respuesta se mantiene con el grupo original, a menos que o hasta que se reasigne de forma explícita la propiedad mediante el parámetro – OverwriteOwner con el cmdlet **Import-CsRgsConfiguration** .

<div>


> [!NOTE]  
> También necesita usar el parámetro – OverwriteOwner si reconstruyó el grupo durante la recuperación (es decir, la base de datos del grupo de respuesta está vacía), independientemente de si usa el mismo FQDN. No es necesario usar el parámetro – OverwriteOwner si no regeneizó el grupo, pero se permite que use este parámetro cada vez que importe los grupos de respuesta en el grupo primario.



</div>

Solo puede definir un conjunto de valores de configuración de grupo de respuesta de nivel de aplicación por grupo. Esta configuración incluye la configuración predeterminada de música en espera, el archivo de audio con música activa predeterminada, el período de gracia de timbre de timbre y la configuración de contexto de llamada. Para ver estas opciones de configuración, ejecute el cmdlet **Get-CsRgsConfiguration** . Para obtener más información sobre el cmdlet **Get-CsRgsConfiguration** , vea [Get-CsRgsConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsRgsConfiguration).

Puede transferir esta configuración de nivel de aplicación de un grupo a otro mediante el cmdlet **Import-CsRgsConfiguration** con el parámetro – ReplaceExistingSettings, pero si lo hace, se reemplazará la configuración del grupo de destino.

<div>


> [!IMPORTANT]  
> Esta restricción sobre la transferencia de la configuración a otro grupo solo es verdadera para la configuración de nivel de aplicación y el archivo de audio de música en espera predeterminado. No se aplica a grupos de agentes, colas, flujos de trabajo, horas laborales ni conjuntos de días festivos.



</div>

Si no quiere reemplazar la configuración de nivel de aplicación en el grupo de copias de seguridad durante un desastre y no se puede recuperar el grupo principal, se perderá la configuración de nivel de aplicación del grupo principal. Si necesita crear un nuevo grupo para reemplazar el grupo primario durante la recuperación, ya sea con el mismo FQDN o con un FQDN diferente, no puede recuperar la configuración de nivel de aplicación original. En este caso, debe configurar el nuevo grupo con esta configuración e incluir el archivo de audio de música en espera.

Si decide usar el cmdlet **Import-CsRgsConfiguration** para transferir la configuración de nivel de aplicación del grupo principal al grupo de copia de seguridad durante un desastre, puede transferir la configuración del grupo de copias de seguridad al nuevo grupo durante la recuperación en el mismo modo en que los transfirió del repositorio principal al grupo de copias de seguridad.

La tabla siguiente es una descripción general de los pasos necesarios para recuperar grupos de respuesta.

Para obtener detalles sobre cómo realizar estos pasos, consulte [grupos de respuesta procedimientos de recuperación de desastres en Lync Server 2013](lync-server-2013-response-group-disaster-recovery-procedures.md).

### <a name="response-group-disaster-recovery-steps"></a>Pasos de recuperación ante desastres de grupos de respuesta

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Fase</th>
<th>Pasos</th>
<th>Grupos y roles necesarios</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Antes de la interrupción</p></td>
<td><p>De forma rutinaria, ejecute el cmdlet <strong>Export-CsRgsConfiguration</strong> para crear copias de seguridad de todas las configuraciones de grupo de respuesta en todas las agrupaciones front end donde se implementa la aplicación de grupo de respuesta.</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsResponseGroupAdministrator</p></td>
</tr>
<tr class="even">
<td><p>Durante la interrupción</p></td>
<td><p>Ejecute el cmdlet <strong>Import-CsRgsConfiguration</strong> para importar la configuración del servicio del grupo de respuesta de Lync Server de la copia de seguridad del grupo principal al grupo de copia de seguridad.</p>
<div>

> [!NOTE]  
> Use el parámetro – ReplaceExistingSettings si desea reemplazar la configuración del grupo de respuesta de nivel de aplicación en el grupo de copias de seguridad con la configuración del grupo principal. Si no transfiere la configuración de nivel de aplicación del grupo principal al grupo de copias de seguridad y éste no se puede recuperar, perderá la configuración del grupo primario.


</div></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsResponseGroupAdministrator</p></td>
</tr>
<tr class="odd">
<td><p>Después de importar</p></td>
<td><p>Ejecute cmdlets de grupo de respuesta con el parámetro – ShowAll (para mostrar todos los grupos de respuesta) o el parámetro-Owner (para mostrar solo grupos de respuesta importados) para comprobar que todas las configuraciones de grupo de respuesta se importaron al grupo de copias de seguridad.</p>
<div>

> [!IMPORTANT]  
> Si no usa el parámetro – ShowAll o el parámetro-Owner, los grupos de respuesta que importó al grupo de copia de seguridad no se mostrarán en los resultados devueltos por los cmdlets.


</div>
<p>Ejecute los siguientes cmdlets:</p>
<ul>
<li><p><strong>Get-CsRgsWorkflow</strong></p></li>
<li><p><strong>Get-CsRgsQueue</strong></p></li>
<li><p><strong>Get-CsRgsAgentGroup</strong></p></li>
<li><p><strong>Get-CsRgsHoursOfBusiness</strong></p></li>
<li><p><strong>Get-CsRgsHolidaySet</strong></p></li>
</ul></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsResponseGroupAdministrator</p></td>
</tr>
<tr class="even">
<td><p>Después de la conmutación por error</p></td>
<td><ul>
<li><p>Realice una llamada de prueba a un grupo de respuesta que se importó al grupo de copia de seguridad y compruebe que la llamada se controla correctamente.</p></li>
<li><p>Todos los agentes formales deben iniciar sesión de nuevo en sus grupos formales en el grupo de copia de seguridad.</p></li>
<li><p>Administrar cambios de configuración:</p>
<p>Los grupos de respuesta del grupo de copia de seguridad, ya se hayan importado al grupo de copia de seguridad o que pertenezcan al grupo de copias de seguridad, se pueden modificar como de costumbre durante la interrupción.</p>
<div>

> [!IMPORTANT]  
> Debe usar el shell de administración de Lync Server para administrar los grupos de respuesta que importó al grupo de copias de seguridad. No puede usar el panel de control de Lync Server para administrar estos grupos de respuesta mientras se encuentran en el grupo de copia de seguridad.


</div></li>
</ul></td>
<td><p>N/D</p></td>
</tr>
<tr class="odd">
<td><p>Después de la recuperación, antes del failback</p></td>
<td><p>Ejecute el cmdlet <strong>Export-CsRgsConfiguration</strong> y especifique el parámetro-Source como grupo de copias de seguridad y el parámetro-Owner como grupo principal para exportar los grupos de respuesta que pertenecen al grupo principal del grupo de copias de seguridad.</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsResponseGroupAdministrator</p></td>
</tr>
<tr class="even">
<td><p>Después de la conmutación por recuperación</p></td>
<td><ul>
<li><p>Ejecute el cmdlet <strong>Import-CsRgsConfiguration</strong> para volver a importar los grupos de respuesta en el grupo primario.</p>
<div>

> [!NOTE]  
> Si el grupo principal no se puede recuperar e implementa un nuevo grupo de servidores para reemplazarlo, use el parámetro – ReplaceExistingSettings para transferir la configuración de nivel de aplicación del grupo de copias de seguridad al nuevo grupo. Si no transfiere la configuración del grupo de copia de seguridad, el nuevo grupo usará la configuración predeterminada.


</div></li>
<li><p>Ejecute los siguientes cmdlets con el parámetro – ShowAll (para mostrar todos los grupos de respuesta) o el parámetro-Owner (para mostrar solo grupos de respuesta importados) para comprobar que todas las configuraciones de grupo de respuesta se importaron correctamente al grupo primario:</p>
<ul>
<li><p><strong>Get-CsRgsWorkflow</strong></p></li>
<li><p><strong>Get-CsRgsQueue</strong></p></li>
<li><p><strong>Get-CsRgsAgentGroup</strong></p></li>
<li><p><strong>Get-CsRgsHoursOfBusiness</strong></p></li>
<li><p><strong>Get-CsRgsHolidaySet</strong></p></li>
</ul></li>
<li><p>Realice una llamada de prueba a un grupo de respuesta que se haya importado al grupo de servidores principal y compruebe que la llamada se controla correctamente.</p></li>
<li><p>De manera opcional, ejecute el cmdlet <strong>Export-CsRgsConfiguration</strong> en el grupo de copias de seguridad con el parámetro – RemoveExportedConfiguration para quitar los grupos de respuesta que pertenecen al grupo principal del grupo de copias de seguridad.</p></li>
</ul></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsResponseGroupAdministrator</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

