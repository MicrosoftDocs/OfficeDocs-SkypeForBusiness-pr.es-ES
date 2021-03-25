---
title: Configuración de intervalos de puertos y una directiva de calidad de servicio para sus clientes
ms.reviewer: ''
ms:assetid: 287d5cea-7ada-461c-9b4a-9da2af315e71
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204760(v=OCS.15)
ms:contentKeyID: 48183694
mtps_version: v=OCS.15
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: En este artículo se describe cómo configurar intervalos de puertos para sus clientes y cómo configurar directivas de calidad de servicio en Skype Empresarial Server para clientes que se ejecutan en Windows 10.
ms.openlocfilehash: 9cd5fe3fa84c4acd9365e02c0e5801b63d5497d1
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51122434"
---
# <a name="configuring-port-ranges-and-a-quality-of-service-policy-for-your-clients-in-skype-for-business-server"></a>Configuración de intervalos de puertos y una directiva de calidad de servicio para sus clientes en Skype Empresarial Server

En este artículo se describe cómo configurar intervalos de puertos para sus clientes y cómo configurar directivas de calidad de servicio en Skype Empresarial Server para clientes que se ejecutan en Windows 10.

## <a name="configure-port-ranges"></a>Configurar intervalos de puertos

De forma predeterminada, las aplicaciones cliente de Skype Empresarial pueden usar cualquier puerto entre los puertos 1024 y 65535 cuando participan en una sesión de comunicación; esto se debe a que los intervalos de puertos específicos no están habilitados automáticamente para los clientes. Sin embargo, para usar la calidad del servicio, deberá reasignar los distintos tipos de tráfico (audio, vídeo, medios, uso compartido de aplicaciones y transferencia de archivos) a una serie de intervalos de puertos únicos. Para ello, use el cmdlet Set-CsConferencingConfiguration.

> [!NOTE]  
> Los usuarios finales no pueden realizar estos cambios por sí mismos. Los administradores solo pueden realizar cambios de puerto mediante el cmdlet Set-CsConferencingConfiguration puerto.


Puede determinar qué intervalos de puertos se usan actualmente para las sesiones de comunicación ejecutando el siguiente comando desde el Shell de administración de Skype Empresarial Server:

    Get-CsConferencingConfiguration

Suponiendo que no ha realizado ningún cambio en la configuración de conferencia desde que instaló Skype Empresarial Server, debe obtener información que incluya estos valores de propiedad:

    ClientMediaPortRangeEnabled : False
    ClientAudioPort             : 5350
    ClientAudioPortRange        : 40
    ClientVideoPort             : 5350
    ClientVideoPortRange        : 40
    ClientAppSharingPort        : 5350
    ClientAppSharingPortRange   : 40
    ClientFileTransferPort      : 5350
    ClientTransferPortRange     : 40

Si observas de cerca el resultado anterior, verás dos cosas importantes. En primer lugar, la propiedad ClientMediaPortRangeEnabled se establece en False:

    ClientMediaPortRangeEnabled : False

Esto es importante porque, cuando esta propiedad se establece en False, los clientes de Skype Empresarial usarán cualquier puerto disponible entre los puertos 1024 y 65535 cuando participen en una sesión de comunicación; esto es así independientemente de cualquier otra configuración de puerto (por ejemplo, ClientMediaPort o ClientVideoPort). Si desea restringir el uso a un conjunto especificado de puertos (y esto es algo que quiere hacer si planea implementar la calidad del servicio), primero debe habilitar los intervalos de puertos multimedia de cliente. Esto se puede hacer con el siguiente Windows PowerShell comando:

    Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True

El comando anterior habilita los intervalos de puertos multimedia de cliente para la colección global de opciones de configuración de conferencia; sin embargo, esta configuración también se puede aplicar al ámbito del sitio o al ámbito de servicio (solo para el servicio de servidor de conferencia). Para habilitar intervalos de puertos multimedia de cliente para un sitio o servidor específicos, especifique la identidad de ese sitio o servidor al llamar a Set-CsConferencingConfiguration:

    Set-CsConferencingConfiguration -Identity "site:Redmond" -ClientMediaPortRangeEnabled $True

Como alternativa, puede usar este comando para habilitar simultáneamente intervalos de puertos para todas las opciones de configuración de conferencia:

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration  -ClientMediaPortRangeEnabled $True

La segunda cosa importante que observará es que el resultado de ejemplo muestra que, de forma predeterminada, los intervalos de puertos multimedia establecidos para cada tipo de tráfico de red son idénticos:

    ClientAudioPort             : 5350
    ClientVideoPort             : 5350
    ClientAppSharingPort        : 5350
    ClientFileTransferPort      : 5350

Para implementar QoS, cada uno de estos intervalos de puertos tendrá que ser único. Por ejemplo, puede configurar los intervalos de puertos de esta forma:


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


En la tabla anterior, los intervalos de puertos de cliente representan un subconjunto de los intervalos de puertos configurados para los servidores. Por ejemplo, en los servidores, el uso compartido de aplicaciones se configuró para usar los puertos 40803 a 49151; en los equipos cliente, el uso compartido de aplicaciones está configurado para usar los puertos 42000 a 42019. Esto también se hace principalmente para facilitar la administración de QoS: los puertos de cliente no tienen que representar un subconjunto de los puertos usados en el servidor. (Por ejemplo, en los equipos cliente podría configurar el uso compartido de aplicaciones para usar, por ejemplo, los puertos de 10000 a 10019). Sin embargo, se recomienda convertir los intervalos de puertos de cliente en un subconjunto de los intervalos de puertos del servidor.

Además, es posible que haya observado que 8348 puertos se reservaron para el uso compartido de aplicaciones en los servidores, pero solo se reservaron 20 puertos para el uso compartido de aplicaciones en los clientes. Esto también se recomienda, pero no es una regla rápida y dura. En general, puede considerar cada puerto disponible para representar una sola sesión de comunicación: si tiene 100 puertos disponibles en un intervalo de puertos, significa que el equipo en cuestión podría participar en, como máximo, 100 sesiones de comunicación en un momento dado. Dado que los servidores probablemente participarán en muchas más conversaciones que los clientes, tiene sentido abrir muchos más puertos en los servidores que en los clientes. Si se reservan 20 puertos para el uso compartido de aplicaciones en un cliente, un usuario podría participar en 20 sesiones de uso compartido de aplicaciones en el dispositivo especificado y todo al mismo tiempo. Eso debería ser suficiente para la gran mayoría de los usuarios.

Para asignar los intervalos de puertos anteriores a la colección global de opciones de configuración de conferencia, puede usar el siguiente comando del Shell de administración de Skype Empresarial Server:

    Set-CsConferencingConfiguration -Identity global -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

O bien, use este comando para asignar estos mismos intervalos de puertos para todas las opciones de configuración de conferencia:

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

Los usuarios individuales deben cerrar sesión desde Skype Empresarial y, a continuación, volver a iniciar sesión antes de que estos cambios realmente sun efecto.

> [!NOTE]  
> También puede habilitar intervalos de puertos multimedia de cliente y, a continuación, asignar esos intervalos de puertos con un solo comando. Por ejemplo:<BR><CODE>Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20</CODE>

## <a name="configure-quality-of-service-policies-for-clients-running-on-windows-10"></a>Configurar directivas de calidad de servicio para clientes que se ejecutan en Windows 10

Además de especificar intervalos de puertos para su uso por parte de los clientes de Skype Empresarial, también debe crear directivas de calidad de servicio independientes que se aplicarán a los equipos cliente. (Las directivas de calidad de servicio creadas para servidores de conferencia, aplicación y mediación no deben aplicarse a los equipos cliente). Esta información solo se aplica a los equipos que ejecutan el cliente de Skype Empresarial y Windows 10.

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

Para crear una directiva de audio de calidad de servicio para equipos con Windows 10, inicie sesión primero en un equipo donde se haya instalado la administración de directivas de grupo. Abra Administración de directivas de grupo (haga clic **en Inicio**, elija **Herramientas administrativas** y, a continuación, haga clic en **Administración** de directivas de grupo) y, a continuación, realice el siguiente procedimiento:

1.  En Administración de directivas de grupo, busque el contenedor donde se deba crear la nueva directiva. Por ejemplo, si todos los equipos cliente se encuentran en una OU denominada Clientes, la nueva directiva debe crearse en la OU cliente.

2.  Haga clic con el botón secundario en el contenedor adecuado y, a continuación, haga clic en Crear un GPO en este **dominio y vincule aquí**.

3.  En el **cuadro de diálogo Nuevo GPO,** escriba un  nombre para el nuevo objeto de directiva de grupo en el cuadro Nombre y, a continuación, haga clic en **Aceptar**.

4.  Haga clic con el botón secundario en la directiva recién creada y, a continuación, haga clic **en Editar**.

5.  En el Editor de administración de directivas de grupo, **expanda** Configuración del equipo , Expanda Configuración de **Windows**, haga clic con el botón secundario en **QoS** basada en directivas y, a continuación, haga clic **en Crear nueva directiva.**

6.  En el **cuadro de diálogo QoS** basado en directivas, en la página de apertura, escriba un nombre para la nueva directiva en el **cuadro** Nombre. Seleccione **Especificar el valor de DSCP** y, a continuación, defina el valor en **46**. Deje sin seleccionar **Especificar velocidad de salida del acelerador** y, a continuación, haga clic en **Siguiente**.

7.  En la página siguiente, seleccione **Solo aplicaciones** con este nombre ejecutable, **escribaLync.exe** como nombre y, a continuación, haga clic en **Siguiente**. Esta configuración indica a la directiva que sólo priorice el tráfico que coincide con el cliente de Skype Empresarial.

8.  En la tercera página, asegúrese de que todas las direcciones **IP** de origen y cualquier dirección **IP** de destino están seleccionadas y, a continuación, haga clic **en Siguiente**. Con estas dos opciones de configuración activadas, los paquetes se administrarán sin importar qué equipo (dirección IP) los envió ni qué equipo (dirección IP) los recibirá.

9.  En la página cuatro, seleccione **TCP y UDP** en la lista desplegable **Seleccione el protocolo para el que se aplica esta directiva de QoS**. TCP (Transmission Control Protocol) y UDP (User Datagram Protocol) son los dos protocolos de red más usados por Skype Empresarial Server y sus aplicaciones cliente.

10. En el encabezado **Especifique el número de puerto de origen**, seleccione **Desde este intervalo o puerto de origen**. En el cuadro de texto asociado, escriba el intervalo de puertos reservado para las transmisiones de audio. Por ejemplo, si ha reservado los puertos de 50020 a 50039 para el tráfico de audio, escriba el intervalo de puertos con el formato: **50020:50039**. Haga clic en **Finalizar**.

Después de crear la directiva de QoS para audio, deberá crear una segunda directiva para el vídeo. Para ello, siga el mismo procedimiento básico que ha seguido para la directiva de audio, con las siguientes sustituciones:

  - Use un nombre de directiva diferente (y único).

  - Ajuste el valor de DSCP en **34**, en lugar de 46. (Como ya se ha mencionado, no tiene que utilizar el valor 34 para DSCP, sino asignar a DSCP un valor diferente al usado para el audio.)

  - Use el intervalo de puertos configurado anteriormente para el tráfico de vídeo. Por ejemplo, si tiene reservados los puertos 58000 a 58019 para vídeo, establezca el intervalo de puertos en: **58000:58019**.

Si decide crear una directiva para administrar el tráfico de uso compartido de aplicaciones, realice estas sustituciones:

  - Use un nombre de directiva diferente (y único) (por ejemplo, Uso compartido de aplicaciones de **Skype Empresarial Server**).

  - Ajuste el valor de DSCP en **24**, en lugar de 46. (También en este caso, este valor no tiene por qué ser 24, sino que debe ser diferente a los valores de DSCP utilizados para el audio y el vídeo.)

  - Use el intervalo de puertos configurado anteriormente para el tráfico de vídeo. Por ejemplo, si tiene reservados los puertos 42000 a 42019 para uso compartido de aplicaciones, establezca el intervalo de puertos en: **42000:42019**.

Para una directiva de transferencia de archivos:

  - Use un nombre de directiva diferente (y único) (por ejemplo, Transferencias de archivos de **Skype Empresarial Server**).

  - Ajuste el valor de DSCP en **14**. (Una vez más, este valor no tiene por qué ser 14, sino simplemente un código DSCP único.)

  - Use el intervalo de puertos configurado anteriormente para la aplicación. Por ejemplo, si tiene reservados los puertos 42020 a 42039 para uso compartido de aplicaciones, establezca el intervalo de puertos en: **42020:42039**.

Las directivas nuevas que ha creado no tendrán efecto hasta que se actualice Directiva de grupos en los equipos cliente. Aunque la Directiva de grupos se actualiza periódicamente de forma automática, puede forzar una actualización inmediata ejecutando el siguiente comando en todos los equipos en los que es necesario actualizar la Directiva de grupos:

    Gpupdate.exe /force

Este comando se puede ejecutar desde cualquier ventana de comandos que se ejecute con las credenciales de administrador. Para ejecutar una ventana de comando con las credenciales de administrador, haga clic en **Inicio**, haga clic con el botón secundario en **Símbolo del sistema** y, a continuación, haga clic en **Ejecutar como administrador**.

Recuerde que estas directivas deben ir dirigidas a los equipos cliente. No deben aplicarse a los servidores que ejecutan Skype Empresarial Server.

Para asegurarse de que los paquetes de red se marquen con el valor de DSCP adecuado, debe crear también una nueva entrada del Registro en cada equipo, mediante el siguiente procedimiento:

1.  Haga clic en **Inicio** y luego en **Ejecutar**.

2.  En el **cuadro de** diálogo Ejecutar, escriba **regedit** y, a continuación, presione ENTRAR.

3.  En el Editor del Registro, expanda **HKEY \_ LOCAL \_ MACHINE**, **expanda SYSTEM**, **expand CurrentControlSet**, expand **services** y, a continuación, **expande Tcpip**.

4.  Haga clic con el botón secundario en **Tcpip**, elija **Nuevo** y, a continuación, haga clic en **Clave**. Después de crear la nueva clave del Registro, escriba **QoS** y, a continuación, presione ENTRAR para cambiar el nombre de la clave.

5.  Haga clic con el botón secundario en **QoS**, elija **Nuevo** y, a continuación, haga clic en **Valor de cadena**. Después de crear el nuevo valor del Registro, escriba **No usar NLA** y, a continuación, presione ENTRAR para cambiar el nombre del valor.

6.  Haga doble clic en **No usar NLA**. En el cuadro de diálogo Editar **cadena,** escriba **1** en el cuadro **Datos de** valor y, a continuación, haga clic en **Aceptar**.

7.  Cierre el Editor del Registro e arranque el equipo.

### <a name="configure-quality-of-service-on-computers-with-multiple-network-adapters"></a>Configurar la calidad del servicio en equipos con varios adaptadores de red

Si tiene un equipo que tiene varios adaptadores de red, es posible que ocasionalmente se ejecute en problemas en los que los valores de DSCP se muestran como 0x00 en lugar del valor configurado. Esto ocurrirá, generalmente, en equipos en los que uno o más adaptadores de red no pueden acceder al dominio de Active Directory (por ejemplo, si estos adaptadores de red se utilizan para una red privada). En esos casos, los valores DSCP se etiquetarán para los adaptadores que pueden acceder al dominio, pero no se etiquetarán para los adaptadores que no tienen acceso al dominio.

Si desea etiquetar valores DSCP para todos los adaptadores de red de un equipo, incluidos los adaptadores que no tienen acceso a su dominio, deberá agregar y configurar un valor al Registro. Se puede hacer siguiendo este procedimiento:

1.  Haga clic en **Inicio** y luego en **Ejecutar**.

2.  En el **cuadro de** diálogo Ejecutar, escriba **regedit** y, a continuación, presione ENTRAR.

3.  En el Editor del Registro, expanda **HKEY \_ LOCAL \_ MACHINE**, **expanda SYSTEM**, **expand CurrentControlSet**, expand **services** y, a continuación, **expande Tcpip**.

4.  Si no ve una clave de registro con la etiqueta **QoS**, haga clic con el botón secundario en **Tcpip**, seleccione **Nuevo** y, a continuación, haga clic en **Clave**. Después de crear la nueva clave, escriba **QoS** y, a continuación, presione ENTRAR para cambiar el nombre de la tecla.

5.  Haga clic con el botón secundario en **QoS**, elija **Nuevo** y, a continuación, haga clic en **Valor de cadena**. Después de crear el nuevo valor del Registro, escriba **No usar NLA** y, a continuación, presione ENTRAR para cambiar el nombre del valor.

6.  Haga doble clic en **No usar NLA**. En el cuadro de diálogo Editar **cadena,** escriba **1** en el cuadro **Datos de** valor y, a continuación, haga clic en **Aceptar**.

Después de crear y configurar el nuevo valor del Registro, deberá reiniciar el equipo para que los cambios entren en vigor.

## <a name="see-also"></a>Ver también

[Crear un objeto de directiva de grupo en Windows 10](/windows/security/threat-protection/windows-firewall/create-a-group-policy-object)