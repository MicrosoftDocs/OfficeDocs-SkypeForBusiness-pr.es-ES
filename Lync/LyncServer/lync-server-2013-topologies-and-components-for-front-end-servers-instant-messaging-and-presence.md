---
title: 'Lync Server 2013: Topologías y componentes para los servidores front-end, la mensajería instantánea y la presencia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Topologies and components for Front End Servers, instant messaging, and presence
ms:assetid: f08ce7a1-d14e-4a54-9771-a82c870658bf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412996(v=OCS.15)
ms:contentKeyID: 48185763
ms.date: 10/24/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4bc44790fc9584676cdd10305085b23bd5e99299
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850312"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="topologies-and-components-for-front-end-servers-instant-messaging-and-presence-in-lync-server-2013"></a>Topologías y componentes para los servidores front-end, la mensajería instantánea y la presencia en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-10-24_

Los únicos componentes necesarios para la mensajería instantánea (MI) y la presencia son:

  - Los servidores front-end de su organización o los servidores Standard Edition. Las capacidades de presencia y de mensajería instantánea (MI) siempre se encuentran habilitadas en estos servidores.

  - Un equilibrador de carga, si se dispone de un grupo de servidores front-end Enterprise Edition. Para obtener más información, consulte [requisitos de equilibrio de carga para Lync Server 2013](lync-server-2013-load-balancing-requirements.md).

<div>

## <a name="planning-for-the-deployment-of-front-end-pools"></a>Planear la implementación de grupos de servidores front-end

En Lync Server 2013, la arquitectura del grupo de servidores front-end ha cambiado y estos cambios afectan a la manera en que debe planear y mantener los grupos de aplicaciones para el usuario.

Recomendamos que todos los grupos de servidores front-end Enterprise Edition incluyan al menos tres servidores frontales. En Lync Server, la arquitectura de los grupos front-end usa un modelo de sistemas distribuidos, con los datos de cada usuario guardados en tres servidores front-end en el grupo. Para obtener más información acerca de esta nueva arquitectura, consulte [cambios de topología en Lync Server 2013](lync-server-2013-topology-changes.md).

Si no desea implementar tres servidores Enterprise Edition front-end y desea recuperar desastres, le recomendamos que use Lync Server Standard Edition y cree dos grupos con una relación de copia de seguridad emparejada. Esto proporcionará una solución de recuperación ante desastres con solo dos servidores. Para obtener más información, sobre las características y las topologías de alta disponibilidad y recuperación ante desastres, consulte [planear la alta disponibilidad y la recuperación ante desastres en Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).

</div>

<div>

## <a name="planning-for-the-management-of-front-end-pools"></a>Planificación de la administración de grupos de servidores front-end

Para los grupos de servidores front-end, siga las instrucciones de esta sección.

<div>

## <a name="ensuring-that-pools-are-functional"></a>Garantizar la funcionalidad de los grupos

Con el nuevo modelo distribuido para los grupos de servidores front-end, se deben ejecutar ciertos números de servidores de grupo para que el grupo funcione. Hay dos modos de pérdida para un grupo

  - Pérdida de cuórum en el grupo de enrutamiento, provocada por una cantidad insuficiente de servidores de réplicas para un determinado grupo de enrutamiento. Un grupo de enrutamiento es una agregación de un conjunto de usuarios alojados en el grupo. Cada grupo de enrutamiento tiene tres réplicas en el Grupo: uno principal y dos secundarios.

  - Pérdida de cuórum en el grupo de servidores, que ocurre cuando no hay una cantidad suficiente de servidores semilla en ejecución en el grupo.

<div>

## <a name="routing-group-level-quorum-loss"></a>Pérdida de cuórum en el grupo de enrutamiento

La primera vez que inicia un nuevo grupo de servidores front-end, es fundamental que el 85 % de los servidores estén en funcionamiento, tal como se muestra en la tabla siguiente. Si hay menos servidores en ejecución, es posible que los servicios queden interrumpidos en el estado de inicio y que el grupo no se inicie.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Cantidad total de servidores en el grupo</th>
<th>Cantidad de servidores que necesitan estar en ejecución para que el grupo se inicie por primera vez</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>2</p></td>
<td><p>1</p></td>
</tr>
<tr class="even">
<td><p>3</p></td>
<td><p>3</p></td>
</tr>
<tr class="odd">
<td><p>4</p></td>
<td><p>3</p></td>
</tr>
<tr class="even">
<td><p>5</p></td>
<td><p>4</p></td>
</tr>
<tr class="odd">
<td><p>6</p></td>
<td><p>5</p></td>
</tr>
<tr class="even">
<td><p>7</p></td>
<td><p>5</p></td>
</tr>
<tr class="odd">
<td><p>4,8</p></td>
<td><p>6</p></td>
</tr>
<tr class="even">
<td><p>99,999</p></td>
<td><p>7</p></td>
</tr>
<tr class="odd">
<td><p>base10</p></td>
<td><p>4,8</p></td>
</tr>
<tr class="even">
<td><p>once</p></td>
<td><p>99,999</p></td>
</tr>
<tr class="odd">
<td><p>2007</p></td>
<td><p>base10</p></td>
</tr>
</tbody>
</table>


Cada vez subsiguiente que se inicie el grupo, es preciso iniciar el 85 % de los servidores (tal como se muestra en la tabla anterior). Si no se puede iniciar esta cantidad de servidores (pero se puede iniciar una cantidad de servidores suficiente para que no haya pérdida de cuórum en el grupo de servidores), puede usar el cmdlet **Reset-CsPoolRegistrarState –ResetType QuorumLossRecovery** para permitir que el grupo se recupere de esta pérdida de cuórum en el grupo de enrutamiento y pueda progresar. Para obtener más información sobre cómo usar este cmdlet, consulte [RESET-CsPoolRegistrarState](https://docs.microsoft.com/powershell/module/skype/Reset-CsPoolRegistrarState).

<div>


> [!NOTE]  
> Puesto que Lync Server usa la base de datos principal de SQL como testigo, si cierra la base de datos principal y cambia a la copia reflejada, y cierra los suficientes servidores frontales para que no haya suficiente ejecución según la tabla anterior, todo el grupo se cerrará. Para obtener más información, consulte <A href="http://go.microsoft.com/fwlink/?linkid=393672">testigo de creación de reflejo de base de datos</A>.



</div>

</div>

<div>

## <a name="pool-level-quorum-loss"></a>Pérdida de cuórum en el grupo de servidores

Para que un grupo de servidores front-end funcione, no puede estar en pérdida de quórum en el nivel de grupo. Si el número de servidores que se ejecutan está por debajo del nivel funcional, como se muestra en la tabla siguiente, el resto de los servidores del grupo detendrán todos los servicios de Lync Server. Tenga en cuenta que los números de la tabla siguiente suponen que los servidores de servicios de fondo del grupo se están ejecutando.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Número total de servidores front-end en el grupo</th>
<th>Cantidad de servidores que es preciso que estén en ejecución para que el grupo funcione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>2</p></td>
<td><p>1</p></td>
</tr>
<tr class="even">
<td><p>3-4</p></td>
<td><p>2 cualesquiera</p></td>
</tr>
<tr class="odd">
<td><p>5-6</p></td>
<td><p>3 cualesquiera</p></td>
</tr>
<tr class="even">
<td><p>7</p></td>
<td><p>4 cualesquiera</p></td>
</tr>
<tr class="odd">
<td><p>8-9</p></td>
<td><p>4 cualesquiera de los primeros 7 servidores</p></td>
</tr>
<tr class="even">
<td><p>10-12</p></td>
<td><p>5 cualesquiera de los primeros 9 servidores</p></td>
</tr>
</tbody>
</table>


En la tabla anterior, los "primeros servidores" son los servidores que aparecieron primero, en orden cronológico, cuando se inició el grupo por primera vez. Para determinar estos servidores, puede usar el cmdlet **Get-CsComputer** con la opción **– PoolFqdn** . Este cmdlet le mostrará los servidores en el orden en el que aparecen en la topología; los que se encuentran en la parte superior de la lista son los primeros servidores.

</div>

<div>

## <a name="front-end-pools-with-two-front-end-servers"></a>Pools front end con dos servidores front-end

No se recomienda implementar un grupo de servidores front-end que contenga solo dos servidores front-end. Si alguna vez necesita implementar ese grupo, siga estas instrucciones:

  - Si uno de los dos servidores de solicitudes de cliente deja de funcionar, debe intentar volver a ponerlo en marcha tan pronto como pueda. Del mismo modo, si necesita actualizar uno de los dos servidores, vuelva a ponerlo en línea tan pronto como termine la actualización.

  - Si, por algún motivo, necesita detener los dos servidores en algún momento, realice lo siguiente cuando termine el tiempo de inactividad del grupo:
    
      - Lo mejor es reiniciar ambos servidores front-end al mismo tiempo.
    
      - Si no se pueden reiniciar los dos servidores al mismo tiempo, será necesario ponerlos en funcionamiento nuevamente en el orden inverso al orden en que se detuvieron.
    
      - Si no puede hacer una copia de seguridad en ese orden, use el siguiente cmdlet antes de volver a poner el grupo de servidores:.
        
            Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery -PoolFQDN <FQDN>

</div>

<div>

## <a name="additional-steps-to-ensure-pools-are-functional"></a>Pasos adicionales para garantizar que los grupos sean funcionales

Es necesario tener en cuenta algunos otros factores a fin de asegurarse de que los grupos de servidores front-end sigan siendo funcionales.

  - Al mover usuarios al grupo por primera vez, asegúrese de que al menos tres de los servidores front-end se estén ejecutando.

  - Si establece una relación de emparejamiento entre este grupo y otro grupo para fines de recuperación ante desastres, después de establecer dicha relación, debe asegurarse de que este grupo tenga tres servidores front-end ejecutándose de forma simultánea en algún momento para sincronizar correctamente datos con el grupo de copias de seguridad. Para obtener más información sobre el emparejamiento de bloqueos y las características de recuperación ante desastres, vea [planear la alta disponibilidad y la recuperación ante desastres en Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).

</div>

</div>

<div>

## <a name="improving-the-reliability-of-pool-upgrades"></a>Mejorar la confiabilidad de las actualizaciones de grupos

Cuando necesite actualizar o aplicar revisiones a los servidores de un grupo de servidores front-end, siga el flujo de trabajo que se muestra en [actualizar o actualizar los servidores front-end de Lync Server 2013](lync-server-2013-upgrade-or-update-front-end-servers.md)y las siguientes pautas:

  - Al pasar de un dominio de actualización a otro para actualizaciones (siguiendo el flujo de trabajo de actualización [o actualización de los servidores front-end de Lync Server 2013](lync-server-2013-upgrade-or-update-front-end-servers.md)), deberá usar el cmdlet **Get-CsPoolUpgradeReadinessState** y comprobar el estado de lista. Agregar una espera de 20 minutos entre cada dominio de actualización después de que se encuentre "listo" hará que las actualizaciones sean más confiables. Si no está **listo** durante los 20 minutos, reinicie el temporizador de 20 minutos. Además, puede ejecutar el cmdlet **Get-CsPoolFabricState** antes y después de iniciar el intervalo de 20 minutos y asegurarse de que no haya cambios en las principales y secundarias de los grupos de enrutamiento.

  - No pase al siguiente dominio de actualización si alguno de los servidores del último dominio de actualización revisada se bloquea o no se reinicia. Esto también se aplica si no se puede iniciar ninguno de los servidores dentro de una actualización. Ejecute **Get-CsPoolFabricState** para asegurarse de que todos los grupos de enrutamiento tienen como principal y como mínimo un secundario; Esto confirmará si todos los usuarios tienen servicio.

  - Si algunos usuarios tienen servicio y otros no, ejecute **Get-CsPoolFabricState** con la opción – verboso para comprobar si hay grupos de enrutamiento con réplicas que faltan. No reinicie todo el grupo como primer paso de solución de problemas. Para obtener más información sobre este cmdlet, vea [Get-CsPoolFabricState](https://docs.microsoft.com/powershell/module/skype/Get-CsPoolFabricState).

  - Asegúrese de que todas las instancias del visor de eventos o de las ventanas de monitor de rendimiento estén cerradas para que Windows fabric se instale o desinstale.

</div>

<div>

## <a name="changing-a-front-end-pools-configuration"></a>Cambiar la configuración del grupo de servidores front-end

Cada vez que agregue servidores front-end a un grupo, o quítelos del grupo y, a continuación, publique la nueva topología, siga estas pautas:

  - Una vez publicada la nueva topología, debe reiniciar cada servidor front-end en el grupo. Reinícielos de uno en uno.

  - Si se ha desactivado todo el grupo durante el cambio de configuración, ejecute el siguiente cmdlet una vez publicada la nueva topología:
    
        Reset-CsPoolRegistrarState -PoolFQDN <PoolFQDN> -ResetType ServiceReset

Si se produce un error en un servidor front-end y es improbable que se cambie por unos días o más, quite el servidor de la topología. Agregue el nuevo servidor front-end a la topología cuando esté disponible de nuevo.

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

