---
title: 'Lync Server 2013: configuración de directivas de calidad de servicio para clientes que ejecutan Windows 7 o Windows 8'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Quality of Service policies for clients running on Windows 7 or Windows 8
ms:assetid: efff2b98-b3fb-4183-a4f0-329a9105ce2c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205371(v=OCS.15)
ms:contentKeyID: 48185785
ms.date: 03/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b36c16056ef378910dc0cd5c885dc7b5d896d860
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842182"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-quality-of-service-policies-in-lync-server-2013-for-clients-running-on-windows-7-or-windows-8"></a>Configurar directivas de calidad de servicio en Lync Server 2013 para clientes que funcionen en Windows 7 o Windows 8

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2016-03-29_

Además de especificar intervalos de puerto para que los usen sus clientes de Lync, también debe crear directivas de calidad de servicio por separado que se aplicarán a los equipos cliente. (Las directivas de calidad de servicio creadas para servidores de conferencia, aplicaciones y mediación no se deben aplicar a los equipos cliente). Esta información se aplica únicamente a los equipos que ejecutan el cliente de Lync 2013 y Windows 7 o Windows 8.

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


Para crear una directiva de audio de calidad de servicio para equipos con Windows 7 o Windows 8, primero inicie sesión en un equipo en el que se haya instalado administración de directivas de grupo. Abra administración de directivas de grupo (haga clic en **Inicio**, seleccione **herramientas administrativas**y, a continuación, haga clic en **Administración de directivas de grupo**) y realice el siguiente procedimiento:

1.  En administración de directivas de grupo, busque el contenedor en el que se debe crear la nueva Directiva. Por ejemplo, si todos los equipos cliente se encuentran en una unidad organizativa denominada clientes, la nueva Directiva debe crearse en la uo cliente.

2.  Haga clic con el botón secundario en el contenedor correspondiente y luego haga clic en **crear un GPO en este dominio y vincúlelo aquí**.

3.  En el cuadro de diálogo **nuevo GPO** , escriba un nombre para el nuevo objeto de directiva de grupo en el cuadro **nombre** (por ejemplo, **audio de Lync**) y, a continuación, haga clic en **Aceptar**.

4.  Haga clic con el botón secundario en la Directiva recién creada y luego haga clic en **Editar**.

5.  En el editor de administración de directivas de grupo, expanda **configuración del equipo**, expanda **directivas**, expanda **configuración de Windows**, haga clic con el botón secundario en **QoS basada en directivas**y, a continuación, haga clic en **crear nueva Directiva**.

6.  En el cuadro de diálogo **QoS basado en directivas** , en la página de apertura, escriba un nombre para la nueva Directiva (por ejemplo, **audio de Lync**) en el cuadro **nombre** . Seleccione **especificar valor de DSCP** y establezca el valor en **46**. Deje la **tasa de límite saliente** desactivada y, a continuación, haga clic en **siguiente**.

7.  En la página siguiente, asegúrese de que **todas las aplicaciones** está seleccionada y, a continuación, haga clic en **siguiente**. Esta configuración instruye a la red para que busque todos los paquetes con un marcado de DSCP de 46, no solo los paquetes creados por una aplicación específica.

8.  En la tercera página, asegúrese de que **todas las direcciones IP de origen** y **cualquier dirección IP de destino** estén seleccionadas y, a continuación, haga clic en **siguiente**. Estas dos opciones de configuración garantizan que los paquetes se administrarán independientemente del equipo (dirección IP) que hayan enviado esos paquetes y qué equipo (dirección IP) recibirá esos paquetes.

9.  En la cuarta página, seleccione **TCP y UDP** en la lista desplegable **seleccionar el protocolo de esta directiva de QoS** . TCP (Protocolo de control de transmisión) y UDP (Protocolo de datagrama de usuario) son los dos protocolos de red más usados por Lync Server y sus aplicaciones cliente.

10. En el encabezado, **especifique el número de puerto de origen**, seleccione **de este rango o puerto de origen**. En el cuadro de texto que acompaña, escriba el intervalo de puertos reservado para las transtransmisións de audio. Por ejemplo, si ha reservado los puertos 50020 a través de los puertos 50039 para el tráfico de audio, escriba el intervalo de puertos con este formato: **50020:50039**. Haga clic en **Finalizar**.

Después de crear la directiva QoS para el audio, debe crear una segunda Directiva para el vídeo. Para crear una directiva para el vídeo, siga el mismo procedimiento básico que siguió al crear la Directiva de audio y realizar estas sustituciones:

  - Use un nombre de directiva diferente (y único) (por ejemplo, **vídeo de Lync**).

  - Establezca el valor de DSCP en **34** en lugar de 46. (Como se ha indicado anteriormente, no tiene que usar el valor de DSCP 34; simplemente debe asignar un valor de DSCP diferente al utilizado para el audio).

  - Use el intervalo de puertos configurado previamente para el tráfico de vídeo. Por ejemplo, si ha reservado los puertos 58000 a 58019 para el vídeo, establezca el intervalo de puertos en: **58000:58019**.

Si decide crear una directiva para administrar el tráfico de uso compartido de aplicaciones, realice estas sustituciones:

  - Use un nombre de directiva diferente (y único) (por ejemplo, **compartir aplicaciones de Lync Server**).

  - Establezca el valor de DSCP en **24** en lugar de 46. (Nuevamente, este valor no tiene que ser 24; simplemente debe ser diferente de los valores de DSCP usados para el audio y el vídeo).

  - Use el intervalo de puertos configurado previamente para el tráfico de vídeo. Por ejemplo, si ha reservado los puertos 42000 a 42019 para el uso compartido de aplicaciones, establezca el intervalo de puertos en este: **42000:42019**.

Para una directiva de transferencia de archivos:

  - Use un nombre de directiva diferente (y único) (por ejemplo, transferencias de **archivos de Lync Server**).

  - Establezca el valor de DSCP en **14**. (Nuevamente, este valor no tiene que ser 14; simplemente debe ser un código DSCP único).

  - Use el intervalo de puertos configurado previamente para la aplicación. Por ejemplo, si ha reservado los puertos 42020 a 42039 para el uso compartido de aplicaciones, establezca el intervalo de puertos en este: **42020:42039**.

Las nuevas directivas que ha creado no tendrán efecto hasta que se actualice la Directiva de grupo en los equipos cliente. Aunque la directiva de grupo se actualiza periódicamente por sí misma, se puede forzar una actualización inmediata si se ejecuta el siguiente comando en cada equipo en el que se tenga que actualizar la directiva de grupo:

    Gpudate.exe /force

Este comando se puede ejecutar desde cualquier ventana de comandos que se ejecute con las credenciales del administrador. Para abrir una ventana de comandos con las credenciales del administrador, haga clic en **Inicio**, haga clic con el botón derecho en **Símbolo del sistema** y, a continuación, haga clic en **Ejecutar como administrador**.

Tenga en cuenta que estas directivas deben ir dirigidas a los equipos cliente. No se deben aplicar a servidores que ejecuten Lync Server.

Para asegurarse de que los paquetes de red estén marcados con el valor de DSCP adecuado, también debe crear una nueva entrada de registro en cada equipo completando el procedimiento siguiente:

1.  Haga clic en **Inicio** y, después, en **Ejecutar**.

2.  En el cuadro de diálogo **Ejecutar** , **** escriba regedit y, a continuación, presione Entrar.

3.  En el editor del registro, expanda el **equipo local\_\_HKEY**, expanda **sistema**, expanda **CurrentControlSet**, expanda **Services**y, a continuación, expanda **TCPIP**.

4.  Haga clic con el botón derecho en **TCPIP**, seleccione **nuevo**y, a continuación, haga clic en **clave**. Después de crear la nueva clave del registro, escriba **QoS** y, a continuación, presione Entrar para cambiar el nombre de la clave.

5.  Haga clic con el botón derecho en **QoS**, seleccione **nuevo**y, a continuación, haga clic en **valor de cadena**. Después de crear el nuevo valor del registro, escriba **no use NLA** y, a continuación, presione Entrar para cambiar el nombre del valor.

6.  Haga doble clic en **no usar NLA**. En el cuadro de diálogo **Editar cadena** , escriba **1** en el cuadro **datos del valor** y, a continuación, haga clic en **Aceptar**.

7.  Cierre el editor del registro y, a continuación, reinicie el equipo.

<div>

## <a name="configuring-quality-of-service-on-computers-with-multiple-network-adapters"></a>Configuración de la calidad de servicio en equipos con varios adaptadores de red

Si tiene un equipo con varios adaptadores de red, ocasionalmente puede encontrarse con problemas en los que los valores de DSCP se muestran como 0x00 en lugar del valor configurado. Esto suele ocurrir en equipos en los que uno o varios de los adaptadores de red no pueden obtener acceso al dominio de Active Directory (por ejemplo, si se usan para una red privada). En casos como ese, los valores DSCP se etiquetarán para los adaptadores que pueden acceder al dominio, pero no se etiquetarán para los adaptadores que no tienen acceso al dominio.

Si desea etiquetar valores DSCP para todos los adaptadores de red de un equipo, incluidos los adaptadores que no tienen acceso a su dominio, tendrá que agregar y configurar un valor en el registro. Esto se puede realizar mediante el siguiente procedimiento:

1.  Haga clic en **Inicio** y, después, en **Ejecutar**.

2.  En el cuadro de diálogo **Ejecutar** , **** escriba regedit y, a continuación, presione Entrar.

3.  En el editor del registro, expanda el **equipo local\_\_HKEY**, expanda **sistema**, expanda **CurrentControlSet**, expanda **Services**y, a continuación, expanda **TCPIP**.

4.  Si no ve una clave del registro denominada **QoS** , haga clic con el botón derecho en **TCPIP**, seleccione **nuevo**y, después, haga clic en **clave**. Una vez creada la nueva clave, escriba **QoS** y, a continuación, presione Entrar para cambiar el nombre de la clave.

5.  Haga clic con el botón derecho en **QoS**, seleccione **nuevo**y, a continuación, haga clic en **valor de cadena**. Después de crear el nuevo valor del registro, escriba **no use NLA** y, a continuación, presione Entrar para cambiar el nombre del valor.

6.  Haga doble clic en **no usar NLA**. En el cuadro de diálogo **Editar cadena** , escriba **1** en el cuadro **datos del valor** y, a continuación, haga clic en **Aceptar**.

Después de crear y configurar el nuevo valor del registro, tendrá que reiniciar el equipo para que los cambios surtan efecto.

</div>

</div>

<span> </span>

</div>

</div>

</div>

