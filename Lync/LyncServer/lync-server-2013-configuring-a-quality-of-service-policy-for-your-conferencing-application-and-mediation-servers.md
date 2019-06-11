---
title: 'Lync Server 2013: Configurar la directiva de calidad de servicio para los servidores de conferencia, aplicación y mediación'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring a Quality of Service policy for your Conferencing, Application, and Mediation servers
ms:assetid: 8adcbbc5-c9f5-476d-ab7f-72e61859cacf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205076(v=OCS.15)
ms:contentKeyID: 48184769
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 47a79835fb19f5a30a11eac4859f133aeec5c8cb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842308"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-a-quality-of-service-policy-in-lync-server-2013-for-your-conferencing-application-and-mediation-servers"></a>Configurar la directiva de calidad de servicio para los servidores de conferencia, aplicación y mediación en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-06-23_

La configuración de intervalos de puertos facilita el uso de la calidad de servicio al garantizar que todo el tráfico de un tipo específico (por ejemplo, todo el tráfico de audio) se desplaza por el mismo conjunto de puertos. Esto facilita que el sistema identifique y marque un paquete determinado: Si el puerto 49152 está reservado para tráfico de audio, todos los paquetes que viajan a través del puerto 49152 se pueden marcar con un código DSCP que indica que se trata de un paquete de audio. A su vez, permite que los enrutadores identifiquen el paquete como un paquete de audio y le dan mayor prioridad que los paquetes no marcados (como los paquetes que se usan para copiar un archivo de un servidor a otro).

Sin embargo, simplemente restringir un conjunto de puertos a un tipo específico de tráfico no da lugar a que los paquetes se marquen con el código DSCP adecuado. Además de definir intervalos de puertos, también debe crear directivas de calidad de servicio que especifiquen el código DSCP que se va a asociar con cada intervalo de puertos. Para Microsoft Lync Server 2013, que normalmente significa la creación de dos directivas: una para el audio y otra para el vídeo.

Las directivas de calidad de servicio se crean más fácilmente y se administran mediante una directiva de grupo. (Estas mismas directivas también se pueden crear con directivas de seguridad local. Sin embargo, eso requiere repetir el mismo procedimiento en todos los equipos.) El conjunto inicial de directivas de QoS (uno para el audio y otra para el vídeo) debe aplicarse solo a los equipos de Lync Server que ejecuten el servidor de conferencia, el servidor de aplicaciones o los servicios de Media Server. Si todos estos equipos se encuentran en la misma unidad organizativa de Active Directory, simplemente puede asignar el nuevo objeto de directiva de grupo (GPO) a esa unidad organizativa. Como alternativa, puede realizar otros pasos para dirigir la nueva Directiva a los equipos especificados; por ejemplo, puede colocar los equipos apropiados en un grupo de seguridad y, a continuación, usar el filtrado de seguridad de directiva de grupo para aplicar el GPO solo a ese grupo de seguridad.

Para crear una directiva de calidad de servicio para administrar el audio, inicie sesión en un equipo en el que se haya instalado administración de directivas de grupo. Abra administración de directivas de grupo (haga clic en **Inicio**, seleccione **herramientas administrativas**y, a continuación, haga clic en **Administración de directivas de grupo**) y realice el siguiente procedimiento:

1.  En administración de directivas de grupo, busque el contenedor en el que se debe crear la nueva Directiva. Por ejemplo, si todos los equipos de Lync Server se encuentran en una unidad organizativa denominada Lync Server, la nueva Directiva debe crearse en la OU de Lync Server.

2.  Haga clic con el botón secundario en el contenedor correspondiente y luego haga clic en **crear un GPO en este dominio y vincúlelo aquí**.

3.  En el cuadro de diálogo **nuevo GPO** , escriba un nombre para el nuevo objeto de directiva de grupo en el cuadro **nombre** (por ejemplo, **QoS de Lync Server**) y, a continuación, haga clic en **Aceptar**.

4.  Haga clic con el botón secundario en la Directiva recién creada y luego haga clic en **Editar**.

5.  En el editor de administración de directivas de grupo, expanda **configuración del equipo**, expanda **directivas**, expanda **configuración de Windows**, haga clic con el botón secundario en **QoS basada en directivas**y, a continuación, haga clic en **crear nueva Directiva**.

6.  En el cuadro de diálogo **QoS basado en directivas** , en la página de apertura, escriba un nombre para la nueva Directiva (por ejemplo, **Lync Server QoS**) en el cuadro **nombre** . Seleccione **especificar valor de DSCP** y establezca el valor en **46**. Deje la **tasa de límite saliente** desactivada y, a continuación, haga clic en **siguiente**.

7.  En la página siguiente, asegúrese de que **todas las aplicaciones** está seleccionada y, a continuación, haga clic en **siguiente**. Esto simplemente garantiza que todas las aplicaciones coincidirán con paquetes del intervalo de puertos especificado con el código DSCP especificado.

8.  En la tercera página, asegúrese de que **todas las direcciones IP de origen y cualquier dirección IP de destino** estén seleccionadas y, a continuación, haga clic en **siguiente**. Estas dos opciones de configuración garantizan que los paquetes se administrarán independientemente del equipo (dirección IP) que hayan enviado esos paquetes y qué equipo (dirección IP) recibirá esos paquetes.

9.  En la cuarta página, seleccione **TCP y UDP** en la lista desplegable **seleccionar el protocolo de esta directiva de QoS** . TCP (Protocolo de control de transmisión) y UDP (Protocolo de datagrama de usuario) son los dos protocolos de red más usados por Lync Server y sus aplicaciones cliente.

10. En el encabezado, **especifique el número de puerto de origen**, seleccione **de este rango o puerto de origen**. En el cuadro de texto que acompaña, escriba el intervalo de puertos reservado para las transtransmisións de audio. Por ejemplo, si ha reservado los puertos 49152 a través de los puertos 57500 para el tráfico de audio, escriba el intervalo de puertos con este formato: **49152:57500**. Haga clic en **Finalizar**.

<div>


> [!NOTE]  
> El valor de DSCP de 46 es algo arbitrario: aunque DSCP 46 se usa a menudo para marcar paquetes de audio, no es necesario usar DSCP 46 para las comunicaciones de audio. Si ya ha implementado QoS y está usando un código de DSCP diferente para el audio (por ejemplo, DSCP 40), debe configurar la Directiva de calidad de servicio para usar el mismo código (por ejemplo, 40 para audio). Si ahora está implementando la calidad de servicio, se recomienda que use DSCP 46 para el audio, simplemente porque ese valor suele usarse para marcar paquetes de audio.



</div>

Después de crear la directiva QoS para el tráfico de audio, debe crear una segunda Directiva para el tráfico de vídeo (y, opcionalmente, una tercera Directiva para administrar el tráfico de uso compartido de aplicaciones). Para crear una directiva para el vídeo, siga el mismo procedimiento básico que siguió al crear la Directiva de audio y realizar estas sustituciones:

  - Use un nombre de directiva diferente (y único) (por ejemplo, **vídeo de Lync Server**).

  - Establezca el valor de DSCP en **34** en lugar de 46. (Tenga en cuenta que no es necesario usar un valor de DSCP de 34. El único requisito es que use un valor de DSCP diferente para el vídeo que el que usó para el audio.

  - Use el intervalo de puertos configurado previamente para el tráfico de vídeo. Por ejemplo, si ha reservado los puertos 57501 a 65535 para el vídeo, establezca el intervalo de puertos en: **57501:65535**.

Si decide crear una directiva para administrar el tráfico de uso compartido de aplicaciones, debe crear una tercera Directiva y realizar las siguientes sustituciones:

  - Use un nombre de directiva diferente (y único) (por ejemplo, **compartir aplicaciones de Lync Server**).

  - Establezca el valor de DSCP en **24** en lugar de 46. (Nuevamente, no es necesario usar un valor de DSCP de 24. El único requisito es que use un valor de DSCP diferente para el uso compartido de aplicaciones que el que usó para el audio o el vídeo.

  - Use el intervalo de puertos configurado previamente para el tráfico de vídeo. Por ejemplo, si ha reservado los puertos 40803 a 49151 para el uso compartido de aplicaciones, establezca el intervalo de puertos en este: **40803:49151**.

Las nuevas directivas que ha creado no tendrán efecto hasta que se actualice la Directiva de grupo en los equipos de Lync Server. Aunque la directiva de grupo se actualiza periódicamente por sí misma, se puede forzar una actualización inmediata si se ejecuta el siguiente comando en cada equipo en el que se tenga que actualizar la directiva de grupo:

    Gpupdate.exe /force

Este comando se puede ejecutar desde el shell de administración de Lync Server o desde cualquier ventana de comandos que se ejecute con credenciales de administrador. Para abrir una ventana de comandos con las credenciales del administrador, haga clic en **Inicio**, haga clic con el botón derecho en **Símbolo del sistema** y, a continuación, haga clic en **Ejecutar como administrador**.

Para comprobar que se han aplicado las nuevas directivas de QoS, haga lo siguiente:

1.  En un equipo de Lync Server, haga clic en **Inicio** y, a continuación, en **Ejecutar**.

2.  En el cuadro de diálogo **Ejecutar** , **** escriba regedit y, a continuación, presione Entrar.

3.  En el editor del registro, expanda **equipo**, expanda **\_HKEY local\_Machine**, expanda **software**, expanda **directivas**, expanda **Microsoft**, expanda **Windows**y, a continuación, haga clic en **QoS**. En **QoS** , debe ver las claves del registro para cada una de las directivas de QoS que acaba de crear. Por ejemplo, si ha creado dos nuevas directivas (una con el nombre QoS de audio de Lync Server y la otra llamada de vídeo de Lync Server QoS), debe entradas del registro para QoS de audio de Lync Server y la calidad de video de Lync Server.

Para asegurarse de que los paquetes de red estén marcados con el valor de DSCP adecuado, también debe crear una nueva entrada de registro en cada equipo completando el procedimiento siguiente:

1.  Haga clic en **Inicio** y, después, en **Ejecutar**.

2.  En el cuadro de diálogo **Ejecutar** , **** escriba regedit y, a continuación, presione Entrar.

3.  En el editor del registro, expanda el **equipo local\_\_HKEY**, expanda **sistema**, expanda **CurrentControlSet**, expanda **Services**y, a continuación, expanda **TCPIP**.

4.  Haga clic con el botón derecho en **TCPIP**, seleccione **nuevo**y, a continuación, haga clic en **clave**. Después de crear la nueva clave del registro, escriba **QoS** y, a continuación, presione Entrar para cambiar el nombre de la clave.

5.  Haga clic con el botón derecho en **QoS**, seleccione **nuevo**y, a continuación, haga clic en **valor de cadena**. Después de crear el nuevo valor del registro, escriba **no use NLA** y, a continuación, presione Entrar para cambiar el nombre del valor.

6.  Haga doble clic en **no usar NLA**. En el cuadro de diálogo **Editar cadena** , escriba **1** en el cuadro **datos del valor** y, a continuación, haga clic en **Aceptar**.

7.  Cierre el editor del registro y, a continuación, reinicie el equipo.

</div>

<span> </span>

</div>

</div>

</div>

