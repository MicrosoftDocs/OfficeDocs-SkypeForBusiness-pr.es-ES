---
title: 'Lync Server 2013: configurar directivas de calidad de servicio para clientes que ejecutan Windows 7 o Windows 8'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Quality of Service policies for clients running on Windows 7 or Windows 8
ms:assetid: efff2b98-b3fb-4183-a4f0-329a9105ce2c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205371(v=OCS.15)
ms:contentKeyID: 48185785
ms.date: 03/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 05835b74f12d5e2d28036b100fd84f207a64e67c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046093"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-quality-of-service-policies-in-lync-server-2013-for-clients-running-on-windows-7-or-windows-8"></a>Configurar directivas de calidad de servicio en Lync Server 2013 para clientes que ejecutan Windows 7 o Windows 8

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2016-03-29_

Además de especificar intervalos de puertos para su uso por parte de los clientes de Lync, también debe crear directivas de calidad de servicio independientes que se aplicarán a los equipos cliente. (Las directivas de calidad de servicio creadas para los servidores de conferencia, aplicación y mediación no deben aplicarse a los equipos cliente). Esta información solo se aplica a los equipos que ejecutan el cliente de Lync 2013 y Windows 7 o Windows 8.

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


Para crear una directiva de audio de calidad de servicio para equipos con Windows 7 o Windows 8, primero inicie sesión en un equipo en el que se haya instalado administración de directivas de grupo. Abra la Administración de directivas de grupo (haga clic en **Inicio**, seleccione **Herramientas administrativas** y, a continuación, haga clic en **Administración de directivas de grupo**) y, a continuación, complemente el siguiente procedimiento:

1.  En la Administración de directivas de grupo, busque el contenedor en el que se deba crear la nueva directiva. Por ejemplo, si todos los equipos cliente están ubicados en una OU denominada Clientes, la nueva directiva se deberá crear en la OU Clientes.

2.  Haga clic con el botón secundario en el contenedor apropiado y, a continuación, haga clic en **Crear un GPO en este dominio y vincularlo aquí**.

3.  En el cuadro de diálogo **Nuevo GPO**, escriba un nombre para el nuevo objeto de directiva de grupo en el cuadro **Nombre** (por ejemplo, **Lync Audio**) y, a continuación, haga clic en **Aceptar**.

4.  Haga clic con el botón secundario en la directiva recién creada y, a continuación, haga clic en **Editar**.

5.  En el Editor de la Administración de directivas de grupo, expanda **Configuración de equipo**, expanda **Directivas**, expanda **Configuración de Windows**, haga clic con el botón secundario en **QoS basada en directivas** y, a continuación, haga clic en **Crear nueva directiva**.

6.  En el cuadro de diálogo **QoS basada en directivas**, en la página de inicio, escriba un nombre para la directiva nueva (por ejemplo, **Lync Audio**) en el cuadro **Nombre**. Seleccione **Especificar el valor de DSCP** y, a continuación, defina el valor en **46**. Deje sin seleccionar **Especificar velocidad de salida del acelerador** y, a continuación, haga clic en **Siguiente**.

7. En la página siguiente, seleccione **solo aplicaciones con este nombre de archivo ejecutable** y escriba el nombre **Lync. exe**y, a continuación, haga clic en **siguiente**. Esta configuración le indica a la Directiva que solo Asigne prioridades de tráfico que coincidan con el cliente de Lync.

8.  En la tercera página, compruebe que las opciones **Cualquier dirección IP de origen** y **Cualquier dirección IP de destino** están seleccionadas y haga clic en **Siguiente**. Estas dos opciones garantizan que se gestionarán todos los paquetes, sin tener en cuenta el equipo (o dirección IP) que los envió y el equipo (o dirección IP) que los recibirá.

9.  En la página cuatro, seleccione **TCP y UDP** en la lista desplegable **Seleccione el protocolo para el que se aplica esta directiva de QoS**. TCP (Protocolo de control de transmisión) y UDP (Protocolo de datagramas de usuario) son los dos protocolos de red más usados por Lync Server y sus aplicaciones cliente.

10. En el encabezado **Especifique el número de puerto de origen**, seleccione **Desde este intervalo o puerto de origen**. En el cuadro de texto asociado, escriba el intervalo de puertos reservado para las transmisiones de audio. Por ejemplo, si ha reservado los puertos de 50020 a 50039 para el tráfico de audio, escriba el intervalo de puertos con el formato: **50020:50039**. Haga clic en **Finalizar**.

Después de crear la directiva de QoS para audio, deberá crear una segunda directiva para el vídeo. Para ello, siga el mismo procedimiento básico que ha seguido para la directiva de audio, con las siguientes sustituciones:

  - Use un nombre de directiva diferente (y único), por ejemplo, **Lync Video**.

  - Ajuste el valor de DSCP en **34**, en lugar de 46. (Como ya se ha mencionado, no tiene que utilizar el valor 34 para DSCP, sino asignar a DSCP un valor diferente al usado para el audio.)

  - Use el intervalo de puertos para el tráfico de vídeo que ha configurado anteriormente. Por ejemplo, si reservó los puertos de 58000 a 58019 para el vídeo, ajuste el intervalo de puertos del siguiente modo: **58000:58019**.

Si decide crear una directiva para la administración del tráfico del uso compartido de aplicaciones, realice las siguientes sustituciones:

  - Use un nombre de directiva diferente (y único), como puede ser **Lync Server Application Sharing**.

  - Ajuste el valor de DSCP en **24**, en lugar de 46. (También en este caso, este valor no tiene por qué ser 24, sino que debe ser diferente a los valores de DSCP utilizados para el audio y el vídeo.)

  - Use el intervalo de puertos para el tráfico de vídeo que ha configurado anteriormente. Por ejemplo, si reservó los puertos de 42000 a 42019 para el uso compartido de aplicaciones, ajuste el intervalo de puertos del siguiente modo: **42019:42000**.

Para una directiva de transferencia de archivos:

  - Use un nombre de directiva diferente (y único), como puede ser **Lync Server File Transfer**.

  - Ajuste el valor de DSCP en **14**. (Una vez más, este valor no tiene por qué ser 14, sino simplemente un código DSCP único.)

  - Use el intervalo de puertos configurado anteriormente para la aplicación. Por ejemplo, si reservó los puertos de 42020 a 42039 para el uso compartido de aplicaciones, ajuste el intervalo de puertos del siguiente modo: **42039:42020**.

Las directivas nuevas que ha creado no tendrán efecto hasta que se actualice Directiva de grupos en los equipos cliente. Aunque la Directiva de grupos se actualiza periódicamente de forma automática, puede forzar una actualización inmediata ejecutando el siguiente comando en todos los equipos en los que es necesario actualizar la Directiva de grupos:

    Gpudate.exe /force

Este comando se puede ejecutar desde cualquier ventana de comandos que se ejecute con las credenciales de administrador. Para ejecutar una ventana de comando con las credenciales de administrador, haga clic en **Inicio**, haga clic con el botón secundario en **Símbolo del sistema** y, a continuación, haga clic en **Ejecutar como administrador**.

Recuerde que estas directivas deben ir dirigidas a los equipos cliente. No se deben aplicar a los servidores que ejecutan Lync Server.

Para asegurarse de que los paquetes de red se marquen con el valor de DSCP adecuado, debe crear también una nueva entrada del Registro en cada equipo, mediante el siguiente procedimiento:

1.  Haga clic en **Inicio** y, a continuación, en **Ejecutar**.

2.  En el cuadro de diálogo **Ejecutar**, escriba **regedit** y, a continuación, presione ENTRAR.

3.  En el editor del registro, expanda el **equipo local\_\_HKEY**, expanda **sistema**, expanda **CurrentControlSet**, expanda **servicios**y, a continuación, expanda **TCPIP**.

4.  Haga clic con el botón secundario en **Tcpip**, elija **Nuevo** y, a continuación, haga clic en **Clave**. Después de que se cree una nueva clave del Registro, escriba **QoS** y presione ENTRAR para cambiar el nombre de la clave.

5.  Haga clic con el botón secundario en **QoS**, elija **Nuevo** y, a continuación, haga clic en **Valor de cadena**. Después de que se cree un nuevo valor del Registro, escriba **No usar NLA** y presione ENTRAR para cambiar el nombre del valor.

6.  Haga doble clic en **No usar NLA**. En el cuadro de diálogo **Editar cadena**, escriba **1** en el cuadro **Datos del valor** y, a continuación, haga clic en **Aceptar**.

7.  Cierre el Editor del Registro y reinicie el equipo.

<div>

## <a name="configuring-quality-of-service-on-computers-with-multiple-network-adapters"></a>Configuración de la Calidad de servicio en equipos con varios adaptadores de red

Si tiene un equipo con varios adaptadores de red, habrá ocasiones en las que los valores DSCP se muestren como 0x00, en lugar del valor configurado. Esto ocurrirá, generalmente, en equipos en los que uno o más adaptadores de red no pueden acceder al dominio de Active Directory (por ejemplo, si estos adaptadores de red se utilizan para una red privada). En esos casos, los valores DSCP se etiquetarán para los adaptadores que pueden acceder al dominio, pero no se etiquetarán para los adaptadores que no tienen acceso al dominio.

Si desea etiquetar valores DSCP para todos los adaptadores de red de un equipo, incluidos los que no tienen acceso a su dominio, tendrá que agregar y configurar un valor en el registro. Para ello:

1.  Haga clic en **Inicio** y, a continuación, en **Ejecutar **.

2.  En el cuadro de diálogo **Ejecutar**, escriba **regedit** y, a continuación, presione ENTRAR.

3.  En el editor del registro, expanda el **equipo local\_\_HKEY**, expanda **sistema**, expanda **CurrentControlSet**, expanda **servicios**y, a continuación, expanda **TCPIP**.

4.  Si no ve una clave de registro con la etiqueta **QoS**, haga clic con el botón secundario en **Tcpip**, seleccione **Nuevo** y, a continuación, haga clic en **Clave**. Después de crear la clave nueva, escriba **QoS** y pulse ENTRAR para cambiarle el nombre.

5.  Haga clic con el botón secundario en **QoS**, elija **Nuevo** y, a continuación, haga clic en **Valor de cadena**. Cuando se haya creado el nuevo valor de registro, escriba **No usar NLA** y presione ENTRAR para cambiar el nombre al valor.

6.  Haga doble clic en **No usar NLA**. En el cuadro de diálogo **Editar cadena**, escriba **1** en el cuadro **Datos del valor** y, a continuación, haga clic en **Aceptar**.

Después de crear y configurar el nuevo valor de registro, tendrá que reiniciar el equipo para que los cambios surtan efecto.

</div>

</div>

<span> </span>

</div>

</div>

</div>

