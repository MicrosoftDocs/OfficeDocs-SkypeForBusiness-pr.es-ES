---
title: 'Lync Server 2013: Planeación de la recuperación ante desastres del grupo de respuesta'
description: 'Lync Server 2013: Planeación de la recuperación ante desastres del grupo de respuesta.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for response group disaster recovery
ms:assetid: 14e0f5dc-77cd-42cd-a9c9-4d0da38fb1cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204699(v=OCS.15)
ms:contentKeyID: 48183482
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5294ddf7dbd42d95c5eb17acd6be6a5abc7a5917
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48549266"
---
# <a name="planning-for-response-group-disaster-recovery-in-lync-server-2013"></a>Planeación de la recuperación ante desastres del grupo de respuesta en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-11-01_

En esta sección se describen maneras para la preparación de grupos de respuesta para la recuperación ante desastres y se proporciona una visión general del proceso de recuperación ante desastres.

<div>

## <a name="preparing-for-response-group-disaster-recovery"></a>Preparación para la recuperación ante desastres del grupo de respuesta

Tenga en cuenta lo siguiente al preparar y llevar a cabo los procedimientos de recuperación ante desastres.

<div>


> [!NOTE]  
> En un entorno de coexistencia, solo se admiten los grupos de respuesta 2013 de Lync Server para los procedimientos de recuperación ante desastres descritos en este documento.



</div>

  - Planifique para la recuperación ante desastres cuando realice el planeamiento de capacidad. Para la capacidad de recuperación ante desastres, cada grupo de servidores de un grupo de par debe ser capaz de manejar las cargas de trabajo de todos los grupos de respuesta de ambos grupos. Para obtener más información sobre la planeación de la capacidad del grupo de respuesta, consulte [Capacity Planning for Response Group in Lync Server 2013](lync-server-2013-capacity-planning-for-response-group.md).

  - Realice copias de seguridad periódicas de todas las configuraciones de grupo de respuesta en todos los grupos de servidores front-end donde implementó la aplicación de grupo de respuesta mediante el procedimiento de exportación que se describe en este documento. Para obtener más información, consulte [Response Group Disaster Recovery Procedures in Lync Server 2013](lync-server-2013-response-group-disaster-recovery-procedures.md). Mantenga las copias de seguridad en una ubicación protegida y segura.

  - Conserve una copia de seguridad independiente de todos los archivos de audio originales que ha usado para la aplicación de grupo de respuesta, incluidas las grabaciones y los archivos de música en espera. Mantenga los archivos de seguridad en una ubicación segura.

  - Para la recuperación ante desastres de Lync Server 2013, todas las opciones de configuración del grupo de respuesta deben tener nombres únicos en toda la implementación. Este requisito se aplica a los flujos de trabajo, colas, grupos de agentes, conjuntos de vacaciones y horas laborales. Debe comprobar que se cumple este requisito cuando los grupos primarios y de reserva están todavía activos y antes de iniciar cualquier procedimiento de conmutación por error. Si encuentra conflictos de nombres al importar datos de grupo de respuesta al grupo de copia de seguridad, se produce un error en la importación. Para completar la importación y el procedimiento de conmutación por error, tiene que resolver los conflictos de nombre cambiando el nombre del objeto de grupo de respuesta en el grupo de copia de seguridad o usando el cmdlet **Import-CsRgsConfiguration** con el parámetro –ResolveNameConflicts para resolver el conflicto anexando un número de identificación único al objeto de grupo de respuesta.

  - En general, se recomienda que realice copias de seguridad diarias, pero si tiene un gran volumen de cambios, es posible que desee programar copias de seguridad más frecuentes. La cantidad de información que puede perder en caso de un desastre depende de la frecuencia de las copias de seguridad, así como de la frecuencia y el volumen de cambios.

  - Es posible importar grupos de respuesta a un grupo de servidores de copia de seguridad antes de que se produzca un desastre o una operación de conmutación por error. La importación de grupos de respuesta de antemano reduce el tiempo de inactividad, ya que el servicio del grupo de respuesta de Lync Server se puede restaurar en el grupo de copia de seguridad en cuanto las llamadas se enruten al grupo de copia de seguridad.
    
    <div>
    

    > [!NOTE]  
    > La aplicación de grupo de respuesta no puede llegar a ningún agente hospedado en un grupo de servidores inactivo hasta que se complete la conmutación por error. Durante este tiempo, la aplicación de grupo de respuesta procesa las llamadas como si dichos agentes no estuvieran disponibles.

    
    </div>

</div>

<div>

## <a name="response-group-disaster-recovery-process"></a>Proceso de recuperación ante desastres de grupo de respuesta

En el caso de un desastre, puede recuperar grupos de respuesta usando cualquiera de los siguientes enfoques de recuperación:

  - Realice la conmutación por error a un grupo de servidores de copia de seguridad y, a continuación, la conmutación por recuperación del grupo de servidores original.

  - Realice la conmutación por error a un grupo de servidores de copia de seguridad, cree un nuevo grupo de servidores con un nombre de dominio completo (FQDN) diferente y, a continuación, importe los grupos de respuesta al nuevo grupo de servidores.

Durante la fase de conmutación por error de la recuperación ante desastres, los grupos de respuesta se encuentran en varios grupos de servidores: en el grupo de servidores principal (que no está disponible) y en el grupo de servidores de copia de seguridad. Los grupos de respuesta de ambos grupos de servidores tienen el mismo nombre y el mismo propietario (el grupo de servidores principal) pero tienen principales diferentes.

Cuando recupera creando un nuevo grupo de servidores con un FQDN diferente, tiene que asignar el nuevo grupo de servidores como el propietario de los grupos de respuesta al importarlos. La propiedad de los grupos de respuesta permanece con el grupo de servidores original a menos o hasta que vuelva a asignar de manera explícita la propiedad mediante el parámetro –OverwriteOwner con el cmdlet **Import-CsRgsConfiguration**.

<div>


> [!NOTE]  
> También debe usar el parámetro – OverwriteOwner si ha reconstruido el grupo de servidores durante la recuperación (es decir, la base de datos del grupo de respuesta está vacía), independientemente de si usa el mismo FQDN. No tiene que usar el parámetro –OverwriteOwner si no ha vuelto a crear el grupo de servidores pero es permisible usar este parámetro siempre que importe grupos de respuesta de nuevo al grupo de servidores principal.



</div>

Solo se puede definir un conjunto de opciones de configuración de grupo de respuesta de nivel de aplicación por grupo de servidores. Estos valores incluyen la configuración de música de espera predeterminada, el archivo de audio de música en espera predeterminado, el período de gracia de devolución de llamada de agente y la configuración de contexto de llamada. Para ver estos valores de configuración, ejecute el cmdlet de **Get-CsRgsConfiguration**. Para obtener más información sobre el cmdlet **Get-CsRgsConfiguration** , consulte [Get-CsRgsConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsRgsConfiguration).

Puede transferir esta configuración de nivel de aplicación de un grupo de servidores a otro mediante el cmdlet **Import-CsRgsConfiguration**  con el parámetro –ReplaceExistingSettings, pero al hacerlo se invalidará la configuración en el grupo de servidores de destino.

<div>


> [!IMPORTANT]  
> Esta restricción acerca de la transferencia de configuración a otro grupo de servidores es verdadera solo para la configuración de nivel de aplicación y el archivo de audio de música en espera predeterminado. No se aplica a grupos de agente, a colas, a flujos de trabajo, a horas de oficina y a conjuntos de días festivos.



</div>

Si no desea reemplazar la configuración de nivel de aplicación en el grupo de servidores de copia de seguridad durante un desastre y el grupo de servidores principal no se puede recuperar, se perderá la configuración de nivel de aplicación del grupo de servidores principal. Si tiene que crear un nuevo grupo de servidores para reemplazar el grupo de servidores principal durante la recuperación, con el mismo FQDN o con un FQDN diferente, no podrá recuperar la configuración de nivel de aplicación original. En este caso, tiene que configurar el nuevo grupo de servidores con esta configuración e incluir el archivo de audio de música en espera.

Si decide usar el cmdlet **Import-CsRgsConfiguration**  para transferir la configuración de nivel de aplicación desde el grupo de servidores principal al grupo de servidores de copia de seguridad durante un desastre, a continuación, puede transferir la configuración del grupo de servidores de copia de seguridad al nuevo grupo de servidores durante la recuperación de la misma manera que los ha transferido desde le grupo de servidores principal al grupo de servidores de copia de seguridad.

La tabla siguiente es una visión general de los pasos implicados en la recuperación de grupos de respuesta.

Para más detalles sobre cómo realizar estos pasos, consulte [Response Group Disaster Recovery Procedures in Lync Server 2013](lync-server-2013-response-group-disaster-recovery-procedures.md).

### <a name="response-group-disaster-recovery-steps"></a>Pasos de recuperación ante desastres de grupo de respuesta

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
<td><p>Antes de una interrupción</p></td>
<td><p>De forma rutinaria, ejecute el cmdlet <strong>Export-CsRgsConfiguration</strong> para crear copias de seguridad de todas las configuraciones de grupo de respuesta en todos los grupos de servidores front-end donde se implemente la aplicación de grupo de respuesta.</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsResponseGroupAdministrator</p></td>
</tr>
<tr class="even">
<td><p>Durante la interrupción</p></td>
<td><p>Ejecute el cmdlet <strong>Import-CsRgsConfiguration</strong> para importar la configuración del servicio del grupo de respuesta de Lync Server de la copia de seguridad del grupo principal al grupo de copia de seguridad.</p>
<div>

> [!NOTE]  
> Use el parámetro – ReplaceExistingSettings si desea reemplazar la configuración del grupo de respuesta de nivel de aplicación en el grupo de servidores de reserva con la configuración del grupo principal. Si no transfiere la configuración de nivel de aplicación desde el grupo de servidores principal al grupo de servidores de copia de seguridad, y no se puede recuperar el grupo de servidores principal, perderá la configuración del grupo de servidores principal.


</div></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsResponseGroupAdministrator</p></td>
</tr>
<tr class="odd">
<td><p>Después de importar</p></td>
<td><p>Ejecute cmdlets de grupo de respuesta con el parámetro – ShowAll (para mostrar todos los grupos de respuesta) o el parámetro – Owner (para mostrar solo los grupos de respuesta importados) para comprobar que todas las configuraciones de grupo de respuesta se han importado al grupo de copia de seguridad.</p>
<div>

> [!IMPORTANT]  
> Si usa el parámetro –ShowAll o el parámetro –Owner, los grupos de respuesta que ha importado al grupo de servidores de copia de seguridad no se mostrarán en los resultados devueltos por los cmdlets.


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
<td><p>Luego de la conmutación por error</p></td>
<td><ul>
<li><p>Realice una llamada de prueba a un grupo de respuesta que se importó al grupo de copia de seguridad y compruebe que la llamada se controla correctamente.</p></li>
<li><p>Todos los agentes formales deben iniciar sesión de nuevo en sus grupos formales en el grupo de copia de seguridad.</p></li>
<li><p>Administrar los cambios de configuración:</p>
<p>Los grupos de respuesta del grupo de servidores de copia de seguridad, ya sean importados para el grupo de copia de seguridad o que pertenecen al grupo de copia de seguridad, se pueden modificar de la forma habitual durante la interrupción.</p>
<div>

> [!IMPORTANT]  
> Debe usar el shell de administración de Lync Server para administrar los grupos de respuesta que importó al grupo de copia de seguridad. No puede usar el panel de control de Lync Server para administrar estos grupos de respuesta mientras están en el grupo de copia de seguridad.


</div></li>
</ul></td>
<td><p>N/D</p></td>
</tr>
<tr class="odd">
<td><p>Después de la recuperación, antes de la conmutación por recuperación</p></td>
<td><p>Ejecutar el cmdlet <strong>Export-CsRgsConfiguration</strong> especificando el parámetro -Source como el grupo de copia de seguridad y el parámetro -Owner como el grupo primario para exportar los grupos de respuesta que son propiedad del grupo principal del grupo de copia de seguridad.</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsResponseGroupAdministrator</p></td>
</tr>
<tr class="even">
<td><p>Después de la conmutación por recuperación</p></td>
<td><ul>
<li><p>Ejecutar el cmdlet <strong>Import-CsRgsConfiguration</strong> para importar los grupos de respuesta de vuelta al grupo principal.</p>
<div>

> [!NOTE]  
> Si el grupo de servidores principal no se puede recuperar e implementa un nuevo grupo de servidores para reemplazarlo, use el parámetro –ReplaceExistingSettings para transferir la configuración de nivel de aplicación del grupo de servidores de copia de seguridad al nuevo grupo de servidores. Si no transfiere la configuración del grupo de servidores de la copia de seguridad, el nuevo grupo de servidores usará la configuración predeterminada.


</div></li>
<li><p>Ejecute los siguientes cmdlets con el parámetro –ShowAll (para mostrar todos los grupos de respuestas) o el parámetro –Owner (para mostrar solo los grupos de respuesta importados) para comprobar que todas las configuraciones de grupo de respuesta se han importado correctamente de vuelta al grupo primario:</p>
<ul>
<li><p><strong>Get-CsRgsWorkflow</strong></p></li>
<li><p><strong>Get-CsRgsQueue</strong></p></li>
<li><p><strong>Get-CsRgsAgentGroup</strong></p></li>
<li><p><strong>Get-CsRgsHoursOfBusiness</strong></p></li>
<li><p><strong>Get-CsRgsHolidaySet</strong></p></li>
</ul></li>
<li><p>Realice una llamada de prueba a un grupo de respuesta que se importó de vuelta al grupo primario y compruebe que la llamada se controla correctamente.</p></li>
<li><p>Opcionalmente, ejecute el cmdlet <strong>Export-CsRgsConfiguration</strong> en el grupo de copia de seguridad con el parámetro –RemoveExportedConfiguration para quitar los grupos de respuesta que son propiedad del grupo principal del grupo de copia de seguridad.</p></li>
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

