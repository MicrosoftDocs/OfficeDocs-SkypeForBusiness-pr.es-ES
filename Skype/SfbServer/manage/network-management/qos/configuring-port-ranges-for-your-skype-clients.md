---
title: Configuración de intervalos de puertos y una directiva de calidad de servicio para los clientes
ms.reviewer: ''
ms:assetid: 287d5cea-7ada-461c-9b4a-9da2af315e71
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204760(v=OCS.15)
ms:contentKeyID: 48183694
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: En este artículo se describe cómo configurar los intervalos de puertos para los clientes y configurar directivas de calidad de servicio en Skype empresarial Server para clientes que se ejecutan en Windows 10.
ms.openlocfilehash: 95fe768333a01aff165e74eec334f14bf23d69dc
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045893"
---
# <a name="configuring-port-ranges-and-a-quality-of-service-policy-for-your-clients-in-skype-for-business-server"></a>Configuración de intervalos de puertos y una directiva de calidad de servicio para los clientes en Skype empresarial Server

En este artículo se describe cómo configurar los intervalos de puertos para los clientes y configurar directivas de calidad de servicio en Skype empresarial Server para clientes que se ejecutan en Windows 10.

## <a name="configure-port-ranges"></a>Configuración de intervalos de puertos

De forma predeterminada, las aplicaciones cliente de Skype empresarial pueden usar cualquier puerto entre los puertos 1024 y 65535 cuando participa en una sesión de comunicación; Esto se debe a que los intervalos de puertos específicos no se habilitan automáticamente para los clientes. Sin embargo, para poder usar la calidad de servicio, tendrá que volver a asignar los distintos tipos de tráfico (audio, vídeo, medios, uso compartido de aplicaciones y transferencia de archivos) a una serie de intervalos de puertos únicos. Esto se puede hacer con el cmdlet Set-CsConferencingConfiguration.

> [!NOTE]  
> Los usuarios finales no pueden realizar estos cambios por sí mismos. Los cambios de Puerto solo los pueden realizar los administradores mediante el cmdlet Set-CsConferencingConfiguration.


Puede determinar qué intervalos de puertos se usan actualmente para las sesiones de comunicación ejecutando el siguiente comando desde el shell de administración de Skype empresarial Server:

    Get-CsConferencingConfiguration

Suponiendo que no ha realizado ningún cambio en la configuración de conferencia desde que instaló Skype empresarial Server, debe obtener información que incluya estos valores de propiedades:

    ClientMediaPortRangeEnabled : False
    ClientAudioPort             : 5350
    ClientAudioPortRange        : 40
    ClientVideoPort             : 5350
    ClientVideoPortRange        : 40
    ClientAppSharingPort        : 5350
    ClientAppSharingPortRange   : 40
    ClientFileTransferPort      : 5350
    ClientTransferPortRange     : 40

Si observa atentamente el resultado anterior, verá dos aspectos de importancia. En primer lugar, la propiedad los parámetros clientmediaportrangeenabled se establece en false:

    ClientMediaPortRangeEnabled : False

Esto es importante porque, cuando esta propiedad se establece en false, los clientes de Skype empresarial usarán cualquier puerto disponible entre los puertos 1024 y 65535 cuando participen en una sesión de comunicación; Esto es así independientemente de cualquier otra configuración de puerto (por ejemplo, ClientMediaPort o ClientVideoPort). Si desea restringir el uso a un conjunto específico de puertos (y esto es algo que desea hacer si tiene previsto implementar la calidad de servicio), primero debe habilitar los intervalos de puertos de los medios de cliente. Esto se puede hacer con el siguiente comando de Windows PowerShell:

    Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True

El comando anterior habilita los intervalos de puertos de medios de cliente para la colección global de opciones de configuración de conferencia; sin embargo, estas opciones también se pueden aplicar al ámbito del sitio o al ámbito del servicio (solo para el servicio de servidor de conferencia). Para habilitar los intervalos de puertos de medios de cliente para un sitio o servidor específicos, especifique la identidad de ese sitio o servidor cuando llame a set-CsConferencingConfiguration:

    Set-CsConferencingConfiguration -Identity "site:Redmond" -ClientMediaPortRangeEnabled $True

Como alternativa, puede usar este comando para habilitar simultáneamente los intervalos de puertos para todas las opciones de configuración de Conferencia:

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration  -ClientMediaPortRangeEnabled $True

La segunda importancia que verá es que el resultado del ejemplo muestra que, de forma predeterminada, los intervalos de puertos de medios establecidos para cada tipo de tráfico de red son idénticos:

    ClientAudioPort             : 5350
    ClientVideoPort             : 5350
    ClientAppSharingPort        : 5350
    ClientFileTransferPort      : 5350

Para poder implementar QoS, cada uno de estos intervalos de puertos tendrá que ser único. Por ejemplo, puede configurar los intervalos de puertos como se muestra a continuación:


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


En la tabla anterior, los intervalos de puertos de cliente representan un subconjunto de los intervalos de puertos configurados para los servidores. Por ejemplo, en los servidores, el uso compartido de aplicaciones se configuró para usar los puertos de 40803 a 49151; en los equipos cliente, el uso compartido de aplicaciones está configurado para usar los puertos de 42000 a 42019. Esto también se realiza principalmente para facilitar la administración de QoS: los puertos de cliente no tienen que representar un subconjunto de los puertos usados en el servidor. (Por ejemplo, en los equipos cliente podría configurar el uso compartido de aplicaciones para usar, por ejemplo, los puertos de 10000 a 10019). Sin embargo, se recomienda que los intervalos de puertos de cliente sean un subconjunto de los intervalos de puertos del servidor.

Además, es posible que haya observado que se han reservado 8348 puertos para el uso compartido de aplicaciones en los servidores, pero solo se configuraron 20 puertos para el uso compartido de aplicaciones en los clientes. También se recomienda esto, pero no es una regla difícil y rápida. En general, puede considerar cada puerto disponible para representar una única sesión de comunicación: Si tiene 100 puertos disponibles en un intervalo de puertos, significa que el equipo en cuestión puede participar, como máximo, de 100 sesiones de comunicación en un determinado momento. Como es probable que los servidores participen en muchas más conversaciones que los clientes, tiene sentido abrir muchos más puertos en los servidores que en los clientes. La reserva de 20 puertos para el uso compartido de aplicaciones en un cliente significa que un usuario puede participar en 20 sesiones de uso compartido de aplicaciones en el dispositivo especificado, y todo al mismo tiempo. Eso debería ser suficiente para la inmensa mayoría de los usuarios.

Para asignar los intervalos de puertos anteriores a la colección global de opciones de configuración de conferencia, puede usar el siguiente comando del shell de administración de Skype empresarial Server:

    Set-CsConferencingConfiguration -Identity global -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

O bien, use este comando para asignar estos mismos intervalos de puertos para todas las opciones de configuración de Conferencia:

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

Los usuarios individuales deben cerrar sesión en Skype empresarial y, a continuación, volver a iniciar sesión antes de que estos cambios entren en vigor.

> [!NOTE]  
> También puede habilitar intervalos de puertos de medios de cliente y, a continuación, asignar esos intervalos de puertos con un solo comando. Por ejemplo:<BR><CODE>Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20</CODE>

## <a name="configure-quality-of-service-policies-for-clients-running-on-windows-10"></a>Configurar directivas de calidad de servicio para clientes que se ejecutan en Windows 10

Además de especificar intervalos de puertos para su uso por parte de los clientes de Skype empresarial, también debe crear directivas de calidad de servicio independientes que se aplicarán a los equipos cliente. (Las directivas de calidad de servicio creadas para los servidores de conferencia, aplicación y mediación no deben aplicarse a los equipos cliente). Esta información solo se aplica a los equipos que ejecutan el cliente de Skype empresarial y Windows 10.

En el ejemplo siguiente utiliza este conjunto de intervalos de puertos para crear una directiva de audio y una directiva de vídeo:


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

Para crear una directiva de audio de calidad de servicio para equipos con Windows 10, primero inicie sesión en un equipo en el que se haya instalado administración de directivas de grupo. Abra administración de directivas de grupo (haga clic en **Inicio**, elija **herramientas administrativas**y, a continuación, haga clic en **Administración de directivas de grupo**) y, a continuación, realice el siguiente procedimiento:

1.  En Administración de directivas de grupo, busque el contenedor donde se deba crear la nueva directiva. Por ejemplo, si todos los equipos cliente están ubicados en una unidad organizativa denominada clientes, la nueva Directiva debe crearse en la uo cliente.

2.  Haga clic con el botón secundario en el contenedor adecuado y, a continuación, haga clic en **crear un GPO en este dominio y vincularlo aquí**.

3.  En el cuadro de diálogo **nuevo GPO** , escriba un nombre para el nuevo objeto de directiva de grupo en el cuadro **nombre** y, a continuación, haga clic en **Aceptar**.

4.  Haga clic con el botón secundario en la Directiva recién creada y haga clic en **Editar**.

5.  En el editor de administración de directivas de grupo, expanda **configuración del equipo**, expanda **configuración de Windows**, haga clic con el botón secundario en **QoS basada en Directiva**y, a continuación, haga clic en **crear nueva Directiva**.

6.  En el cuadro de diálogo **QoS basada en directivas** , en la página de inicio, escriba un nombre para la nueva Directiva en el cuadro **nombre** . Seleccione **Especificar el valor de DSCP** y, a continuación, defina el valor en **46**. Deje sin seleccionar **Especificar velocidad de salida del acelerador** y, a continuación, haga clic en **Siguiente**.

7.  En la página siguiente, seleccione **solo aplicaciones con este nombre de archivo ejecutable**, escriba **Lync. exe** como nombre y, a continuación, haga clic en **siguiente**. Esta configuración le indica a la Directiva que solo Asigne prioridades de tráfico de coincidencia desde el cliente de Skype empresarial.

8.  En la tercera página, asegúrese de que **todas las** direcciones IP de origen y de **destino** estén seleccionadas y, a continuación, haga clic en **siguiente**. Con estas dos opciones de configuración activadas, los paquetes se administrarán sin importar qué equipo (dirección IP) los envió ni qué equipo (dirección IP) los recibirá.

9.  En la página cuatro, seleccione **TCP y UDP** en la lista desplegable **Seleccione el protocolo para el que se aplica esta directiva de QoS**. TCP (Protocolo de control de transmisión) y UDP (Protocolo de datagramas de usuario) son los dos protocolos de red más usados por Skype empresarial Server y sus aplicaciones cliente.

10. En el encabezado **Especifique el número de puerto de origen**, seleccione **Desde este intervalo o puerto de origen**. En el cuadro de texto asociado, escriba el intervalo de puertos reservado para las transmisiones de audio. Por ejemplo, si ha reservado los puertos de 50020 a 50039 para el tráfico de audio, escriba el intervalo de puertos con el formato: **50020:50039**. Haga clic en **Finalizar**.

Después de crear la directiva de QoS para audio, deberá crear una segunda directiva para el vídeo. Para ello, siga el mismo procedimiento básico que ha seguido para la directiva de audio, con las siguientes sustituciones:

  - Use un nombre de directiva diferente (y único).

  - Ajuste el valor de DSCP en **34**, en lugar de 46. (Como ya se ha mencionado, no tiene que utilizar el valor 34 para DSCP, sino asignar a DSCP un valor diferente al usado para el audio.)

  - Use el intervalo de puertos configurado anteriormente para el tráfico de vídeo. Por ejemplo, si ha reservado los puertos de 58000 a 58019 para el vídeo, establezca el intervalo de puertos en este: **58000:58019**.

Si decide crear una directiva para administrar el tráfico de uso compartido de aplicaciones, realice las siguientes sustituciones:

  - Use un nombre de directiva diferente (y único) (por ejemplo, **uso compartido de aplicaciones de Skype empresarial Server**).

  - Ajuste el valor de DSCP en **24**, en lugar de 46. (También en este caso, este valor no tiene por qué ser 24, sino que debe ser diferente a los valores de DSCP utilizados para el audio y el vídeo.)

  - Use el intervalo de puertos configurado anteriormente para el tráfico de vídeo. Por ejemplo, si ha reservado los puertos de 42000 a 42019 para el uso compartido de aplicaciones, establezca el intervalo de puertos en este: **42000:42019**.

Para una directiva de transferencia de archivos:

  - Use un nombre de directiva diferente (y único) (por ejemplo, **transferencias de archivos de Skype empresarial Server**).

  - Ajuste el valor de DSCP en **14**. (Una vez más, este valor no tiene por qué ser 14, sino simplemente un código DSCP único.)

  - Usar el intervalo de puertos configurado anteriormente para la aplicación. Por ejemplo, si ha reservado los puertos de 42020 a 42039 para el uso compartido de aplicaciones, establezca el intervalo de puertos en este: **42020:42039**.

Las directivas nuevas que ha creado no tendrán efecto hasta que se actualice Directiva de grupos en los equipos cliente. Aunque la Directiva de grupos se actualiza periódicamente de forma automática, puede forzar una actualización inmediata ejecutando el siguiente comando en todos los equipos en los que es necesario actualizar la Directiva de grupos:

    Gpupdate.exe /force

Este comando se puede ejecutar desde cualquier ventana de comandos que se ejecute con las credenciales de administrador. Para ejecutar una ventana de comando con las credenciales de administrador, haga clic en **Inicio**, haga clic con el botón secundario en **Símbolo del sistema** y, a continuación, haga clic en **Ejecutar como administrador**.

Recuerde que estas directivas deben ir dirigidas a los equipos cliente. No se deben aplicar a los servidores que ejecutan Skype empresarial Server.

Para asegurarse de que los paquetes de red se marquen con el valor de DSCP adecuado, debe crear también una nueva entrada del Registro en cada equipo, mediante el siguiente procedimiento:

1.  Haga clic en **Inicio** y, a continuación, haga clic en **Ejecutar**.

2.  En el cuadro de diálogo **Ejecutar** , escriba **regedit**y, a continuación, presione Entrar.

3.  En el editor del registro, expanda el **equipo local\_\_HKEY**, expanda **sistema**, expanda **CurrentControlSet**, expanda **servicios**y, a continuación, expanda **TCPIP**.

4.  Haga clic con el botón secundario en **Tcpip**, elija **Nuevo** y, a continuación, haga clic en **Clave**. Una vez creada la nueva clave del registro, escriba **QoS**y, a continuación, presione Entrar para cambiar el nombre de la clave.

5.  Haga clic con el botón secundario en **QoS**, elija **Nuevo** y, a continuación, haga clic en **Valor de cadena**. Después de crear el nuevo valor del registro, escriba **no use NLA**y, a continuación, presione Entrar para cambiar el nombre del valor.

6.  Haga doble clic en **No usar NLA**. En el cuadro de diálogo **Editar cadena** , escriba **1** en el cuadro **información del valor** y, a continuación, haga clic en **Aceptar**.

7.  Cierre el editor del registro y eboot el equipo.

### <a name="configure-quality-of-service-on-computers-with-multiple-network-adapters"></a>Configurar la calidad de servicio en equipos con varios adaptadores de red

Si tiene un equipo con varios adaptadores de red, en ocasiones puede que se ejecute en problemas en los que los valores DSCP se muestran como 0x00 en lugar del valor configurado. Esto ocurrirá, generalmente, en equipos en los que uno o más adaptadores de red no pueden acceder al dominio de Active Directory (por ejemplo, si estos adaptadores de red se utilizan para una red privada). En esos casos, los valores DSCP se etiquetarán para los adaptadores que pueden acceder al dominio, pero no se etiquetarán para los adaptadores que no tienen acceso al dominio.

Si desea etiquetar los valores DSCP para todos los adaptadores de red de un equipo, incluidos los adaptadores que no tienen acceso a su dominio, tendrá que agregar y configurar un valor para el registro. Se puede hacer siguiendo este procedimiento:

1.  Haga clic en **Inicio** y, a continuación, haga clic en **Ejecutar**.

2.  En el cuadro de diálogo **Ejecutar** , escriba **regedit**y, a continuación, presione Entrar.

3.  En el editor del registro, expanda el **equipo local\_\_HKEY**, expanda **sistema**, expanda **CurrentControlSet**, expanda **servicios**y, a continuación, expanda **TCPIP**.

4.  Si no ve una clave de registro con la etiqueta **QoS**, haga clic con el botón secundario en **Tcpip**, seleccione **Nuevo** y, a continuación, haga clic en **Clave**. Una vez creada la clave nueva, escriba **QoS**y, a continuación, presione Entrar para cambiar el nombre de la clave.

5.  Haga clic con el botón secundario en **QoS**, elija **Nuevo** y, a continuación, haga clic en **Valor de cadena**. Después de crear el nuevo valor del registro, escriba **no use NLA**y, a continuación, presione Entrar para cambiar el nombre del valor.

6.  Haga doble clic en **No usar NLA**. En el cuadro de diálogo **Editar cadena** , escriba **1** en el cuadro **información del valor** y, a continuación, haga clic en **Aceptar**.

Después de crear y configurar el nuevo valor del registro, tendrá que reiniciar el equipo para que los cambios surtan efecto.

## <a name="see-also"></a>Vea también

[Crear un objeto de directiva de grupo en Windows 10](https://docs.microsoft.com/windows/security/threat-protection/windows-firewall/create-a-group-policy-object)
