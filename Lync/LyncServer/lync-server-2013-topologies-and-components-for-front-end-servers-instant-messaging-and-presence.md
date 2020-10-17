---
title: 'Lync Server 2013: topologías y componentes para los servidores front-end, la mensajería instantánea y la presencia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Topologies and components for Front End Servers, instant messaging, and presence
ms:assetid: f08ce7a1-d14e-4a54-9771-a82c870658bf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412996(v=OCS.15)
ms:contentKeyID: 48185763
ms.date: 10/24/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 103d03920df57023ae7dbb953beb0c426d0a43df
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48503757"
---
# <a name="topologies-and-components-for-front-end-servers-instant-messaging-and-presence-in-lync-server-2013"></a>Topologías y componentes para los servidores front-end, la mensajería instantánea y la presencia en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-10-24_

Los únicos componentes necesarios para la mensajería instantánea (mi) y la presencia son:

  - Los servidores front-end de la organización o los servidores Standard Edition. Las capacidades de mensajería instantánea y presencia siempre están habilitadas en estos servidores.

  - Un equilibrador de carga, si tiene un grupo de servidores front-end Enterprise Edition. Para obtener más información, consulte [requisitos de equilibrio de carga para Lync Server 2013](lync-server-2013-load-balancing-requirements.md).

<div>

## <a name="planning-for-the-deployment-of-front-end-pools"></a>Planeación de la implementación de grupos de servidores front-end

En Lync Server 2013, la arquitectura del grupo de servidores front-end ha cambiado y estos cambios afectan a la planeación y el mantenimiento de los grupos de servidores front-end.

Se recomienda que todos los grupos de servidores front-end Enterprise Edition incluyan al menos tres servidores front-end. En Lync Server, la arquitectura de los grupos de servidores front-end usa un modelo de sistemas distribuidos, donde los datos de cada usuario se guardan en tres servidores front-end del grupo. Para obtener más información acerca de esta nueva arquitectura, vea [cambios en la topología en Lync Server 2013](lync-server-2013-topology-changes.md).

Si no desea implementar tres servidores front-end Enterprise Edition y desea realizar una recuperación ante desastres, le recomendamos que use Lync Server Standard Edition y cree dos grupos de servidores con una relación de copia de seguridad emparejada. Esto proporcionará una solución de recuperación ante desastres con solo dos servidores. Para obtener más información sobre las topologías y características de alta disponibilidad y recuperación ante desastres, consulte [Planning for High Availability and Disaster Recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).

</div>

<div>

## <a name="planning-for-the-management-of-front-end-pools"></a>Planeación de la administración de grupos de servidores front-end

Para los grupos de servidores front-end, siga las instrucciones de esta sección.

<div>

## <a name="ensuring-that-pools-are-functional"></a>Garantizar la funcionalidad de los grupos

Con el nuevo modelo distribuido para los grupos de servidores front-end, se deben ejecutar ciertos números de servidores de grupo para que el grupo funcione. Hay dos modos de pérdida para un grupo de servidores

  - Pérdida de quórum de nivel de grupo de enrutamiento, debido a que no hay suficientes servidores de réplica para un grupo de enrutamiento en particular. Un grupo de enrutamiento es una agregación de un conjunto de usuarios hospedados en el grupo de servidores. Cada grupo de enrutamiento tiene tres réplicas en el Grupo: una principal y dos secundarias.

  - Pérdida de quórum de nivel de grupo de servidores, que se produce cuando no hay suficientes servidores semilla ejecutándose en el grupo.

<div>

## <a name="routing-group-level-quorum-loss"></a>Pérdida de quórum en el nivel de grupo de enrutamiento

La primera vez que inicie un nuevo grupo de servidores front-end, es esencial que 85% de los servidores estén en funcionamiento, como se muestra en la siguiente tabla. Si se están ejecutando menos servidores, es posible que los servicios estén atascados en el estado inicial y que el grupo no se inicie.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Número total de servidores del grupo</th>
<th>Número de servidores que deben estar en ejecución para que el grupo se inicie por primera vez</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>segundo</p></td>
<td><p>1</p></td>
</tr>
<tr class="even">
<td><p>3</p></td>
<td><p>3</p></td>
</tr>
<tr class="odd">
<td><p>4 </p></td>
<td><p>3</p></td>
</tr>
<tr class="even">
<td><p>5 </p></td>
<td><p>4 </p></td>
</tr>
<tr class="odd">
<td><p>6 </p></td>
<td><p>5 </p></td>
</tr>
<tr class="even">
<td><p>7 </p></td>
<td><p>5 </p></td>
</tr>
<tr class="odd">
<td><p>8 </p></td>
<td><p>6 </p></td>
</tr>
<tr class="even">
<td><p>9 </p></td>
<td><p>7 </p></td>
</tr>
<tr class="odd">
<td><p>10  </p></td>
<td><p>8 </p></td>
</tr>
<tr class="even">
<td><p>12</p></td>
<td><p>9 </p></td>
</tr>
<tr class="odd">
<td><p>12 </p></td>
<td><p>10  </p></td>
</tr>
</tbody>
</table>


Cada vez que se inicia el grupo, se debe iniciar el 85% de los servidores (como se muestra en la tabla anterior). Si no se puede iniciar este número de servidores (pero se pueden iniciar suficientes servidores para que no se pierda el quórum en el nivel de grupo), puede usar el cmdlet **RESET-CsPoolRegistrarState – ResetType QuorumLossRecovery** para permitir que el grupo se recupere de esta pérdida de quórum en el nivel de grupo de enrutamiento y realice el progreso. Para obtener más información acerca de cómo usar este cmdlet, consulte [RESET-CsPoolRegistrarState](https://docs.microsoft.com/powershell/module/skype/Reset-CsPoolRegistrarState).

<div>


> [!NOTE]  
> Debido a que Lync Server usa la base de datos SQL principal como testigo, si apaga la base de datos principal y cambia a la copia reflejada, y apaga los servidores front-end suficientes para que no haya suficiente de acuerdo con la tabla anterior, se producirá todo el grupo. Para obtener más información, consulte <A href="https://go.microsoft.com/fwlink/?linkid=393672">testigo de creación de reflejo</A>de la base de datos.



</div>

</div>

<div>

## <a name="pool-level-quorum-loss"></a>Pérdida de quórum de nivel de grupo de servidores

Para que un grupo de servidores front-end funcione, no puede estar en pérdida de quórum en el nivel de grupo. Si el número de servidores que se ejecutan está por debajo del nivel funcional, como se muestra en la siguiente tabla, los demás servidores del grupo detendrán todos los servicios de Lync Server. Tenga en cuenta que los números de la siguiente tabla suponen que se están ejecutando los servidores back-end del grupo.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Número total de servidores front-end en el grupo</th>
<th>Número necesario de servidores en ejecución para que el grupo sea funcional</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>segundo</p></td>
<td><p>1</p></td>
</tr>
<tr class="even">
<td><p>3-4</p></td>
<td><p>Cualquier 2</p></td>
</tr>
<tr class="odd">
<td><p>5-6</p></td>
<td><p>Cualquier 3</p></td>
</tr>
<tr class="even">
<td><p>7 </p></td>
<td><p>Cualquier 4</p></td>
</tr>
<tr class="odd">
<td><p>8-9</p></td>
<td><p>4 de los primeros 7 servidores</p></td>
</tr>
<tr class="even">
<td><p>10-12</p></td>
<td><p>5 de los primeros 9 servidores</p></td>
</tr>
</tbody>
</table>


En la tabla anterior, los "primeros servidores" son los servidores que se pusieron en primer lugar, de forma cronológica, cuando se inició el grupo por primera vez. Para determinar estos servidores, puede usar el cmdlet **Get-CsComputer** con la opción **– PoolFqdn** . Este cmdlet mostrará los servidores en el orden en que aparecen en la topología y los que se encuentran en la parte superior de la lista son los primeros servidores.

</div>

<div>

## <a name="front-end-pools-with-two-front-end-servers"></a>Grupos de servidores front-end con dos servidores front-end

No se recomienda implementar un grupo de servidores front-end que contenga solo dos servidores front-end. Si alguna vez necesita implementar ese grupo de servidores, siga estas instrucciones:

  - Si uno de los dos servidores front-end deja de funcionar, debería intentar volver a conectar el servidor con el error tan pronto como sea posible. De forma similar, si necesita actualizar uno de los dos servidores, vuelva a conectarlo tan pronto como finalice la actualización.

  - Si, por algún motivo, necesita poner ambos servidores al mismo tiempo, haga lo siguiente cuando finalice el tiempo de inactividad del Grupo:
    
      - El procedimiento recomendado es reiniciar ambos servidores front-end al mismo tiempo.
    
      - Si no se pueden reiniciar los dos servidores al mismo tiempo, deberá ponerlos en marcha de nuevo en el orden inverso al orden en que se encontraban.
    
      - Si no puede realizar una copia de seguridad en ese orden, use el siguiente cmdlet antes de volver a poner el grupo de servidores:.
        
            Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery -PoolFQDN <FQDN>

</div>

<div>

## <a name="additional-steps-to-ensure-pools-are-functional"></a>Pasos adicionales para garantizar que los grupos de servidores son funcionales

Debe vigilar un par de otros factores para asegurarse de que los grupos de servidores front-end sigan siendo funcionales.

  - Al mover usuarios al grupo por primera vez, asegúrese de que al menos tres de los servidores front-end se están ejecutando.

  - Si establece una relación de emparejamiento entre este grupo de servidores y otro grupo para fines de recuperación ante desastres, después de establecer esa relación, debe asegurarse de que este grupo tenga tres servidores front-end que se ejecuten simultáneamente para sincronizar correctamente los datos con el grupo de copia de seguridad. Para obtener más información sobre el emparejamiento de grupos de servidores y las características de recuperación ante desastres, consulte [Planning for High Availability and Disaster Recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).

</div>

</div>

<div>

## <a name="improving-the-reliability-of-pool-upgrades"></a>Mejorar la confiabilidad de las actualizaciones de los grupos de servidores

Cuando necesite actualizar o aplicar una revisión a los servidores de un grupo de servidores front-end, siga el flujo de trabajo que se muestra en [actualizar o actualizar los servidores front-end en Lync Server 2013](lync-server-2013-upgrade-or-update-front-end-servers.md)y las siguientes directrices:

  - Al pasar de un dominio de actualización a otro para actualizaciones (siguiendo el flujo de trabajo en la [actualización o actualización de los servidores front-end en Lync Server 2013](lync-server-2013-upgrade-or-update-front-end-servers.md)), usará el cmdlet **Get-CsPoolUpgradeReadinessState** y comprobará el estado Ready. Agregar una espera de 20 minutos entre cada dominio de actualización después de que se alcance "listo" hará que las actualizaciones sean más confiables. Si no está **listo** durante estos 20 minutos, reinicie el temporizador de 20 minutos. Además, puede ejecutar el cmdlet **Get-CsPoolFabricState** antes y después de iniciar el intervalo de 20 minutos y asegurarse de que no haya cambios en las principales y secundarias de los grupos de enrutamiento.

  - No continúe con el siguiente dominio de actualización si alguno de los servidores del último dominio de actualización revisado están detenidos o no se han reiniciado. Esto también se aplica si no se puede iniciar ninguno de los servidores que hay en una actualización. Ejecute **Get-CsPoolFabricState** para asegurarse de que todos los grupos de enrutamiento tienen un primario y al menos uno secundario; se confirmará si todos los usuarios tienen servicio.

  - Si algunos usuarios tienen servicio y otros no, ejecute **Get-CsPoolFabricState** con la opción – verbose para comprobar los grupos de enrutamiento que tienen réplicas que faltan. No reinicie todo el grupo de servidores como primer paso de solución de problemas. Para obtener más información sobre este cmdlet, consulte [Get-CsPoolFabricState](https://docs.microsoft.com/powershell/module/skype/Get-CsPoolFabricState).

  - Asegúrese de que todas las instancias del visor de eventos o de las ventanas del monitor de rendimiento estén cerradas para las instalaciones o desinstalaciones de Windows fabric.

</div>

<div>

## <a name="changing-a-front-end-pools-configuration"></a>Cambio de la configuración del grupo de servidores front-end

Siempre que agregue servidores front-end a un grupo o los quite del grupo y, a continuación, publique la nueva topología, siga estas instrucciones:

  - Una vez publicada la nueva topología, debe reiniciar cada uno de los servidores front-end del grupo. Reinícielo a la vez.

  - Si todo el grupo de servidores ha estado inactivo durante el cambio de configuración, ejecute el siguiente cmdlet después de publicar la nueva topología:
    
        Reset-CsPoolRegistrarState -PoolFQDN <PoolFQDN> -ResetType ServiceReset

Si se produce un error en un servidor front-end y es improbable que se reemplace durante unos cuantos días o más, quite el servidor de la topología. Agregue el nuevo servidor front-end a la topología cuando vuelva a estar disponible.

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

