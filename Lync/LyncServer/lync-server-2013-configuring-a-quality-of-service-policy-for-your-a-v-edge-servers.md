---
title: Configuración de una directiva de calidad de servicio para los servidores perimetrales A/V
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring a Quality of Service policy for your A/V Edge Servers
ms:assetid: 119ee1f5-45b9-40ba-98e5-c694dd2fc5c2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204681(v=OCS.15)
ms:contentKeyID: 48183444
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 58f5bfabfe794ed274d28074aaf162bc715a6ed3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842309"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-a-quality-of-service-policy-for-your-av-edge-servers-in-lync-server-2013"></a>Configurar una directiva de calidad de servicio para los servidores perimetrales A/V en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-19_

Además de crear directivas de QoS para los servidores de conferencias, aplicaciones y mediación, también debe crear directivas de audio y vídeo para el lado interno de los servidores perimetrales A/V. Sin embargo, las directivas que se usan en los servidores perimetrales son distintas de las que se usan en los servidores de conferencia, aplicación y mediación. Para los servidores de conferencia, aplicación y mediación que especificó un intervalo de puertos de origen; con los servidores perimetrales, debe especificar un intervalo de puertos de destino. Por eso no puede simplemente aplicar las directivas QoS del servidor de conferencia, aplicación y media a los servidores perimetrales: estas directivas simplemente no funcionan. En su lugar, debe crear directivas nuevas y aplicarlas solo a los servidores perimetrales.

El procedimiento siguiente describe el proceso de creación de objetos de directiva de grupo de Active Directory que se pueden usar para administrar la calidad de servicio en servidores perimetrales. Por supuesto, es posible que los servidores perimetrales sean servidores independientes que no tengan cuentas de Active Directory. Si ese es el caso, puede usar una directiva de grupo local en lugar de una directiva de grupo de Active Directory: la única diferencia es que debe crear estas directivas locales con el editor de directivas de grupo local y debe crear de forma individual el mismo conjunto de directivas en cada servidor perimetral. Para iniciar el editor de directivas de grupo local en un servidor perimetral, haga lo siguiente:

1.  Haga clic en **Inicio** y, después, en **Ejecutar**.

2.  En el cuadro de diálogo **Ejecutar** , escriba **gpedit. msc** y, a continuación, presione Entrar.

Si va a crear directivas basadas en Active Directory, debe iniciar sesión en un equipo en el que se haya instalado administración de directivas de grupo. En ese caso, abra Administración de directivas de grupo (haga clic en **Inicio**, seleccione **herramientas administrativas**y, a continuación, haga clic en **Administración de directivas de grupo**) y siga los pasos siguientes:

1.  En administración de directivas de grupo, busque el contenedor en el que se debe crear la nueva Directiva. Por ejemplo, si todos los equipos de Lync Server se encuentran en una unidad organizativa denominada Lync Server, la nueva Directiva debe crearse en la OU de Lync Server.

2.  Haga clic con el botón secundario en el contenedor correspondiente y luego haga clic en **crear un GPO en este dominio y vincúlelo aquí**.

3.  En el cuadro de diálogo **nuevo GPO** , escriba un nombre para el nuevo objeto de directiva de grupo en el cuadro **nombre** (por ejemplo, **audio de Lync Server**) y, a continuación, haga clic en **Aceptar**.

4.  Haga clic con el botón secundario en la Directiva recién creada y luego haga clic en **Editar**.

Desde aquí el proceso es idéntico independientemente de si está creando una directiva de Active Directory o una directiva local:

1.  En el editor de administración de directivas de grupo o el editor de directivas de grupo local, expanda **configuración del equipo**, **directivas**, **configuración de Windows**, haga clic con el botón secundario en **QoS basada en directivas**y, a continuación, haga clic en **crear nueva Directiva**.

2.  En el cuadro de diálogo **QoS basado en directivas** , en la página de apertura, escriba un nombre para la nueva Directiva (por ejemplo, **audio de Lync Server**) en el cuadro **nombre** . Seleccione **especificar valor de DSCP** y establezca el valor en **46**. Deje la **tasa de límite saliente** desactivada y, a continuación, haga clic en **siguiente**.

3.  En la página siguiente, asegúrese de que **todas las aplicaciones** está seleccionada y, a continuación, haga clic en **siguiente**. Esta configuración instruye a la red para que busque todos los paquetes con un marcado de DSCP de 46, no solo los paquetes creados por una aplicación específica.

4.  En la tercera página, asegúrese de que **todas las direcciones IP de origen** y **cualquier dirección IP de destino** estén seleccionadas y, a continuación, haga clic en **siguiente**. Estas dos opciones de configuración garantizan que los paquetes se administrarán independientemente del equipo (dirección IP) que hayan enviado esos paquetes y qué equipo (dirección IP) recibirá esos paquetes.

5.  En la cuarta página, seleccione **TCP y UDP** en la lista desplegable **seleccionar el protocolo de esta directiva de QoS** . TCP (Protocolo de control de transmisión) y UDP (Protocolo de datagrama de usuario) son los dos protocolos de red más usados por Lync Server y sus aplicaciones cliente.

6.  En el encabezado, **especifique el número de puerto de destino**, seleccione **desde este intervalo o puerto de destino**. En el cuadro de texto que acompaña, escriba el intervalo de puertos reservado para las transtransmisións de audio. Por ejemplo, si ha reservado los puertos 49152 a través de los puertos 57500 para el tráfico de audio, escriba el intervalo de puertos con este formato: **49152:57500**. Haga clic en **Finalizar**.

Una vez que haya creado la directiva QoS para el tráfico de audio, debe crear una segunda Directiva para el tráfico de vídeo. Para crear una directiva para el vídeo, siga el mismo procedimiento básico que siguió al crear la Directiva de audio y realizar estas sustituciones:

  - Use un nombre de directiva diferente (y único) (por ejemplo, **vídeo de Lync Server**).

  - Establezca el valor de DSCP en **34** en lugar de 46. (Tenga en cuenta que no es necesario usar un valor de DSCP de 34. El único requisito es que use un valor de DSCP diferente para el vídeo que el que usó para el audio.

  - Use el intervalo de puertos configurado previamente para el tráfico de vídeo. Por ejemplo, si ha reservado los puertos 57501 a 65535 para el vídeo, establezca el intervalo de puertos en: **57501:65535**. De nuevo, debe estar configurado como el intervalo de puertos de destino.

Si decide crear una directiva para administrar el tráfico de uso compartido de aplicaciones, debe crear una tercera Directiva y realizar las siguientes sustituciones:

  - Use un nombre de directiva diferente (y único) (por ejemplo, **compartir aplicaciones de Lync Server**).

  - Establezca el valor de DSCP en **24** en lugar de 46. (Nuevamente, no es necesario usar un valor de DSCP de 24. El único requisito es que use un valor de DSCP diferente para el uso compartido de aplicaciones que el que usó para el audio o el vídeo.

  - Use el intervalo de puertos configurado previamente para el tráfico de vídeo. Por ejemplo, si ha reservado los puertos 40803 a 49151 para el uso compartido de aplicaciones, establezca el intervalo de puertos en este: **40803:49151**.

Las nuevas directivas que ha creado no tendrán efecto hasta que se actualice la Directiva de grupo en los servidores perimetrales. Aunque la directiva de grupo se actualiza periódicamente por sí misma, se puede forzar una actualización inmediata si se ejecuta el siguiente comando en cada equipo en el que se tenga que actualizar la directiva de grupo:

    Gpudate.exe /force

Este comando se puede ejecutar desde el servidor de Lync o desde cualquier ventana de comandos que se ejecute con credenciales de administrador. Para abrir una ventana de comandos con las credenciales del administrador, haga clic en **Inicio**, haga clic con el botón derecho en **Símbolo del sistema** y, a continuación, haga clic en **Ejecutar como administrador**. Tenga en cuenta que es posible que tenga que reiniciar el servidor perimetral incluso después de ejecutar Gpudate. exe.

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

