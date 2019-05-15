---
title: Configuración de intervalos de puertos y una directiva de calidad de servicio para los servidores de conferencia, aplicación y mediación
ms.reviewer: ''
ms:assetid: 4d6eaa5d-0127-453f-be6a-e55384772d83
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204872(v=OCS.15)
ms:contentKeyID: 48184074
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: En este artículo se describe cómo configurar intervalos de puertos y una directiva de calidad de servicio para los servidores de conferencia, aplicación y mediación.
ms.openlocfilehash: 29685029580271462e090da7fa82cd8d416e83e1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33913366"
---
# <a name="configuring-port-ranges-and-a-quality-of-service-policy-for-your-conferencing-application-and-mediation-servers"></a>Configuración de intervalos de puertos y una directiva de calidad de servicio para los servidores de conferencia, aplicación y mediación

En este artículo se describe cómo configurar intervalos de puertos y una directiva de calidad de servicio para los servidores de conferencia, aplicación y mediación.

## <a name="configure-port-ranges"></a>Configurar intervalos de puertos

Para implementar la calidad de servicio, debe configurar los intervalos de puertos idénticos de audio, vídeo y uso compartido en sus servidores de conferencia, aplicación y mediación; de aplicaciones Además, los intervalos de puertos no deben se superponen en modo alguno. Para usar un ejemplo sencillo, suponga que utiliza puertos 10000 a través de 10999 para vídeo en sus servidores de conferencia. Eso significa que también debe reservar puertos 10000 a través de 10999 para vídeo en sus servidores de aplicación y mediación. Si no lo hace, QoS no funcionarán como se esperaba.

De forma similar, supongamos que reservar puertos 10000 a través de 10999 para vídeo, pero a continuación, los puertos de reserva 10500 a través de 11999 para el audio. Esto puede crear problemas de calidad de servicio, debido a que el puerto de rangos de la superposición. Con QoS, cada modalidad debe tener un conjunto único de puertos: Si utiliza puertos 10000 a través de 10999 para vídeo, a continuación, tendrá que utilizar un rango diferente (por ejemplo, 11000 a 11999, para el audio).

De forma predeterminada, los intervalos de puertos de audio y vídeo no se superponen en Skype para Business Server; Sin embargo, los intervalos de puertos asignan a la aplicación de uso compartido de la superposición con ambos los intervalos de puertos de audio y vídeo. (Que, a su vez, significa que ninguno de estos intervalos son único). Puede comprobar los intervalos de puertos existente para los servidores de mediación, conferencia y aplicaciones mediante la ejecución de los siguientes tres comandos desde dentro de la Skype para Shell de administración de servidor empresarial:

    Get-CsService -ConferencingServer | Select-Object Identity, AudioPortStart, AudioPortCount, VideoPortStart, VideoPortCount, AppSharingPortStart, AppSharingPortCount
    
    Get-CsService -ApplicationServer | Select-Object Identity, AudioPortStart, AudioPortCount
    
    Get-CsService -MediationServer | Select-Object Identity, AudioPortStart, AudioPortCount

> [!WARNING]  
> Como puede ver en los comandos anteriores, cada tipo de puerto (audio, vídeo y uso compartido de aplicaciones) se asigna a dos valores de propiedad independiente: el inicio de puerto y el número de puerto. El inicio de puerto indica el primer puerto utilizado para esa modalidad; Por ejemplo, si el inicio de puertos de audio es igual a 50000 que significa que el primer puerto utilizado para el tráfico de audio es puerto 50000. Si el recuento de puertos de audio es 2 (que no es un valor válido, pero se utiliza aquí con fines ilustrativos), que significa que sólo dos puertos que se asignan para el audio. Si el primer puerto es el puerto 50000 y hay un total de dos puertos, significa que el segundo puerto debe ser el puerto 50001 (puerto rangos tienen que ser contiguos). Como resultado, el intervalo de puertos para el audio sería puertos 50000 a través de 50001, ambos inclusive.<BR><br>Tenga en cuenta también que servidor de aplicaciones y servidor de mediación sólo admiten QoS de audio; no es necesario cambiar vídeo o uso compartido de puertos de los servidores de aplicaciones o de los servidores de mediación de aplicaciones.

Si ejecuta los tres comandos anteriores, verá que los que el puerto predeterminado valores de Skype para Business Server se configuran como este:

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Propiedad</th>
<th>Servidor de conferencia</th>
<th>Servidor de aplicaciones</th>
<th>Servidor de mediación</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>AudioPortStart</p></td>
<td><p>49152</p></td>
<td><p>49152</p></td>
<td><p>49152</p></td>
</tr>
<tr class="even">
<td><p>AudioPortCount</p></td>
<td><p>8348</p></td>
<td><p>8348</p></td>
<td><p>8348</p></td>
</tr>
<tr class="odd">
<td><p>VideoPortStart</p></td>
<td><p>57501</p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
<tr class="even">
<td><p>VideoPortCount</p></td>
<td><p>8034</p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
<tr class="odd">
<td><p>ApplicationSharingPortStart</p></td>
<td><p>49152</p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
<tr class="even">
<td><p>ApplicationSharingPortCount</p></td>
<td><p>16383</p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
</tbody>
</table>

Como se indicó anteriormente, al configurar Skype para los puertos de servidor empresarial para QoS, debe asegurarse de que: 1) configuración de puertos de audio es idénticos a través de la suya, los servidores de conferencia, aplicación y mediación; y, 2) no se superponen los intervalos de puertos. Si examina atentamente la tabla anterior, verá que los intervalos de puertos son idénticos a través de los tipos de servidores de tres. Por ejemplo, se establece el puerto de audio inicio al puerto 49152 en cada tipo de servidor y el número total de puertos reservados para el audio en cada servidor también es idéntico: 8348. Sin embargo, el puerto de rangos de la superposición: puertos de sonido de iniciarse en el puerto 49152 pero, por lo que hacen los puertos reservados para uso compartido de aplicaciones. Para hacer un uso óptimo de calidad de servicio, uso compartido de aplicaciones debe volver a configurar para usar un intervalo de puerto único. Por ejemplo, podría configurar uso compartido de aplicaciones para iniciarse en el puerto 40803 y usar 8348 puertos. (¿Por qué 8348 puertos? Si agrega esos valores juntos--40803 + 8348--que significa que el uso compartido de aplicaciones va a usar puertos 40803 a través del puerto 49150. Debido a que los puertos de audioconferencias no empiezan hasta el puerto 49152, ya no tendrá ningún superpuestas intervalos de puertos.)

Después de haber seleccionado el nuevo intervalo de puertos para uso compartido de aplicaciones, puede realizar el cambio mediante el cmdlet Set-CsConferencingServer. Este cambio no es necesario realizar en los servidores de aplicaciones o en los servidores de mediación, debido a que estos servidores no controlan el tráfico de uso compartido de aplicaciones. Sólo debe cambiar los valores de puerto en estos servidores si decide reasignar los puertos usados para el tráfico de audio.

Para modificar los valores de puerto para la aplicación de uso compartido en un único servidor de conferencia, ejecute un comando similar a este desde dentro de la Skype para Shell de administración de servidor empresarial:

    Set-CsConferenceServer -Identity ConferencingServer:atl-cs-001.litwareinc.com -AppSharingPortStart 40803 -AppSharingPortCount 8348

Si desea realizar estos cambios en todos los servidores de conferencia, puede ejecutar este comando en su lugar:

    Get-CsService -ConferencingServer | ForEach-Object {Set-CsConferenceServer -Identity $_.Identity -AppSharingPortStart 40803 -AppSharingPortCount 8348}

Después de cambiar la configuración de puerto, debe detener y reiniciar cada servicio afectado por los cambios.

No es obligatorio que los servidores de conferencia, servidores de aplicaciones y los servidores de mediación comparten el mismo intervalo puerto exacto; el requisito de true sólo es que se retiradas intervalos de puertos único en todos los servidores. Sin embargo, normalmente será más fácil si usa el mismo conjunto de puertos en todos los servidores de administración.

## <a name="configure-a-quality-of-service-policy-in-skype-for-business-server-for-your-conferencing-application-and-mediation-servers"></a>Configurar una directiva de calidad de servicio en Skype para Business Server para los servidores de conferencia, aplicación y mediación

Configuración de intervalos de puertos facilita el uso de calidad de servicio al garantizar que todo el tráfico de un tipo especificado (por ejemplo, todos los de tráfico de audio) se transfiere a través del mismo conjunto de puertos. Esto facilita el sistema identificar y marcar un paquete determinado: si el puerto 49152 está reservado para el tráfico de audio, entonces cualquier paquete que viaja a través del puerto 49152 se puede marcar con un código DSCP que indica que se trata de un paquete de audio. A su vez, esto permite que los enrutadores identificar el paquete como un paquete de audio y asignarle mayor prioridad que los paquetes sin marcar (por ejemplo, los paquetes que se usa para copiar un archivo de un servidor a otro).

Sin embargo, restringir simplemente un conjunto de puertos a un tipo específico de tráfico no se produce en paquetes que viajan a través de esos puertos se marquen con el código DSCP adecuado. Además de definir intervalos de puertos, también debe crear directivas de calidad de servicio que especifican el código DSCP para asociarse con cada intervalo de puertos. Para Skype para Business Server, que normalmente significa crear dos directivas: uno para audio y otro para vídeo.

Calidad de las directivas de servicio son más fácilmente creado y administrado, mediante el uso de directiva de grupo. (Estas directivas mismas también pueden crearse mediante el uso de directivas de seguridad local. Sin embargo, que requiere que repita el mismo procedimiento en cada equipo.) El conjunto inicial de las directivas de QoS (uno para el audio) y otro para vídeo debe aplicarse sólo en Skype para los equipos de servidor empresarial que ejecuta el servidor de conferencia, el servidor de aplicaciones o los servicios de servidor de mediación. Si todos estos equipos se encuentran en la misma unidad organizativa de Active Directory, simplemente puede asignar el nuevo objeto de directiva de grupo (GPO) para esa unidad organizativa. Como alternativa, puede realizar otros pasos para dirigir la nueva directiva a los equipos especificados; Por ejemplo, puede colocar los equipos adecuados en un grupo de seguridad, a continuación, usar el filtrado de seguridad de directiva de grupo para aplicar el GPO sólo a ese grupo de seguridad.

Para crear una directiva de calidad de servicio para la administración de audio, inicie sesión en un equipo donde se ha instalado Administración de directivas de grupo. Abra Administración de directivas de grupo (haga clic en **Inicio**, elija **Herramientas administrativas**y, a continuación, haga clic en **Administración de directivas de grupo**) y, a continuación, complete el siguiente procedimiento:

1.  En administración de directivas de grupo, busque el contenedor donde se debe crear la nueva directiva. Por ejemplo, si todos los su Skype para equipos Business Server se encuentra en una unidad organizativa denominada Skype para Business Server, se debe crear la nueva directiva en el Skype para la unidad organizativa de servidor empresarial.

2.  Haga clic en el contenedor adecuado y, a continuación, haga clic en **crear un GPO en este dominio y vincularlo aquí**.

3.  En el cuadro de diálogo **Nuevo GPO** , escriba un nombre para el nuevo objeto de directiva de grupo en el cuadro **nombre** (por ejemplo, **Skype para QoS de servidor empresarial**) y, a continuación, haga clic en **Aceptar**.

4.  Haga clic en la directiva recién creada y, a continuación, haga clic en **Editar**.

5.  En el Editor de administración de directiva de grupo, expanda **Configuración del equipo**, expanda **directivas**, expanda **Configuración de Windows**, haga clic en **QoS basada en directiva de**y, a continuación, haga clic en **Crear nueva directiva**.

6.  En el cuadro de diálogo de **QoS basada en directiva** , en la página de apertura, escriba un nombre para la nueva directiva (por ejemplo, **Skype para Business Server QoS**) en el cuadro **nombre** . Seleccione **Especificar el valor de DSCP** y establezca el valor **46**. Deje **Especificar velocidad de aceleración saliente** no está seleccionada y, a continuación, haga clic en **siguiente**.

7.  En la página siguiente, asegúrese de que **todas las aplicaciones** está activada y, a continuación, haga clic en **siguiente**. Esto simplemente garantiza que todas las aplicaciones coincidirá con paquetes desde el intervalo de puertos especificado con el código DSCP especificado.

8.  En la tercera página, asegúrese de que ambos **cualquier dirección IP de origen y cualquier dirección IP de destino** están seleccionados y, a continuación, haga clic en **siguiente**. Estos dos valores Asegúrese de que se administrarán los paquetes independientemente de qué equipo (dirección IP) enviado esos paquetes y qué equipo (dirección IP) recibirán los paquetes.

9.  En la cuarta página, seleccione **TCP y UDP** en la lista desplegable **Seleccione el protocolo que se aplica esta directiva de QoS** . TCP (Protocolo de Control de transmisión) y UDP (Protocolo de datagramas de usuario) son los dos protocolos de red más utilizados por Skype para Business Server y sus aplicaciones de cliente.

10. Bajo el encabezado, **Especifique el número de puerto de origen**, seleccione **desde este intervalo o el puerto de origen**. En el cuadro de texto que lo acompaña, escriba el intervalo de puertos reservado para las transmisiones de audioconferencias. Por ejemplo, si ha reservado puertos 49152 a través de puertos 57500 para el tráfico de audio, escriba el intervalo de puertos con este formato: **49152:57500**. Haga clic en **Finalizar**.

> [!NOTE]  
> El valor de DSCP de 46 es algo arbitrario: aunque DSCP 46 a menudo se usa para marcar los paquetes de audio, no es necesario usar 46 DSCP para comunicaciones de audio. Si ya ha implementado QoS y están usando un código DSCP diferente para el audio (por ejemplo, DSCP 40), debe configurar la directiva de calidad de servicio para usar ese mismo código (es decir, 40 para audio). Si ahora va a implementar la calidad de servicio, a continuación, se recomienda que utilice DSCP 46 para el audio, simplemente porque ese valor normalmente se utiliza para marcar los paquetes de audio.

Después de haber creado la directiva de QoS para el tráfico de audio, a continuación, debe crear una segunda directiva para el tráfico de vídeo (y, opcionalmente, una tercera directiva para administrar el tráfico de uso compartido de aplicaciones). Para crear una directiva para el vídeo, siga el mismo procedimiento básico seguido al crear la directiva de audio, realizar las siguientes sustituciones:

  - Use un nombre de directiva diferente (y único) (por ejemplo, **Skype para vídeo de servidor empresarial**).

  - Establezca el valor DSCP a **34** en lugar de 46. (Tenga en cuenta que no es necesario usar un valor DSCP de 34. El único requisito es usar un valor DSCP diferente para el vídeo que se utiliza para el audio.)

  - Usar el intervalo de puerto configurado anteriormente para el tráfico de vídeo. Por ejemplo, si lo ha reservado puertos 57501 y 65535 para vídeo, establezca el intervalo de puertos a la siguiente: **57501:65535**.

Si decide crear una directiva para administrar el tráfico de uso compartido de aplicaciones, debe crear una tercera Directiva, sustituyendo lo siguiente:

  - Use un nombre de directiva diferente (y único) (por ejemplo, **Skype para compartir aplicaciones de servidor de negocio**).

  - Establezca el valor de DSCP en **24** en lugar de 46. (De nuevo, no es necesario usar un valor DSCP de 24. El único requisito es que usar un valor DSCP diferente para uso compartido de aplicaciones que usa para el audio o de vídeo.)

  - Usar el intervalo de puerto configurado anteriormente para el tráfico de vídeo. Por ejemplo, si lo ha reservado puertos 40803 y 49151 para uso compartido de aplicaciones, puede establecer el intervalo de puertos a la siguiente: **40803:49151**.

Las nuevas directivas que ha creado no tendrán efecto hasta que se ha actualizado la directiva de grupo en su Skype para equipos servidor empresarial. Aunque la directiva de grupo se actualiza periódicamente por sí misma, se puede forzar una actualización inmediata si se ejecuta el siguiente comando en cada equipo en el que se tenga que actualizar la directiva de grupo:

    Gpupdate.exe /force

Este comando se puede ejecutar desde dentro de la Skype para Shell de administración de servidor empresarial o desde cualquier ventana de comandos que se ejecuta con credenciales de administrador. Para abrir una ventana de comandos con las credenciales del administrador, haga clic en **Inicio**, haga clic con el botón derecho en **Símbolo del sistema** y, a continuación, haga clic en **Ejecutar como administrador**.

Para comprobar que se han aplicado las nuevas directivas de QoS, haga lo siguiente:

1.  En un Skype para equipo Business Server, haga clic en **Inicio**y, a continuación, haga clic en **Ejecutar**.

2.  En el cuadro de diálogo **Ejecutar** , escriba **regedit**y, a continuación, presione ENTRAR.

3.  En el Editor del registro, expanda **equipo**, expanda **HKEY\_LOCAL\_máquina**, expanda **SOFTWARE**, expanda **directivas**, expanda **Microsoft**, expanda **Windows**y, a continuación, haga clic en **QoS**. En **QoS** debería ver las claves del registro para cada una de las directivas de QoS que acaba de crear. Por ejemplo, si ha creado dos nuevas directivas (uno con nombre Skype para QoS de Audio de servidor empresarial) y el otro con nombre Skype para QoS de vídeo de servidor empresarial, debería ver las entradas del registro de Skype para QoS de Audio de servidor empresarial y Skype para QoS de vídeo de servidor empresarial.

Para ayudar a garantizar que los paquetes de red están marcados con el valor DSCP adecuado, también debe crear una nueva entrada del registro en cada equipo completando el procedimiento siguiente:

1.  Haga clic en  **Inicio ** y en  **Ejecutar **.

2.  En el cuadro de diálogo **Ejecutar** , escriba **regedit**y, a continuación, presione ENTRAR.

3.  En el Editor del registro, expanda **HKEY\_LOCAL\_máquina**, expanda **SYSTEM**, expanda **CurrentControlSet**, expanda **Servicios**y, a continuación, expanda **Tcpip**.

4.  Secundario **Tcpip**, elija **nuevo**y, a continuación, haga clic en **clave**. Una vez creada la nueva clave del registro, escriba **QoS**y, a continuación, presione ENTRAR para cambiar el nombre de la clave.

5.  Secundario **QoS**, elija **nuevo**y, a continuación, haga clic en **Valor de tipo String**. Una vez creado el nuevo valor del registro, escriba **no use NLA**y, a continuación, presione ENTRAR para cambiar el nombre del valor.

6.  Haga doble clic en **no usa NLA**. En el cuadro de diálogo **Editar cadena** , escriba **1** en el cuadro **datos de valor** y, a continuación, haga clic en **Aceptar**.

7.  Cierre el Editor del registro y reinicie el equipo.
