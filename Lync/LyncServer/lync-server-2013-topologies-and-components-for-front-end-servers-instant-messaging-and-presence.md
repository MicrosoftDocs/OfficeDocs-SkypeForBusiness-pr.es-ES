---
title: "Topologías y componentes de servidores front-end, mensajería instantánea y presencia"
TOCTitle: Topologías y componentes para los servidores front-end, la mensajería instantánea y la presencia
ms:assetid: f08ce7a1-d14e-4a54-9771-a82c870658bf
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg412996(v=OCS.15)
ms:contentKeyID: 48277127
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Topologías y componentes para los servidores front-end, la mensajería instantánea y la presencia en Lync Server 2013

 

_**Última modificación del tema:** 2016-12-08_

Los únicos componentes necesarios para la mensajería instantánea (MI) y el estado de presencia son:

  - Los servidores front-end o Standard Edition de la organización. Las funciones de mensajería instantánea y presencia siempre están habilitadas en estos servidores.

  - Un equilibrador de carga, si se dispone de un Grupo de servidores front-end de Enterprise Edition. Si desea más información, vea [Requisitos del equilibrio de carga de Lync Server 2013](lync-server-2013-load-balancing-requirements.md).

## Planificación de la implementación de grupos de servidores front-end

En Lync Server 2013, la arquitectura de Grupo de servidores front-end ha cambiado y estos cambios afectan a la planificación y el mantenimiento de Grupos de servidores front-end.

Se recomienda que todos los Grupos de servidores front-end de Enterprise Edition incluyan al menos tres servidores front-end. En Lync Server, la arquitectura de Grupos de servidores front-end utiliza un modelo de sistemas distribuido, en el que los datos de cada usuario se guardan en tres servidores front-end del grupo. Si desea más información sobre esta nueva arquitectura, consulte [Cambios en la topología en Lync Server 2013](lync-server-2013-topology-changes.md).

Si no quiere implementar tres Enterprise EditionServidores front-end y quiere obtener las características de recuperación ante desastres, le recomendamos usar Lync ServerStandard Edition y crear dos grupos de servidores con una relación de emparejamiento para copia de seguridad. De este modo, contará con una solución de recuperación ante desastres con solo dos servidores. Para más información sobre las topologías y las características de alta disponibilidad y recuperación ante desastres, vea [Planeación de alta disponibilidad y recuperación ante desastres en Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).

## Planificación de la administración de los grupos de servidores front-end

Para los Grupos de servidores front-end, siga las instrucciones descritas en esta sección.

## Comprobar que los grupos de servidores sean funcionales

Con el nuevo modelo distribuido para los Grupos de servidores front-end, para que el grupo de servidores funcione debe estar en ejecución un determinado número de servidores de un grupo. Hay dos modelos de pérdidas para un grupo de servidores.

  - Pérdida de quórum en el nivel del grupo de enrutamiento, provocada por una cantidad insuficiente de servidores de réplicas para un determinado grupo de enrutamiento. Un grupo de enrutamiento es una agregación de un conjunto de usuarios hospedados en el grupo de servidores. Cada grupo de enrutamiento tiene tres réplicas en el grupo: una principal y dos secundarias.

  - Pérdida de quórum en el nivel del grupo de servidores, que ocurre cuando no hay una cantidad suficiente de servidores semilla en ejecución en el grupo.

## Pérdida de quórum en el nivel del grupo de enrutamiento

La primera vez que inicia un nuevo Grupo de servidores front-end, es fundamental que el 85 % de los servidores estén en funcionamiento, tal como se muestra en la tabla siguiente. Si hay menos servidores en ejecución, es posible que los servicios queden interrumpidos en el estado de inicio y que el grupo no se inicie.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Cantidad total de servidores en el grupo</th>
<th>Cantidad de servidores que deben estar en ejecución para que el grupo se inicie por primera vez</th>
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
<td><p>8</p></td>
<td><p>6</p></td>
</tr>
<tr class="even">
<td><p>9</p></td>
<td><p>7</p></td>
</tr>
<tr class="odd">
<td><p>10</p></td>
<td><p>8</p></td>
</tr>
<tr class="even">
<td><p>11</p></td>
<td><p>9</p></td>
</tr>
<tr class="odd">
<td><p>12</p></td>
<td><p>10</p></td>
</tr>
</tbody>
</table>


Cada vez subsiguiente que se inicie el grupo, el 85 % de los servidores deben iniciarse (tal como se muestra en la tabla anterior). Si no se puede iniciar esta cantidad de servidores (pero se puede iniciar una cantidad de servidores suficiente para que no haya pérdida de quórum en el nivel del grupo), puede usar el cmdlet **Reset-CsPoolRegistrarState –ResetType QuorumLossRecovery** para permitir que el grupo se recupere de esta pérdida de quórum en el nivel del grupo de enrutamiento y pueda progresar. Para más información sobre cómo usar este cmdlet, vea [Reset-CsPoolRegistrarState](https://docs.microsoft.com/en-us/powershell/module/skype/Reset-CsPoolRegistrarState).


> [!NOTE]
> Dado que Lync Server usa la base de datos SQL principal como testigo, si apaga la base de datos principal, cambia a la copia reflejada y apaga una cantidad suficiente de Servidores front-end de modo que no haya los suficientes en ejecución de acuerdo con la tabla anterior, todo el grupo de servidores quedará inactivo. Para más información, vea <A href="http://go.microsoft.com/fwlink/?linkid=393672">Testigo de creación de reflejo de la base de datos</A>.



## Pérdida de quórum en el nivel del grupo de servidores

Para que un Grupo de servidores front-end funcione totalmente, no puede presentar una pérdida de quórum en el nivel del grupo de servidores. Si la cantidad de servidores en ejecución está por debajo del nivel de funcionamiento (tal como se muestra en la tabla siguiente), los servidores restantes del grupo detendrán todos los servicios de Lync Server. Tenga en cuenta que en los números de la siguiente tabla se asume que los servidores back-end del grupo de servidores están en ejecución.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Número total de servidores front-end de un grupo</th>
<th>Número de servidores que deben estar en ejecución para que el grupo funcione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>2</p></td>
<td><p>1</p></td>
</tr>
<tr class="even">
<td><p>3 -4</p></td>
<td><p>2 cualesquiera</p></td>
</tr>
<tr class="odd">
<td><p>5 -6</p></td>
<td><p>3 cualesquiera</p></td>
</tr>
<tr class="even">
<td><p>7</p></td>
<td><p>4 cualesquiera</p></td>
</tr>
<tr class="odd">
<td><p>8 -9</p></td>
<td><p>4 cualesquiera de los primeros 7 servidores</p></td>
</tr>
<tr class="even">
<td><p>10 -12</p></td>
<td><p>5 cualesquiera de los primeros 9 servidores</p></td>
</tr>
</tbody>
</table>


En la tabla anterior, los "primeros servidores" son los servidores que aparecieron primero, en orden cronológico, cuando se inició el grupo por primera vez. A fin de determinar cuáles son estos servidores, puede usar el cmdlet **Get-CsComputer** con la opción **–PoolFqdn**. Este cmdlet le mostrará los servidores en el orden en el que aparecen en la topología; los que se encuentran en la parte superior de la lista son los primeros servidores.

## Grupos de servidores front-end con dos servidores front-end

No recomendamos implementar un grupo de servidores front-end que contenga solo dos servidores front-end. Si, aún así, necesita implementar un grupo de este tipo, tenga en cuenta lo siguiente:

  - Si uno de los servidores front-end fallara, intente recuperarlo lo antes posible. Del mismo modo, si necesita actualizar uno de los dos servidores, vuelva a ponerlo en marcha tan pronto como termine la actualización.

  - Si, por algún motivo, necesita detener los dos servidores en algún momento, realice las operaciones siguientes cuando termine el período de inactividad:
    
      - Se recomienda reiniciar ambos servidores front-end al mismo tiempo.
    
      - Si no se pueden reiniciar los dos servidores al mismo tiempo, deberá ponerlos en marcha en el orden inverso al orden en que se detuvieron.
    
      - Si no puede ponerlos en funcionamiento en ese orden, utilice el siguiente cmdlet antes de iniciarlo:
        
            Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery -PoolFQDN <FQDN>

## Pasos adicionales para comprobar si los grupos de servidores son funcionales

Debe tener en cuenta algunos otros factores a fin de asegurarse de que los Grupos de servidores front-end sigan siendo funcionales.

  - Cuando traslade usuarios al grupo por primera vez, compruebe que al menos tres de los servidores front-end están en funcionamiento.

  - Si establece una relación de emparejamiento entre este grupo de servidores y otro con fines de recuperación ante desastres, después de establecer dicha relación, deberá asegurarse de que este grupo tiene tres servidores front-end ejecutándose simultáneamente en algún momento para sincronizar correctamente los datos con el servidor de copias de seguridad. Si desea más información sobre el emparejamiento de grupos de servidores y las características de recuperación ante desastres, consulte [Planeación de alta disponibilidad y recuperación ante desastres en Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).

## Mejorar la confiabilidad de las actualizaciones del grupo de servidores

Cuando deba actualizar los servidores de un Grupo de servidores front-end o aplicar una revisión, siga el flujo de trabajo propuesto en [Actualización o mejora de los servidores front-end en Lync Server 2013](lync-server-2013-upgrade-or-update-front-end-servers.md) y las siguientes instrucciones:

  - Cuando pase de un dominio de actualización a otro por actualizaciones (siguiendo el flujo de trabajo descrito en [Actualización o mejora de los servidores front-end en Lync Server 2013](lync-server-2013-upgrade-or-update-front-end-servers.md)), deberá usar el cmdlet **Get-CsPoolUpgradeReadinessState** y comprobará el estado de Listo. Si agrega un tiempo de espera de 20 minutos entre cada dominio de actualización una vez que se llega a "Listo", las actualizaciones serán más confiables. Si durante estos 20 minutos el estado figura como **No está listo**, reinicie el temporizador de 20 minutos. Asimismo, puede ejecutar el cmdlet **Get-CsPoolFabricState** antes y después de que empiece el intervalo de 20 minutos y asegurarse de que no haya cambios en los grupos de enrutamiento principales y secundarios.

  - No proceda con el dominio de actualización siguiente si alguno de los servidores del último dominio de actualización revisado está interrumpido o no se reinició. Esto se aplica también si no se puede iniciar alguno de los servidores dentro de la actualización. Ejecute **Get-CsPoolFabricState** para asegurarse de que todos los grupos de enrutamiento tengan una réplica principal y al menos una secundaria; de esta forma, confirmará si todos los usuarios tienen servicio.

  - Si algunos usuarios tienen servicio y otros no, ejecute **Get-CsPoolFabricState** con la opción –Verbose para buscar grupos de enrutamiento a los que les falten réplicas. No reinicie todo el grupo de servidores como el primer paso de solución de problemas. Para más información sobre este cmdlet, vea [Get-CsPoolFabricState](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsPoolFabricState).

  - Asegúrese de que todas las instancias de las ventanas del Visor de eventos o del Monitor de rendimiento estén cerradas para las instalaciones y desinstalaciones de Windows Fabric.

## Modificación de la configuración de un grupo de servidores front-end

Siempre que agregue servidores front-end a un grupo, o los quite de un grupo, y publique la nueva topología, tenga en cuenta lo siguiente:

  - Después de publicar una topología nueva, debe reiniciar todos los Servidor front-end del grupo. Reinícielos de uno en uno.

  - Si el grupo entero ha estado inactivo durante el cambio de la configuración, ejecute el siguiente cmdlet después de publicar la topología nueva:
    
        Reset-CsPoolRegistrarState -PoolFQDN <PoolFQDN> -ResetType ServiceReset

Si se produce un error en un servidor front-end y no es probable que se sustituya durante unos días, quite el servidor de la topología. Y cuando el nuevo servidor front-end esté disponible, agréguelo a la topología.

