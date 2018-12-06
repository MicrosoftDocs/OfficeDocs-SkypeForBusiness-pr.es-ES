---
title: "Lync Server 2013: Planeamiento de recuperación ante desastres del grupo de respuesta"
TOCTitle: Planeamiento de recuperación ante desastres del grupo de respuesta
ms:assetid: 14e0f5dc-77cd-42cd-a9c9-4d0da38fb1cf
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ204699(v=OCS.15)
ms:contentKeyID: 48274525
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Planeamiento de recuperación ante desastres del grupo de respuesta en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

En esta sección se describen maneras para la preparación de grupos de respuesta para la recuperación ante desastres y se proporciona una visión general del proceso de recuperación ante desastres.

## Preparación para la recuperación ante desastres de Grupo de respuesta

Tenga en cuenta lo siguiente al preparar y llevar a cabo los procedimientos de recuperación ante desastres.


> [!NOTE]
> En un entorno de coexistencia, sólo se admiten los grupos de respuesta de Lync Server 2013 para los procedimientos de recuperación ante desastres que se describen en este documento.



  - Planifique para la recuperación ante desastres cuando realice el planeamiento de capacidad. Para la capacidad de recuperación ante desastres, cada grupo de servidores de un grupo de par debe ser capaz de manejar las cargas de trabajo de todos los grupos de respuesta de ambos grupos. Para obtener más información acerca de la planificación de capacidad de Grupo de respuesta, vea [Planificar la capacidad para el grupo de respuesta en Lync Server 2013](lync-server-2013-capacity-planning-for-response-group.md).

  - Realice copias de seguridad regulares de todas las configuraciones de grupos de respuesta en todos los Grupos de servidores front-end donde ha implementado el Aplicación de grupo de respuesta mediante el procedimiento de exportación que se describe en este documento. Para obtener detalles, vea [Procedimientos de recuperación ante desastres del grupo de respuesta en Lync Server 2013](lync-server-2013-response-group-disaster-recovery-procedures.md). Mantenga las copias de seguridad en una ubicación protegida y segura.

  - Conserve una copia de seguridad independiente de todos los archivos de audio originales que ha usado para la Aplicación de grupo de respuesta, incluidos las grabaciones y los archivos de música en espera. Mantenga los archivos de seguridad en una ubicación segura.

  - Para la recuperación ante desastres de Lync Server 2013, todas las configuraciones de Grupo de respuesta deben tener nombres únicos en toda la implementación. Este requisito se aplica a los flujos de trabajo, colas, grupos de agentes, conjuntos de vacaciones y horas laborales. Debe comprobar que se cumple este requisito cuando los grupos primarios y de reserva están todavía activos y antes de iniciar cualquier procedimiento de conmutación por error. Si encuentra conflictos de nombres al importar datos de grupo de respuesta al grupo de copia de seguridad, se produce un error en la importación. Para completar la importación y el procedimiento de conmutación por error, tiene que resolver los conflictos de nombre cambiando el nombre del objeto de grupo de respuesta en el grupo de copia de seguridad o usando el cmdlet **Import-CsRgsConfiguration** con el parámetro –ResolveNameConflicts para resolver el conflicto anexando un número de identificación único al objeto de grupo de respuesta.

  - En general, se recomienda que realice copias de seguridad diarias, pero si tiene un gran volumen de cambios, es posible que desee programar copias de seguridad más frecuentes. La cantidad de información que puede perder en caso de un desastre depende de la frecuencia de las copias de seguridad, así como de la frecuencia y el volumen de cambios.

  - Es posible importar grupos de respuesta a un grupo de servidores de copia de seguridad antes de que se produzca un desastre o una operación de conmutación por error. La importación de grupos de respuesta por adelantado reduce el tiempo de inactividad, ya que la Servicio de grupo de respuesta de Lync Server se puede restaurar en el grupo de servidores de copia de seguridad tan pronto como las llamadas se enruten al grupo de servidores de copia de seguridad.
    

    > [!NOTE]
    > El Aplicación de grupo de respuesta no puede llegar a ningún agente hospedado en un grupo de servidores inactivos hasta que finalice la conmutación por error. Durante este tiempo, el Aplicación de grupo de respuesta procesa las llamadas como si los agentes no estuvieran disponibles.



## Proceso de recuperación ante desastres de grupo de respuesta

En el caso de un desastre, puede recuperar grupos de respuesta usando cualquiera de los siguientes enfoques de recuperación:

  - Realice la conmutación por error a un grupo de servidores de copia de seguridad y, a continuación, la conmutación por recuperación del grupo de servidores original.

  - Realice la conmutación por error a un grupo de servidores de copia de seguridad, cree un nuevo grupo de servidores con un nombre de dominio completo (FQDN) diferente y, a continuación, importe los grupos de respuesta al nuevo grupo de servidores.

Durante la fase de conmutación por error de la recuperación ante desastres, los grupos de respuesta se encuentran en varios grupos de servidores: en el grupo de servidores principal (que no está disponible) y en el grupo de servidores de copia de seguridad. Los grupos de respuesta de ambos grupos de servidores tienen el mismo nombre y el mismo propietario (el grupo de servidores principal) pero tienen principales diferentes.

Cuando recupera creando un nuevo grupo de servidores con un FQDN diferente, tiene que asignar el nuevo grupo de servidores como el propietario de los grupos de respuesta al importarlos. La propiedad de los grupos de respuesta permanece con el grupo de servidores original a menos o hasta que vuelva a asignar de manera explícita la propiedad mediante el parámetro –OverwriteOwner con el cmdlet **Import-CsRgsConfiguration**.


> [!NOTE]
> También tiene que usar el parámetro –OverwriteOwner si ha vuelto a crear el grupo de servidores durante la recuperación (es decir, la base de datos de Grupo de respuesta está vacía), use o no el mismo FQDN. No tiene que usar el parámetro –OverwriteOwner si no ha vuelto a crear el grupo de servidores pero es permisible usar este parámetro siempre que importe grupos de respuesta de nuevo al grupo de servidores principal.



Solo puede definir un conjunto de valores de configuración de Grupo de respuesta de nivel de aplicación por grupo de servidores. Estos valores incluyen la configuración de música de espera predeterminada, el archivo de audio de música en espera predeterminado, el período de gracia de devolución de llamada de agente y la configuración de contexto de llamada. Para ver estos valores de configuración, ejecute el cmdlet de **Get-CsRgsConfiguration**. Para obtener detalles acerca del cmdlet **Get-CsRgsConfiguration**, vea [Get-CsRgsConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsRgsConfiguration).

Puede transferir esta configuración de nivel de aplicación de un grupo de servidores a otro mediante el cmdlet **Import-CsRgsConfiguration** con el parámetro –ReplaceExistingSettings, pero al hacerlo se invalidará la configuración en el grupo de servidores de destino.

> [!IMPORTANT]  
> Esta restricción acerca de la transferencia de configuración a otro grupo de servidores es verdadera solo para la configuración de nivel de aplicación y el archivo de audio de música en espera predeterminado. No se aplica a grupos de agente, a colas, a flujos de trabajo, a horas de oficina y a conjuntos de días festivos.



Si no desea reemplazar la configuración de nivel de aplicación en el grupo de servidores de copia de seguridad durante un desastre y el grupo de servidores principal no se puede recuperar, se perderá la configuración de nivel de aplicación del grupo de servidores principal. Si tiene que crear un nuevo grupo de servidores para reemplazar el grupo de servidores principal durante la recuperación, con el mismo FQDN o con un FQDN diferente, no podrá recuperar la configuración de nivel de aplicación original. En este caso, tiene que configurar el nuevo grupo de servidores con esta configuración e incluir el archivo de audio de música en espera.

Si decide usar el cmdlet **Import-CsRgsConfiguration** para transferir la configuración de nivel de aplicación desde el grupo de servidores principal al grupo de servidores de copia de seguridad durante un desastre, a continuación, puede transferir la configuración del grupo de servidores de copia de seguridad al nuevo grupo de servidores durante la recuperación de la misma manera que los ha transferido desde le grupo de servidores principal al grupo de servidores de copia de seguridad.

La tabla siguiente es una visión general de los pasos implicados en la recuperación de grupos de respuesta.

Para obtener más información acerca de cómo realizar estos pasos, consulte [Procedimientos de recuperación ante desastres del grupo de respuesta en Lync Server 2013](lync-server-2013-response-group-disaster-recovery-procedures.md).

### Pasos de recuperación ante desastres de grupo de respuesta

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
<td><p>De forma rutinaria, ejecute el cmdlet <strong>Export-CsRgsConfiguration</strong> para crear copias de seguridad de todas las configuraciones de Grupo de respuesta en todos los Grupos de servidores front-end donde se implementa Aplicación de grupo de respuesta.</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsResponseGroupAdministrator</p></td>
</tr>
<tr class="even">
<td><p>Durante la interrupción</p></td>
<td><p>Ejecute el cmdlet <strong>Import-CsRgsConfiguration</strong> para importar la configuración de Servicio de grupo de respuesta de Lync Server de copia de seguridad del grupo principal al grupo de copia de seguridad.</p>
<div>

> [!NOTE]
> Use el parámetro –ReplaceExistingSettings si desea reemplazar la configuración de Grupo de respuesta de nivel de aplicación en el grupo de servidores de copia de seguridad con la configuración del grupo de servidores principal. Si no transfiere la configuración de nivel de aplicación desde el grupo de servidores principal al grupo de servidores de copia de seguridad, y no se puede recuperar el grupo de servidores principal, perderá la configuración del grupo de servidores principal.


</div></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsResponseGroupAdministrator</p></td>
</tr>
<tr class="odd">
<td><p>Después de importar</p></td>
<td><p>Ejecute los cmdlets de Grupo de respuesta con el parámetro –ShowAll (para mostrar todos los grupos de respuesta) o el parámetro –Owner (para mostrar solo los grupos de respuesta importados) para comprobar que se importaron todas las configuraciones de grupo de respuesta al grupo de copia de seguridad:</p>
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
> Debe usar Shell de administración de Lync Server para administrar los grupos de respuesta que ha importado en el grupo de servidores de copia de seguridad. No puede usar Panel de control de Lync Server para administrar estos grupos de respuesta mientras se encuentran en el grupo de servidores de copia de seguridad.


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

