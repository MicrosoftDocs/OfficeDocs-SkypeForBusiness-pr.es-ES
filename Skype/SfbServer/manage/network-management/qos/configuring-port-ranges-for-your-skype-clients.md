---
title: Configurar intervalos de puertos y una directiva de calidad de servicio para los clientes
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
localization_priority: Normal
description: En este artículo se describe cómo configurar intervalos de puertos para sus clientes y configurar directivas de calidad de servicio en Skype empresarial Server para clientes que se ejecutan en Windows 10.
ms.openlocfilehash: 4d7999634864e222dd627ea3b46a3a3da5c67fe5
ms.sourcegitcommit: 67282b5f2f1aac3e675c4a485f4846deba15deb4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2019
ms.locfileid: "35841472"
---
# <a name="configuring-port-ranges-and-a-quality-of-service-policy-for-your-clients-in-skype-for-business-server"></a>Configuración de intervalos de puertos y una directiva de calidad de servicio para sus clientes en Skype empresarial Server

En este artículo se describe cómo configurar intervalos de puertos para sus clientes y configurar directivas de calidad de servicio en Skype empresarial Server para clientes que se ejecutan en Windows 10.

## <a name="configure-port-ranges"></a>Configurar intervalos de puertos

De forma predeterminada, las aplicaciones cliente de Skype empresarial pueden usar cualquier puerto entre los puertos 1024 y 65535 cuando participan en una sesión de comunicación; Esto se debe a que los intervalos de puertos específicos no se habilitan automáticamente para los clientes. Sin embargo, para usar la calidad de servicio, tendrá que reasignar los diversos tipos de tráfico (audio, vídeo, multimedia, uso compartido de aplicaciones y transferencia de archivos) a una serie de intervalos de puertos únicos. Esto se puede hacer con el cmdlet Set-CsConferencingConfiguration.

> [!NOTE]  
> Los usuarios finales no pueden realizar estos cambios por sí mismos. Los administradores solo pueden hacer cambios en el puerto mediante el cmdlet Set-CsConferencingConfiguration.


Puede determinar qué intervalos de puertos se usan actualmente para las sesiones de comunicación ejecutando el siguiente comando desde el shell de administración de Skype empresarial Server:

    Get-CsConferencingConfiguration

Suponiendo que no ha realizado ningún cambio en la configuración de conferencia después de instalar Skype empresarial Server, debe obtener información que incluya estos valores de propiedades:

    ClientMediaPortRangeEnabled : False
    ClientAudioPort             : 5350
    ClientAudioPortRange        : 40
    ClientVideoPort             : 5350
    ClientVideoPortRange        : 40
    ClientAppSharingPort        : 5350
    ClientAppSharingPortRange   : 40
    ClientFileTransferPort      : 5350
    ClientTransferPortRange     : 40

Si examina detenidamente la salida anterior, verá dos cuestiones de importancia. En primer lugar, la propiedad ClientMediaPortRangeEnabled se establece en false:

    ClientMediaPortRangeEnabled : False

Eso es importante porque, cuando esta propiedad se establece en false, los clientes de Skype empresarial usarán cualquier puerto disponible entre los puertos 1024 y 65535 cuando participen en una sesión de comunicación; Esto es así independientemente de cualquier otra configuración de puertos (por ejemplo, ClientMediaPort o ClientVideoPort). Si desea restringir el uso a un conjunto de puertos especificado (y esto es algo que quiera hacer si tiene previsto implementar la calidad de servicio), primero debe habilitar los intervalos de puertos de los medios de cliente. Esto se puede realizar con el siguiente comando de Windows PowerShell:

    Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True

El comando anterior habilita los intervalos de puertos de medios de cliente para la colección global de opciones de configuración de conferencias; sin embargo, esta configuración también se puede aplicar al ámbito del sitio o al ámbito del servicio (solo para el servicio de servidor de conferencias). Para habilitar los intervalos de puertos de medios de cliente para un sitio o servidor específico, especifique la identidad de ese sitio o servidor cuando llame a set-CsConferencingConfiguration:

    Set-CsConferencingConfiguration -Identity "site:Redmond" -ClientMediaPortRangeEnabled $True

También puede usar este comando para habilitar simultáneamente los intervalos de puertos para todas las opciones de configuración de Conferencia:

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration  -ClientMediaPortRangeEnabled $True

La segunda importancia que observará es que la salida de ejemplo muestra que, de forma predeterminada, los intervalos de puertos de medios establecidos para cada tipo de tráfico de red son idénticos:

    ClientAudioPort             : 5350
    ClientVideoPort             : 5350
    ClientAppSharingPort        : 5350
    ClientFileTransferPort      : 5350

Para implementar QoS, cada uno de estos intervalos de puertos tendrá que ser único. Por ejemplo, puede configurar los intervalos de puertos como este:


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Tipo de tráfico de cliente</th>
<th>Inicio de Puerto</th>
<th>Intervalo de puertos</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Audio</p></td>
<td><p>50020</p></td>
<td><p>veinte</p></td>
</tr>
<tr class="even">
<td><p>Vídeo</p></td>
<td><p>58000</p></td>
<td><p>veinte</p></td>
</tr>
<tr class="odd">
<td><p>Uso compartido de aplicaciones</p></td>
<td><p>42000</p></td>
<td><p>veinte</p></td>
</tr>
<tr class="even">
<td><p>Transferencia de archivos</p></td>
<td><p>42020</p></td>
<td><p>veinte</p></td>
</tr>
</tbody>
</table>


En la tabla anterior, los intervalos de puertos de cliente representan un subconjunto de los intervalos de puertos configurados para los servidores. Por ejemplo, en los servidores, el uso compartido de aplicaciones se configuró para usar los puertos 40803 a 49151; en los equipos cliente, el uso compartido de aplicaciones está configurado para usar los puertos de 42000 a 42019. Esto también se realiza principalmente para facilitar la administración de QoS: los puertos de cliente no tienen que representar un subconjunto de los puertos que se usan en el servidor. (Por ejemplo, en los equipos cliente, puede configurar el uso compartido de aplicaciones para que lo use, por ejemplo, los puertos 10000 a 10019). Sin embargo, le recomendamos que los intervalos de puertos de cliente sean un subconjunto de intervalos de puertos de servidor.

Además, es posible que haya observado que se han reservado 8348 puertos para el uso compartido de aplicaciones en los servidores, pero solo se reservaron 20 puertos para el uso compartido de aplicaciones en los clientes. Esto también se recomienda, pero no es una regla de hardware y rápido. En general, puede considerar que cada puerto disponible representa una única sesión de comunicación: Si tiene 100 puertos disponibles en un intervalo de puertos, significa que el equipo en cuestión puede participar, como máximo, de las sesiones de comunicación de 100 en cualquier momento. Dado que es probable que los servidores adquieran parte de muchas más conversaciones que clientes, tiene sentido abrir muchos más puertos en servidores que en los clientes. La reserva de 20 puertos para el uso compartido de aplicaciones en un cliente significa que un usuario puede participar en 20 sesiones de uso compartido de aplicaciones en el dispositivo especificado, y todas al mismo tiempo. Eso debería ser suficiente para la gran mayoría de los usuarios.

Para asignar los intervalos de puertos anteriores a la colección global de opciones de configuración de conferencias, puede usar el siguiente comando de Shell de administración de Skype empresarial Server:

    Set-CsConferencingConfiguration -Identity global -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

O bien, use este comando para asignar estos mismos intervalos de puerto para todas las opciones de configuración de Conferencia:

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

Los usuarios individuales deben cerrar sesión en Skype empresarial y, a continuación, iniciar sesión de nuevo antes de que estos cambios se hagan efectivos.

> [!NOTE]  
> También puede habilitar intervalos de puertos de medios de cliente y, a continuación, asignar esos intervalos de puertos con un solo comando. Por ejemplo:<BR><CODE>Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20</CODE>

## <a name="configure-quality-of-service-policies-for-clients-running-on-windows-10"></a>Configurar directivas de calidad de servicio para clientes que ejecutan Windows 10

Además de especificar los intervalos de puertos para que los usen sus clientes de Skype empresarial, también debe crear directivas de calidad de servicio por separado que se aplicarán a los equipos cliente. (Las directivas de calidad de servicio creadas para servidores de conferencia, aplicaciones y mediación no se deben aplicar a los equipos cliente). Esta información solo se aplica a los equipos que ejecutan el cliente de Skype empresarial y Windows 10.

En el ejemplo siguiente se usa este conjunto de intervalos de puerto para crear una directiva de audio y una directiva de vídeo:


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Tipo de tráfico de cliente</th>
<th>Inicio de Puerto</th>
<th>Intervalo de puertos</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Audio</p></td>
<td><p>50020</p></td>
<td><p>veinte</p></td>
</tr>
<tr class="even">
<td><p>Vídeo</p></td>
<td><p>58000</p></td>
<td><p>veinte</p></td>
</tr>
<tr class="odd">
<td><p>Uso compartido de aplicaciones</p></td>
<td><p>42000</p></td>
<td><p>veinte</p></td>
</tr>
<tr class="even">
<td><p>Transferencia de archivos</p></td>
<td><p>42020</p></td>
<td><p>veinte</p></td>
</tr>
</tbody>
</table>

Para crear una directiva de audio de calidad de servicio para equipos con Windows 10, primero inicie sesión en un equipo en el que se haya instalado administración de directivas de grupo. Abra administración de directivas de grupo (haga clic en **Inicio**, seleccione **herramientas administrativas**y, a continuación, haga clic en **Administración de directivas de grupo**) y realice el siguiente procedimiento:

1.  En administración de directivas de grupo, busque el contenedor en el que se debe crear la nueva Directiva. Por ejemplo, si todos los equipos cliente se encuentran en una unidad organizativa denominada clientes, la nueva Directiva debe crearse en la uo cliente.

2.  Haga clic con el botón secundario en el contenedor correspondiente y, después, haga clic en **crear un GPO en este dominio y vincúlelo aquí**.

3.  En el cuadro de diálogo **nuevo GPO** , escriba un nombre para el nuevo objeto de directiva de grupo en el cuadro **nombre** y, a continuación, haga clic en **Aceptar**.

4.  Haga clic con el botón secundario en la Directiva recién creada y, después, haga clic en **Editar**.

5.  En el editor de administración de directivas de grupo, expanda **configuración del equipo**, expanda **configuración de Windows**, haga clic con el botón secundario en **QoS basada en directivas**y, a continuación, haga clic en **crear nueva Directiva**.

6.  En el cuadro de diálogo **QoS basado en directivas** , en la página de apertura, escriba un nombre para la nueva Directiva en el cuadro **nombre** . Seleccione **especificar valor de DSCP** y establezca el valor en **46**. Deje la **tasa de límite saliente** desactivada y, a continuación, haga clic en **siguiente**.

7.  En la página siguiente, seleccione **solo las aplicaciones con este nombre de archivo ejecutable**, escriba **Lync. exe** como nombre y, a continuación, haga clic en **siguiente**. Esta configuración indica a la Directiva que solo asigne prioridad al tráfico coincidente del cliente de Skype empresarial.

8.  En la tercera página, asegúrese de que **todas las direcciones IP de origen** y **cualquier dirección IP de destino** estén seleccionadas y, a continuación, haga clic en **siguiente**. Estas dos opciones de configuración garantizan que los paquetes se administrarán independientemente del equipo (dirección IP) que hayan enviado esos paquetes y qué equipo (dirección IP) recibirá esos paquetes.

9.  En la cuarta página, seleccione **TCP y UDP** en la lista desplegable **seleccionar el protocolo de esta directiva de QoS** . TCP (Protocolo de control de transmisión) y UDP (Protocolo de datagrama de usuario) son los dos protocolos de red más usados por Skype empresarial Server y sus aplicaciones cliente.

10. En el encabezado, **especifique el número de puerto de origen**, seleccione **de este rango o puerto de origen**. En el cuadro de texto que acompaña, escriba el intervalo de puertos reservado para las transtransmisións de audio. Por ejemplo, si ha reservado los puertos 50020 a través de los puertos 50039 para el tráfico de audio, escriba el intervalo de puertos con este formato: **50020:50039**. Haga clic en **Finalizar**.

Después de crear la directiva QoS para el audio, debe crear una segunda Directiva para el vídeo. Para crear una directiva para el vídeo, siga el mismo procedimiento básico que siguió al crear la Directiva de audio y realizar estas sustituciones:

  - Use un nombre de directiva diferente (y único).

  - Establezca el valor de DSCP en **34** en lugar de 46. (Como se ha indicado anteriormente, no tiene que usar el valor de DSCP 34; simplemente debe asignar un valor de DSCP diferente al utilizado para el audio).

  - Use el intervalo de puertos configurado previamente para el tráfico de vídeo. Por ejemplo, si ha reservado los puertos 58000 a 58019 para el vídeo, establezca el intervalo de puertos en: **58000:58019**.

Si decide crear una directiva para administrar el tráfico de uso compartido de aplicaciones, realice estas sustituciones:

  - Use un nombre de directiva diferente (y único) (por ejemplo, **uso compartido de aplicaciones de Skype empresarial Server**).

  - Establezca el valor de DSCP en **24** en lugar de 46. (Nuevamente, este valor no tiene que ser 24; simplemente debe ser diferente de los valores de DSCP usados para el audio y el vídeo).

  - Use el intervalo de puertos configurado previamente para el tráfico de vídeo. Por ejemplo, si ha reservado los puertos 42000 a 42019 para el uso compartido de aplicaciones, establezca el intervalo de puertos en: **42000:42019**.

Para una directiva de transferencia de archivos:

  - Use un nombre de directiva diferente (y único) (por ejemplo, transferencias de **archivos de Skype empresarial Server**).

  - Establezca el valor de DSCP en **14**. (Nuevamente, este valor no tiene que ser 14; simplemente debe ser un código DSCP único).

  - Use el intervalo de puertos configurado previamente para la aplicación. Por ejemplo, si ha reservado los puertos 42020 a 42039 para el uso compartido de aplicaciones, establezca el intervalo de puertos en: **42020:42039**.

Las nuevas directivas que ha creado no tendrán efecto hasta que se actualice la Directiva de grupo en los equipos cliente. Aunque la directiva de grupo se actualiza periódicamente por sí misma, se puede forzar una actualización inmediata si se ejecuta el siguiente comando en cada equipo en el que se tenga que actualizar la directiva de grupo:

    Gpupdate.exe /force

Este comando se puede ejecutar desde cualquier ventana de comandos que se ejecute con las credenciales del administrador. Para abrir una ventana de comandos con las credenciales del administrador, haga clic en **Inicio**, haga clic con el botón derecho en **Símbolo del sistema** y, a continuación, haga clic en **Ejecutar como administrador**.

Tenga en cuenta que estas directivas deben ir dirigidas a los equipos cliente. No se deben aplicar a servidores que ejecuten Skype empresarial Server.

Para asegurarse de que los paquetes de red estén marcados con el valor de DSCP adecuado, también debe crear una nueva entrada de registro en cada equipo completando el procedimiento siguiente:

1.  Haga clic en  **Inicio ** y en  **Ejecutar **.

2.  En el cuadro de diálogo **Ejecutar** , **** escriba regedit y, a continuación, presione Entrar.

3.  En el editor del registro, expanda el **equipo local\_\_HKEY**, expanda **sistema**, expanda **CurrentControlSet**, expanda **Services**y, a continuación, expanda **TCPIP**.

4.  Haga clic con el botón derecho en **TCPIP**, seleccione **nuevo**y, a continuación, haga clic en **clave**. Después de crear la nueva clave del registro, escriba **QoS**y, a continuación, presione Entrar para cambiar el nombre de la clave.

5.  Haga clic con el botón derecho en **QoS**, seleccione **nuevo**y, a continuación, haga clic en **valor de cadena**. Después de crear el nuevo valor del registro, escriba **no use NLA**y, a continuación, presione Entrar para cambiar el nombre del valor.

6.  Haga doble clic en **no usar NLA**. En el cuadro de diálogo **Editar cadena** , escriba **1** en el cuadro **datos del valor** y, a continuación, haga clic en **Aceptar**.

7.  Cierre el editor del registro y eboot su equipo.

### <a name="configure-quality-of-service-on-computers-with-multiple-network-adapters"></a>Configurar la calidad de servicio en equipos con varios adaptadores de red

Si tiene un equipo con varios adaptadores de red, es posible que ocasionalmente se encuentre con problemas en los que los valores de DSCP se muestran como 0x00 en lugar de con el valor configurado. Esto suele ocurrir en equipos en los que uno o varios de los adaptadores de red no pueden obtener acceso al dominio de Active Directory (por ejemplo, si se usan para una red privada). En casos como ese, los valores DSCP se etiquetarán para los adaptadores que pueden acceder al dominio, pero no se etiquetarán para los adaptadores que no tienen acceso al dominio.

Si desea etiquetar valores DSCP para todos los adaptadores de red de un equipo, incluidos los adaptadores que no tienen acceso a su dominio, tendrá que agregar y configurar un valor en el registro. Esto se puede realizar mediante el siguiente procedimiento:

1.  Haga clic en  **Inicio ** y en  **Ejecutar **.

2.  En el cuadro de diálogo **Ejecutar** , **** escriba regedit y, a continuación, presione Entrar.

3.  En el editor del registro, expanda el **equipo local\_\_HKEY**, expanda **sistema**, expanda **CurrentControlSet**, expanda **Services**y, a continuación, expanda **TCPIP**.

4.  Si no ve una clave del registro denominada **QoS** , haga clic con el botón derecho en **TCPIP**, seleccione **nuevo**y, después, haga clic en **clave**. Después de crear la nueva clave, escriba **QoS**y, a continuación, presione Entrar para cambiar el nombre de la clave.

5.  Haga clic con el botón derecho en **QoS**, seleccione **nuevo**y, a continuación, haga clic en **valor de cadena**. Después de crear el nuevo valor del registro, escriba **no use NLA**y, a continuación, presione Entrar para cambiar el nombre del valor.

6.  Haga doble clic en **no usar NLA**. En el cuadro de diálogo **Editar cadena** , escriba **1** en el cuadro **datos del valor** y, a continuación, haga clic en **Aceptar**.

Después de crear y configurar el nuevo valor del registro, tendrá que reiniciar el equipo para que los cambios surtan efecto.

## <a name="see-also"></a>Vea también

[Crear un objeto de directiva de grupo en Windows 10](https://docs.microsoft.com/en-us/windows/security/threat-protection/windows-firewall/create-a-group-policy-object)
