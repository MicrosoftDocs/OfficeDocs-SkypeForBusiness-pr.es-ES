---
title: Configuración de intervalos de puertos y una directiva de calidad de servicio para los clientes
ms.reviewer: ''
ms:assetid: 287d5cea-7ada-461c-9b4a-9da2af315e71
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204760(v=OCS.15)
ms:contentKeyID: 48183694
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Este artículo describe cómo configurar los intervalos de puertos para clientes y la configuración de las directivas de calidad de servicio de Skype para Business Server para los clientes que se ejecutan en Windows 10.
ms.openlocfilehash: 2e5328406634302a1b076eec8466e7f7b9245150
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30881524"
---
# <a name="configuring-port-ranges-and-a-quality-of-service-policy-for-your-clients-in-skype-for-business-server"></a>Configuración de intervalos de puertos y una directiva de calidad de servicio para los clientes en Skype para Business Server

Este artículo describe cómo configurar los intervalos de puertos para clientes y la configuración de las directivas de calidad de servicio de Skype para Business Server para los clientes que se ejecutan en Windows 10.

## <a name="configure-port-ranges"></a>Configurar intervalos de puertos

De forma predeterminada, Skype para aplicaciones empresariales de cliente pueden usar cualquier puerto entre puertos 1024 y 65535 cuando participa en una sesión de comunicación; Esto es debido a que los intervalos de puertos no se habilitan automáticamente para los clientes. Para poder usar la calidad de servicio, sin embargo, debe volver a asignar los distintos tipos de tráfico (audio, vídeo, medios, uso compartido de aplicaciones y transferencia de archivos) a una serie de intervalos de puertos único. Esto puede realizarse mediante el cmdlet Set-CsConferencingConfiguration.

> [!NOTE]  
> Los usuarios finales no pueden realizar estos cambios ellos mismos. Cambios de puerto sólo pueden realizar los administradores con el cmdlet Set-CsConferencingConfiguration.


Puede determinar qué intervalos de puertos se usan actualmente para las sesiones de comunicación ejecutando el siguiente comando desde dentro de la Skype de consola de administración de servidor empresarial:

    Get-CsConferencingConfiguration

Suponiendo que no ha realizado ningún cambio en la configuración de conferencia desde que instaló Skype para Business Server, debería obtener información que incluya estos valores de propiedad:

    ClientMediaPortRangeEnabled : False
    ClientAudioPort             : 5350
    ClientAudioPortRange        : 40
    ClientVideoPort             : 5350
    ClientVideoPortRange        : 40
    ClientAppSharingPort        : 5350
    ClientAppSharingPortRange   : 40
    ClientFileTransferPort      : 5350
    ClientTransferPortRange     : 40

Si examina atentamente el resultado anterior, verá dos cosas de importancia. En primer lugar, la propiedad de los parámetros ClientMediaPortRangeEnabled está establecida en False:

    ClientMediaPortRangeEnabled : False

Que es importante porque, cuando se establece esta propiedad en False, Skype para clientes empresariales va a usar cualquier puerto disponible entre los puertos 1024 y 65535 cuando participa en una sesión de comunicación; Esto es así independientemente de cualquier otra configuración de puerto (por ejemplo, ClientMediaPort o ClientVideoPort). Si desea restringir el uso a un conjunto de puertos especificado (y esto es algo que desea hacer si tiene previsto en la implementación de calidad de servicio), primero debe habilitar intervalos de puertos de medios de cliente. Que se puede realizar mediante el siguiente comando de Windows PowerShell:

    Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True

El comando anterior permite intervalos de puertos de medios de cliente para la colección global de opciones de configuración de la conferencia; Sin embargo, estas opciones de configuración también pueden aplicarse en el ámbito de sitio o el ámbito de servicio (sólo para el servidor de conferencia servicio). Para habilitar intervalos para un sitio específico o el servidor, de puertos de medios de cliente especificar la identidad de ese sitio o el servidor cuando se llama a Set-CsConferencingConfiguration:

    Set-CsConferencingConfiguration -Identity "site:Redmond" -ClientMediaPortRangeEnabled $True

Como alternativa, puede usar este comando para habilitar intervalos de puertos para todas las opciones de configuración de conferencia:

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration  -ClientMediaPortRangeEnabled $True

La segunda cosa de importancia que observará es que los resultados de muestra que, de forma predeterminada, los intervalos de puertos multimedia configurados para cada tipo de tráfico de red son idénticos:

    ClientAudioPort             : 5350
    ClientVideoPort             : 5350
    ClientAppSharingPort        : 5350
    ClientFileTransferPort      : 5350

Para implementar QoS, cada uno de estos intervalos de puertos deberá ser único. Por ejemplo, puede configurar los intervalos de puertos como esta:


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Tipo de tráfico de cliente</th>
<th>Puerto inicial</th>
<th>Intervalo de puertos</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Audio</p></td>
<td><p>50020</p></td>
<td><p>20</p></td>
</tr>
<tr class="even">
<td><p>Vídeo</p></td>
<td><p>58000</p></td>
<td><p>20</p></td>
</tr>
<tr class="odd">
<td><p>Uso compartido de aplicaciones</p></td>
<td><p>42000</p></td>
<td><p>20</p></td>
</tr>
<tr class="even">
<td><p>Transferencia de archivos</p></td>
<td><p>42020</p></td>
<td><p>20</p></td>
</tr>
</tbody>
</table>


En la tabla anterior, los intervalos de puertos de cliente representan un subconjunto de los intervalos de puertos configurados para los servidores. Por ejemplo, en los servidores, uso compartido de aplicaciones se ha configurado para utilizar puertos 40803 y 49151; en los equipos cliente, el uso compartido de aplicaciones está configurado para utilizar puertos 42000 a través de 42019. Esto, demasiado, se realiza principalmente para facilitar la administración de QoS: puertos de cliente no es necesario que representar un subconjunto de los puertos utilizados en el servidor. (Por ejemplo, en los equipos cliente se puede configurar uso compartido de aplicaciones para que utilice, por ejemplo, puertos 10000 a través de 10019.) Sin embargo, se recomienda que realice su cliente puerto rangos un subconjunto de los intervalos de puertos de servidor.

Además, es posible que haya observado que los 8348 puertos estaban reservados para uso compartido en los servidores de aplicaciones, pero sólo 20 puertos estaban reservados para uso compartido en los clientes de aplicaciones. Esto es demasiado, se recomienda, pero no es una una regla. En general, se puede tener en cuenta cada puerto disponible para representar una sesión de comunicación único: si dispone de 100 puertos disponibles en un intervalo de puertos, lo que significa que el equipo en cuestión podría participar en, como máximo, 100 sesiones de comunicación en cualquier momento dado. Debido a que los servidores es probable que va a participar en muchas conversaciones más que los clientes, tiene sentido abrir muchas más puertos en servidores que en los clientes. 20 puertos de anulación de configuración de aplicación de uso compartido en un cliente significa que un usuario puede participar en 20 sesiones de uso compartido de aplicaciones en el dispositivo especificado y todos al mismo tiempo. Que debería ser suficiente para la mayoría de los usuarios.

Para asignar los intervalos de puertos anteriores a la colección global de la configuración de conferencia, puede usar el siguiente Skype para el comando de Shell de administración de servidor empresarial:

    Set-CsConferencingConfiguration -Identity global -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

O bien, use este comando para asignar estos intervalos de puertos misma para todas las conferencias de los valores de configuración:

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

Los usuarios individuales deben cerrar la sesión de Skype para la empresa y, a continuación, vuelva a iniciarla antes de que estos cambios surtan efecto.

> [!NOTE]  
> Puede también habilitar intervalos de puertos de medios de cliente y, a continuación, asignar los intervalos de puertos, con un solo comando. Por ejemplo:<BR><CODE>Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20</CODE>

## <a name="configure-quality-of-service-policies-for-clients-running-on-windows-10"></a>Configurar directivas de calidad de servicio para los clientes que se ejecutan en Windows 10

Además de especificar intervalos de puertos para su uso por su Skype para clientes empresariales, también debe crear directivas distintas de calidad de servicio que se aplicará a los equipos cliente. (Las directivas de calidad de servicio creadas para los servidores de conferencia, aplicación y mediación no deben aplicarse a los equipos cliente.) Esta información sólo se aplica a los equipos que ejecutan el Skype para clientes empresariales y 10 de Windows.

En el ejemplo siguiente se usa este conjunto de intervalos de puertos para crear una directiva de audio y una directiva de vídeo:


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Tipo de tráfico de cliente</th>
<th>Puerto inicial</th>
<th>Intervalo de puertos</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Audio</p></td>
<td><p>50020</p></td>
<td><p>20</p></td>
</tr>
<tr class="even">
<td><p>Vídeo</p></td>
<td><p>58000</p></td>
<td><p>20</p></td>
</tr>
<tr class="odd">
<td><p>Uso compartido de aplicaciones</p></td>
<td><p>42000</p></td>
<td><p>20</p></td>
</tr>
<tr class="even">
<td><p>Transferencia de archivos</p></td>
<td><p>42020</p></td>
<td><p>20</p></td>
</tr>
</tbody>
</table>

Para crear una directiva de audio de calidad de servicio para equipos Windows 10, primero inicie sesión en un equipo donde se ha instalado Administración de directivas de grupo. Abra Administración de directivas de grupo (haga clic en **Inicio**, elija **Herramientas administrativas**y, a continuación, haga clic en **Administración de directivas de grupo**) y, a continuación, complete el siguiente procedimiento:

1.  En administración de directivas de grupo, busque el contenedor donde se debe crear la nueva directiva. Por ejemplo, si todos los equipos cliente se encuentran en una unidad organizativa denominada a clientes, se debe crear la nueva directiva en la unidad organizativa de cliente.

2.  Haga clic en el contenedor adecuado y, a continuación, haga clic en **crear un GPO en este dominio y vincularlo aquí**.

3.  En el cuadro de diálogo **Nuevo GPO** , escriba un nombre para el nuevo objeto de directiva de grupo en el cuadro **nombre** y, a continuación, haga clic en **Aceptar**.

4.  Haga clic en la directiva recién creada y, a continuación, haga clic en **Editar**.

5.  En el Editor de administración de directiva de grupo, expanda **Configuración del equipo**, expanda **Configuración de Windows**, haga clic en **QoS basada en directiva**y, a continuación, haga clic en **Crear nueva directiva**.

6.  En el cuadro de diálogo de **QoS basada en directiva** , en la página de apertura, escriba un nombre para la nueva directiva en el cuadro **nombre** . Seleccione **Especificar el valor de DSCP** y establezca el valor **46**. Deje **Especificar velocidad de aceleración saliente** no está seleccionada y, a continuación, haga clic en **siguiente**.

7.  En la página siguiente, asegúrese de que **todas las aplicaciones** está activada y, a continuación, haga clic en **siguiente**. Esta opción indica a la red para buscar todos los paquetes con un marcado DSCP 46, no sólo de paquetes de creados mediante una aplicación específica.

8.  En la tercera página, asegúrese de que **cualquier dirección IP de origen** y **cualquier dirección IP de destino** están seleccionados y, a continuación, haga clic en **siguiente**. Estos dos valores Asegúrese de que se administrarán los paquetes independientemente de qué equipo (dirección IP) enviado esos paquetes y qué equipo (dirección IP) recibirán los paquetes.

9.  En la cuarta página, seleccione **TCP y UDP** en la lista desplegable **Seleccione el protocolo que se aplica esta directiva de QoS** . TCP (Protocolo de Control de transmisión) y UDP (Protocolo de datagramas de usuario) son los dos protocolos de red más utilizados por Skype para Business Server y sus aplicaciones de cliente.

10. Bajo el encabezado, **Especifique el número de puerto de origen**, seleccione **desde este intervalo o el puerto de origen**. En el cuadro de texto que lo acompaña, escriba el intervalo de puertos reservado para las transmisiones de audioconferencias. Por ejemplo, si ha reservado puertos 50020 a través de los puertos 50039 el tráfico de audio, escriba el intervalo de puertos con este formato: **50020:50039**. Haga clic en **Finalizar**.

Después de haber creado la directiva de QoS para el audio, a continuación, debe crear una segunda directiva para vídeo. Para crear una directiva para el vídeo, siga el mismo procedimiento básico seguido al crear la directiva de audio, realizar las siguientes sustituciones:

  - Use un nombre de directiva diferente (y único).

  - Establezca el valor DSCP a **34** en lugar de 46. (Como se indicó anteriormente, no es necesario usar el valor de DSCP 34; simplemente debe asignar un valor DSCP distinto del que se utilizó para el audio).

  - Usar el intervalo de puerto configurado anteriormente para el tráfico de vídeo. Por ejemplo, si lo ha reservado puertos 58000 a través de 58019 para el vídeo, establezca el intervalo de puertos a la siguiente: **58000:58019**.

Si decide crear una directiva para administrar el tráfico de uso compartido de aplicaciones, realice las siguientes sustituciones:

  - Use un nombre de directiva diferente (y único) (por ejemplo, **Skype para compartir aplicaciones de servidor de negocio**).

  - Establezca el valor de DSCP en **24** en lugar de 46. (De nuevo, este valor no tiene que ser 24; simplemente debe ser diferente de los valores DSCP usados para audio y vídeo).

  - Usar el intervalo de puerto configurado anteriormente para el tráfico de vídeo. Por ejemplo, si lo ha reservado puertos 42000 a través de 42019 para uso compartido de aplicaciones, puede establecer el intervalo de puertos a la siguiente: **42000:42019**.

Para una directiva de transferencia de archivo:

  - Use un nombre de directiva diferente (y único) (por ejemplo, **Skype para las transferencias de archivos de servidor empresarial**).

  - Establezca el valor DSCP a **14**. (De nuevo, este valor no tiene que ser 14; simplemente debe ser un código DSCP único).

  - Utilice el intervalo de puerto configurado anteriormente para la aplicación. Por ejemplo, si lo ha reservado puertos 42020 a través de 42039 para uso compartido de aplicaciones, puede establecer el intervalo de puertos a la siguiente: **42020:42039**.

Las nuevas directivas que ha creado no tendrán efecto hasta que se ha actualizado la directiva de grupo en los equipos cliente. Aunque la directiva de grupo se actualiza periódicamente por sí misma, se puede forzar una actualización inmediata si se ejecuta el siguiente comando en cada equipo en el que se tenga que actualizar la directiva de grupo:

    Gpudate.exe /force

Este comando se puede ejecutar desde cualquier ventana de comandos que se ejecute con las credenciales del administrador. Para abrir una ventana de comandos con las credenciales del administrador, haga clic en **Inicio**, haga clic con el botón derecho en **Símbolo del sistema** y, a continuación, haga clic en **Ejecutar como administrador**.

Tenga en cuenta que deben ser destinadas estas directivas a los equipos cliente. No debe aplicarse a los servidores que ejecutan Skype para Business Server.

Para ayudar a garantizar que los paquetes de red están marcados con el valor DSCP adecuado, también debe crear una nueva entrada del registro en cada equipo completando el procedimiento siguiente:

1.  Haga clic en  **Inicio ** y en  **Ejecutar **.

2.  En el cuadro de diálogo **Ejecutar** , escriba **regedit**y, a continuación, presione ENTRAR.

3.  En el Editor del registro, expanda **HKEY\_LOCAL\_máquina**, expanda **SYSTEM**, expanda **CurrentControlSet**, expanda **Servicios**y, a continuación, expanda **Tcpip**.

4.  Secundario **Tcpip**, elija **nuevo**y, a continuación, haga clic en **clave**. Una vez creada la nueva clave del registro, escriba **QoS**y, a continuación, presione ENTRAR para cambiar el nombre de la clave.

5.  Secundario **QoS**, elija **nuevo**y, a continuación, haga clic en **Valor de tipo String**. Una vez creado el nuevo valor del registro, escriba **no use NLA**y, a continuación, presione ENTRAR para cambiar el nombre del valor.

6.  Haga doble clic en **no usa NLA**. En el cuadro de diálogo **Editar cadena** , escriba **1** en el cuadro **datos de valor** y, a continuación, haga clic en **Aceptar**.

7.  Cierre el Editor del registro y eboot su equipo.

### <a name="configure-quality-of-service-on-computers-with-multiple-network-adapters"></a>Configuración de calidad de servicio en equipos con varios adaptadores de red

Si tiene un equipo que tenga varios adaptadores de red, es posible que ejecute cada cierto tiempo problemas donde se muestran los valores de DSCP como 0 x 00 en lugar de con el valor configurado. Normalmente, esto se producirá en los equipos donde uno o varios de los adaptadores de red no son capaz de obtener acceso a su dominio de Active Directory (por ejemplo, si se utilizan estos adaptadores para una red privada). En casos como, valores de DSCP se etiquetarán para los adaptadores que pueden tener acceso al dominio, pero no se etiquetará para los adaptadores que no se pueden tener acceso al dominio.

Si desea que los valores DSCP de etiqueta para todos los adaptadores de red en un equipo, incluidos los adaptadores que no tienen acceso a su dominio, debe agregar y configurar un valor en el registro. Es posible que al completar el procedimiento siguiente:

1.  Haga clic en  **Inicio ** y en  **Ejecutar **.

2.  En el cuadro de diálogo **Ejecutar** , escriba **regedit**y, a continuación, presione ENTRAR.

3.  En el Editor del registro, expanda **HKEY\_LOCAL\_máquina**, expanda **SYSTEM**, expanda **CurrentControlSet**, expanda **Servicios**y, a continuación, expanda **Tcpip**.

4.  Si no ve una clave del registro con la etiqueta **QoS** , a continuación, haga clic en **TCP/IP**, elija **nuevo**y, a continuación, haga clic en **clave**. Una vez creada la nueva clave, escriba **QoS**y, a continuación, presione ENTRAR para cambiar el nombre de la clave.

5.  Secundario **QoS**, elija **nuevo**y, a continuación, haga clic en **Valor de tipo String**. Una vez creado el nuevo valor del registro, escriba **no use NLA**y, a continuación, presione ENTRAR para cambiar el nombre del valor.

6.  Haga doble clic en **no usa NLA**. En el cuadro de diálogo **Editar cadena** , escriba **1** en el cuadro **datos de valor** y, a continuación, haga clic en **Aceptar**.

Después de crear y configurar el nuevo valor del registro, debe reiniciar el equipo para que los cambios surtan efecto.

## <a name="see-also"></a>Consulte también

[Crear un objeto de directiva de grupo en Windows 10](https://docs.microsoft.com/en-us/windows/security/threat-protection/windows-firewall/create-a-group-policy-object)
