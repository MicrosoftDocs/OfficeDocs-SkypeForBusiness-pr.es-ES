---
title: Configuración de intervalos de puerto y una directiva de calidad de servicio para los servidores de conferencia, aplicación y mediación
ms.reviewer: ''
ms:assetid: 4d6eaa5d-0127-453f-be6a-e55384772d83
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204872(v=OCS.15)
ms:contentKeyID: 48184074
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: En este artículo se describe cómo configurar intervalos de puertos y una directiva de calidad de servicio para los servidores de conferencias, aplicaciones y mediación.
ms.openlocfilehash: e0bd6092792a9ed813aadecc004f58830bc5b133
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279468"
---
# <a name="configuring-port-ranges-and-a-quality-of-service-policy-for-your-conferencing-application-and-mediation-servers"></a>Configuración de intervalos de puerto y una directiva de calidad de servicio para los servidores de conferencia, aplicación y mediación

En este artículo se describe cómo configurar intervalos de puertos y una directiva de calidad de servicio para los servidores de conferencias, aplicaciones y mediación.

## <a name="configure-port-ranges"></a>Configurar intervalos de puertos

Para implementar la calidad de servicio, debe configurar los intervalos de puertos idénticos para el audio, el vídeo y el uso compartido de aplicaciones en sus servidores de conferencias, aplicaciones y mediación. Además, esos intervalos de puertos no deben superponerse de ninguna manera. Para usar un ejemplo sencillo, suponga que usa los puertos 10000 a 10999 para vídeo en los servidores de conferencia. Eso significa que también debe reservar los puertos 10000 a 10999 para vídeo en su aplicación y servidores de mediación. De lo contrario, QoS no funcionará de la forma esperada.

De forma similar, suponga que reserva los puertos 10000 a 10999 para video, pero después reserva los puertos 10500 a 11999 para audio. Esto puede crear problemas de calidad de servicio porque los intervalos de puertos se superponen. Con QoS, cada modalidad debe tener un único conjunto de puertos: Si usa los puertos 10000 a 10999 para vídeo, tendrá que usar un intervalo diferente (por ejemplo, 11000 a 11999, para audio).

De forma predeterminada, los intervalos de los puertos de audio y vídeo no se superponen en Skype empresarial Server; sin embargo, los intervalos de puertos asignados al uso compartido de aplicaciones se superponen con los intervalos de puertos de audio y vídeo. (Que, a su vez, significa que ninguno de estos intervalos es único). Puede comprobar los intervalos de puertos existentes para los servidores de conferencia, aplicación y mediación ejecutando los siguientes tres comandos desde el shell de administración de Skype empresarial Server:

    Get-CsService -ConferencingServer | Select-Object Identity, AudioPortStart, AudioPortCount, VideoPortStart, VideoPortCount, AppSharingPortStart, AppSharingPortCount
    
    Get-CsService -ApplicationServer | Select-Object Identity, AudioPortStart, AudioPortCount
    
    Get-CsService -MediationServer | Select-Object Identity, AudioPortStart, AudioPortCount

> [!WARNING]  
> Como puede ver en los comandos anteriores, cada tipo de puerto (audio, vídeo y uso compartido de aplicaciones) tiene asignados dos valores de propiedad distintos: el inicio del puerto y el recuento de puertos. El inicio del puerto indica el primer puerto utilizado para ese modal; por ejemplo, si el inicio del puerto de audio es igual a 50000, significa que el primer puerto que se usa para el tráfico de audio es el puerto 50000. Si el recuento de puertos de audio es 2 (que no es un valor válido, pero se usa aquí con fines de ilustración), eso significa que solo se asignan dos puertos para el audio. Si el primer puerto es el puerto 50000 y hay un total de dos puertos, significa que el segundo puerto debe ser el puerto 50001 (los intervalos de puertos deben ser contiguos). Como resultado, el intervalo de puertos para el audio sería los puertos 50000 a 50001, ambos incluidos.<BR><br>Ten en cuenta que el servidor de aplicaciones y el servidor de mediación solo admiten QoS para el audio; no es necesario cambiar los puertos de uso compartido de vídeo o aplicaciones en los servidores de aplicaciones o servidores de mediación.

Si ejecuta los tres comandos anteriores, verá que los valores de puerto predeterminados para Skype empresarial Server están configurados de la siguiente manera:

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

Como se mencionó anteriormente, al configurar puertos de Skype empresarial Server para QoS, debe asegurarse de que: 1) la configuración del puerto de audio sea idéntica en los servidores de conferencias, aplicaciones y mediación. y 2) los intervalos de puertos no se superponen. Si examina atentamente la tabla anterior, verá que los intervalos de puertos son idénticos en los tres tipos de servidor. Por ejemplo, el puerto de salida de audio se establece en el puerto 49152 en cada tipo de servidor, y el número total de puertos reservados para el audio en cada servidor también es idéntico: 8348. Sin embargo, los intervalos de puertos se superponen: los puertos de audio comienzan en el puerto 49152, pero también hacen que los puertos reservados para uso compartido de aplicaciones. Para hacer uso óptimo de la calidad de servicio, el uso compartido de aplicaciones debe reconfigurarse para que use un intervalo de puertos único. Por ejemplo, puede configurar el uso compartido de aplicaciones para que se inicie en el puerto 40803 y para usar puertos 8348. (¿Por qué 8348 puertos? Si suma esos valores juntos, 40803 + 8348, eso significa que el uso compartido de aplicaciones usará los puertos 40803 a través del puerto 49150. Puesto que los puertos de audio no comienzan hasta el puerto 49152, ya no tendrá intervalos de puertos superpuestos.)

Una vez que haya seleccionado el nuevo intervalo de puertos para el uso compartido de aplicaciones, puede realizar su cambio con el cmdlet Set-CsConferencingServer. No es necesario realizar este cambio en los servidores de aplicaciones o en los servidores de mediación, ya que estos servidores no manejan tráfico de uso compartido de aplicaciones. Solo necesita cambiar los valores de puerto en estos servidores si decide reasignar los puertos usados para el tráfico de audio.

Para modificar los valores de puerto para el uso compartido de aplicaciones en un solo servidor de conferencia, ejecute un comando similar a este en el shell de administración de Skype empresarial Server:

    Set-CsConferenceServer -Identity ConferencingServer:atl-cs-001.litwareinc.com -AppSharingPortStart 40803 -AppSharingPortCount 8348

Si desea realizar estos cambios en todos los servidores de conferencia, puede ejecutar este comando en su lugar:

    Get-CsService -ConferencingServer | ForEach-Object {Set-CsConferenceServer -Identity $_.Identity -AppSharingPortStart 40803 -AppSharingPortCount 8348}

Después de cambiar la configuración del puerto, debe detener y reiniciar cada servicio afectado por los cambios.

No es obligatorio que los servidores de conferencia, los servidores de aplicaciones y los servidores de mediación compartan exactamente el mismo intervalo de puertos; el único requisito es que se reserven intervalos de puertos exclusivos en todos los servidores. Sin embargo, la administración generalmente será más fácil si usa el mismo conjunto de puertos en todos los servidores.

## <a name="configure-a-quality-of-service-policy-in-skype-for-business-server-for-your-conferencing-application-and-mediation-servers"></a>Configurar una directiva de calidad de servicio en Skype empresarial Server para sus servidores de conferencia, aplicaciones y mediación

La configuración de intervalos de puertos facilita el uso de la calidad de servicio al garantizar que todo el tráfico de un tipo específico (por ejemplo, todo el tráfico de audio) se desplaza por el mismo conjunto de puertos. Esto facilita que el sistema identifique y marque un paquete determinado: Si el puerto 49152 está reservado para tráfico de audio, todos los paquetes que viajan a través del puerto 49152 se pueden marcar con un código DSCP que indica que se trata de un paquete de audio. A su vez, permite que los enrutadores identifiquen el paquete como un paquete de audio y le dan mayor prioridad que los paquetes no marcados (como los paquetes que se usan para copiar un archivo de un servidor a otro).

Sin embargo, simplemente restringir un conjunto de puertos a un tipo específico de tráfico no da lugar a que los paquetes se marquen con el código DSCP adecuado. Además de definir intervalos de puertos, también debe crear directivas de calidad de servicio que especifiquen el código DSCP que se va a asociar con cada intervalo de puertos. Para Skype empresarial Server, normalmente significa crear dos directivas: una para el audio y otra para el vídeo.

Las directivas de calidad de servicio se crean más fácilmente y se administran mediante la Directiva de grupo. (Estas mismas directivas también se pueden crear con directivas de seguridad local. Sin embargo, eso requiere repetir el mismo procedimiento en todos los equipos.) El conjunto inicial de directivas de QoS (uno para el audio y otra para el vídeo) debe aplicarse solo a equipos con Skype empresarial Server que ejecuten el servidor de conferencia, el servidor de aplicaciones o los servicios del servidor de mediación. Si todos estos equipos se encuentran en la misma unidad organizativa de Active Directory, simplemente puede asignar el nuevo objeto de directiva de grupo (GPO) a esa unidad organizativa. Como alternativa, puede realizar otros pasos para dirigir la nueva Directiva a los equipos especificados; por ejemplo, puede colocar los equipos apropiados en un grupo de seguridad y, a continuación, usar el filtrado de seguridad de directiva de grupo para aplicar el GPO solo a ese grupo de seguridad.

Para crear una directiva de calidad de servicio para administrar el audio, inicie sesión en un equipo en el que se haya instalado administración de directivas de grupo. Abra administración de directivas de grupo (haga clic en **Inicio**, seleccione **herramientas administrativas**y, a continuación, haga clic en **Administración de directivas de grupo**) y realice el siguiente procedimiento:

1.  En administración de directivas de grupo, busque el contenedor en el que se debe crear la nueva Directiva. Por ejemplo, si todos los equipos de Skype empresarial Server se encuentran en una unidad organizativa denominada Skype empresarial Server, la nueva Directiva debe crearse en la OU de Skype empresarial Server.

2.  Haga clic con el botón secundario en el contenedor correspondiente y, después, haga clic en **crear un GPO en este dominio y vincúlelo aquí**.

3.  En el cuadro de diálogo **nuevo GPO** , escriba un nombre para el nuevo objeto de directiva de grupo en el cuadro **nombre** (por ejemplo, **QoS de Skype empresarial Server**) y, a continuación, haga clic en **Aceptar**.

4.  Haga clic con el botón secundario en la Directiva recién creada y, después, haga clic en **Editar**.

5.  En el editor de administración de directivas de grupo, expanda **configuración del equipo**, expanda **directivas**, expanda **configuración de Windows**, haga clic con el botón secundario en **QoS basada en directivas**y, a continuación, haga clic en **crear nueva Directiva**.

6.  En el cuadro de diálogo **QoS basado en directivas** , en la página de apertura, escriba un nombre para la nueva Directiva (por ejemplo, **Skype empresarial Server QoS**) en el cuadro **nombre** . Seleccione **especificar valor de DSCP** y establezca el valor en **46**. Deje la **tasa de límite saliente** desactivada y, a continuación, haga clic en **siguiente**.

7.  En la página siguiente, asegúrese de que **todas las aplicaciones** está seleccionada y, a continuación, haga clic en **siguiente**. Esto simplemente garantiza que todas las aplicaciones coincidirán con paquetes del intervalo de puertos especificado con el código DSCP especificado.

8.  En la tercera página, asegúrese de que **todas las direcciones IP de origen y cualquier dirección IP de destino** estén seleccionadas y, a continuación, haga clic en **siguiente**. Estas dos opciones de configuración garantizan que los paquetes se administrarán independientemente del equipo (dirección IP) que hayan enviado esos paquetes y qué equipo (dirección IP) recibirá esos paquetes.

9.  En la cuarta página, seleccione **TCP y UDP** en la lista desplegable **seleccionar el protocolo de esta directiva de QoS** . TCP (Protocolo de control de transmisión) y UDP (Protocolo de datagrama de usuario) son los dos protocolos de red más usados por Skype empresarial Server y sus aplicaciones cliente.

10. En el encabezado, **especifique el número de puerto de origen**, seleccione **de este rango o puerto de origen**. En el cuadro de texto que acompaña, escriba el intervalo de puertos reservado para las transtransmisións de audio. Por ejemplo, si ha reservado los puertos 49152 a través de los puertos 57500 para el tráfico de audio, escriba el intervalo de puertos con este formato: **49152:57500**. Haga clic en **Finalizar**.

> [!NOTE]  
> El valor de DSCP de 46 es algo arbitrario: aunque DSCP 46 se usa a menudo para marcar paquetes de audio, no es necesario usar DSCP 46 para las comunicaciones de audio. Si ya ha implementado QoS y está usando un código de DSCP diferente para el audio (por ejemplo, DSCP 40), debe configurar la Directiva de calidad de servicio para usar el mismo código (por ejemplo, 40 para audio). Si ahora está implementando la calidad de servicio, se recomienda que use DSCP 46 para el audio, simplemente porque ese valor suele usarse para marcar paquetes de audio.

Después de crear la directiva QoS para el tráfico de audio, debe crear una segunda Directiva para el tráfico de vídeo (y, opcionalmente, una tercera Directiva para administrar el tráfico de uso compartido de aplicaciones). Para crear una directiva para el vídeo, siga el mismo procedimiento básico que siguió al crear la Directiva de audio y realizar estas sustituciones:

  - Use un nombre de directiva diferente (y único) (por ejemplo, **vídeo de Skype empresarial Server**).

  - Establezca el valor de DSCP en **34** en lugar de 46. (Tenga en cuenta que no es necesario usar un valor de DSCP de 34. El único requisito es que use un valor de DSCP diferente para el vídeo que el que usó para el audio.

  - Use el intervalo de puertos configurado previamente para el tráfico de vídeo. Por ejemplo, si ha reservado los puertos 57501 a 65535 para el vídeo, establezca el intervalo de puertos en: **57501:65535**.

Si decide crear una directiva para administrar el tráfico de uso compartido de aplicaciones, debe crear una tercera Directiva y realizar las siguientes sustituciones:

  - Use un nombre de directiva diferente (y único) (por ejemplo, **uso compartido de aplicaciones de Skype empresarial Server**).

  - Establezca el valor de DSCP en **24** en lugar de 46. (Nuevamente, no es necesario usar un valor de DSCP de 24. El único requisito es que use un valor de DSCP diferente para el uso compartido de aplicaciones que el que usó para el audio o el vídeo.

  - Use el intervalo de puertos configurado previamente para el tráfico de vídeo. Por ejemplo, si ha reservado los puertos 40803 a 49151 para el uso compartido de aplicaciones, establezca el intervalo de puertos en: **40803:49151**.

Las nuevas directivas que ha creado no tendrán efecto hasta que se actualice la Directiva de grupo en los equipos de Skype empresarial Server. Aunque la directiva de grupo se actualiza periódicamente por sí misma, se puede forzar una actualización inmediata si se ejecuta el siguiente comando en cada equipo en el que se tenga que actualizar la directiva de grupo:

    Gpupdate.exe /force

Este comando se puede ejecutar desde el shell de administración de Skype empresarial Server o desde cualquier ventana de comandos que se ejecute con credenciales de administrador. Para abrir una ventana de comandos con las credenciales del administrador, haga clic en **Inicio**, haga clic con el botón derecho en **Símbolo del sistema** y, a continuación, haga clic en **Ejecutar como administrador**.

Para comprobar que se han aplicado las nuevas directivas de QoS, haga lo siguiente:

1.  En un equipo con Skype empresarial Server, haga clic en **Inicio**y, a continuación, haga clic en **Ejecutar**.

2.  En el cuadro de diálogo **Ejecutar** , **** escriba regedit y, a continuación, presione Entrar.

3.  En el editor del registro, expanda **equipo**, expanda **\_HKEY local\_Machine**, expanda **software**, expanda **directivas**, expanda **Microsoft**, expanda **Windows**y, a continuación, haga clic en **QoS**. En **QoS** , debe ver las claves del registro para cada una de las directivas de QoS que acaba de crear. Por ejemplo, si ha creado dos nuevas directivas (una con el nombre QoS de audio de Skype empresarial Server y la otra denominada QoS de vídeo de Skype empresarial Server), debería ver las entradas del registro para la calidad de audio de Skype empresarial Server y la calidad de video de Skype empresarial Server.

Para asegurarse de que los paquetes de red estén marcados con el valor de DSCP adecuado, también debe crear una nueva entrada de registro en cada equipo completando el procedimiento siguiente:

1.  Haga clic en  **Inicio ** y en  **Ejecutar **.

2.  En el cuadro de diálogo **Ejecutar** , **** escriba regedit y, a continuación, presione Entrar.

3.  En el editor del registro, expanda el **equipo local\_\_HKEY**, expanda **sistema**, expanda **CurrentControlSet**, expanda **Services**y, a continuación, expanda **TCPIP**.

4.  Haga clic con el botón derecho en **TCPIP**, seleccione **nuevo**y, a continuación, haga clic en **clave**. Después de crear la nueva clave del registro, escriba **QoS**y, a continuación, presione Entrar para cambiar el nombre de la clave.

5.  Haga clic con el botón derecho en **QoS**, seleccione **nuevo**y, a continuación, haga clic en **valor de cadena**. Después de crear el nuevo valor del registro, escriba **no use NLA**y, a continuación, presione Entrar para cambiar el nombre del valor.

6.  Haga doble clic en **no usar NLA**. En el cuadro de diálogo **Editar cadena** , escriba **1** en el cuadro **datos del valor** y, a continuación, haga clic en **Aceptar**.

7.  Cierre el editor del registro y reinicie el equipo.
