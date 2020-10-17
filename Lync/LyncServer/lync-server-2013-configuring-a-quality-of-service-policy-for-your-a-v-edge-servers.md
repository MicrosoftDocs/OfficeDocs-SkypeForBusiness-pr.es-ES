---
title: Configuración de una directiva de calidad de servicio para los servidores perimetrales A/V
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring a Quality of Service policy for your A/V Edge Servers
ms:assetid: 119ee1f5-45b9-40ba-98e5-c694dd2fc5c2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204681(v=OCS.15)
ms:contentKeyID: 48183444
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 69b9beb119ebd7189c31f9e239ac45409758ba00
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48515697"
---
# <a name="configuring-a-quality-of-service-policy-for-your-av-edge-servers-in-lync-server-2013"></a>Configurar una directiva de calidad de servicio para los servidores perimetrales A/V en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-19_

Además de crear directivas de QoS para los servidores de conferencia, aplicación y mediación, también debe crear directivas de audio y vídeo para el lado interno de sus servidores perimetrales A/V. Sin embargo, las directivas usadas en los servidores perimetrales son diferentes de las que se usan en los servidores de conferencia, aplicación y mediación. Para los servidores de conferencia, aplicación y mediación especifica un intervalo de puertos de origen; con los servidores perimetrales, debe especificar un intervalo de puertos de destino. Debido a que no puede simplemente aplicar las directivas QoS del servidor de conferencia, aplicación y mediación a los servidores perimetrales: estas directivas simplemente no funcionan. En su lugar, debe crear nuevas directivas y aplicar dichas directivas solo a los servidores perimetrales.

El siguiente procedimiento describe el proceso para crear objetos de directiva de grupo de Active Directory que se pueden usar para administrar la calidad de servicio en los servidores perimetrales. Por supuesto, es posible que los servidores perimetrales sean servidores independientes que no tengan cuentas de Active Directory. Si ese es el caso, puede usar la Directiva de grupo local en lugar de la Directiva de grupo de Active Directory: la única diferencia es que debe crear estas directivas locales con el editor de directivas de grupo local y debe crear de forma individual el mismo conjunto de directivas en cada servidor perimetral. Para iniciar el editor de directivas de grupo local en un servidor perimetral, haga lo siguiente:

1.  Haga clic en **Inicio** y, a continuación, haga clic en **Ejecutar**.

2.  En el cuadro de diálogo **Ejecutar** , escriba **gpedit. msc** y, a continuación, presione Entrar.

Si va a crear directivas basadas en Active Directory, debe iniciar sesión en un equipo en el que se haya instalado administración de directivas de grupo. En ese caso, abra Administración de directivas de grupo (haga clic en **Inicio**, elija **herramientas administrativas**y, a continuación, haga clic en **Administración de directivas de grupo**) y, a continuación, complete los siguientes pasos:

1.  En Administración de directivas de grupo, busque el contenedor donde se deba crear la nueva directiva. Por ejemplo, si todos los equipos de Lync Server están ubicados en una unidad organizativa llamada Lync Server, la nueva Directiva debe crearse en la unidad organizativa Lync Server.

2.  Haga clic con el botón secundario en el contenedor que corresponda y, después, haga clic en **Crear un GPO en este dominio y vincularlo aquí**.

3.  En el cuadro de diálogo **Nuevo GPO**, escriba un nombre para el nuevo objeto de directiva de grupo en el cuadro **Nombre** (por ejemplo, **Audio Lync Server**) y haga clic en **Aceptar**.

4.  Haga clic con el botón secundario en la directiva recién creada y, a continuación, haga clic en **Editar**.

Desde aquí, el proceso es idéntico independientemente de si está creando una directiva de Active Directory o una directiva local:

1.  En el editor de administración de directivas de grupo o el editor de directivas de grupo local, expanda **configuración del equipo**, **directivas**, **configuración de Windows**, haga clic con el botón secundario en **QoS basada en Directiva**y, a continuación, haga clic en **crear nueva Directiva**.

2.  En el cuadro de diálogo **QoS basada en directivas**, en la página que se abre, escriba un nombre para la nueva directiva (p. ej., **Audio Lync Server**) en el cuadro **Nombre**. Seleccione **Especificar el valor de DSCP** y establezca el valor **46**. Deje desactivada la casilla **Especificar velocidad de salida del acelerador** y haga clic en **Siguiente**.

3.  En la página siguiente, compruebe que la opción **Todas las aplicaciones** está seleccionada y haga clic en **Siguiente**. Esta configuración indica a la red que busque todos los paquetes con el valor 46 para DSCP, y no solo los paquetes creados por una aplicación en particular.

4.  En la tercera página, compruebe que las opciones **Cualquier dirección IP de origen** y **Cualquier dirección IP de destino** están seleccionadas y haga clic en **Siguiente**. Estas dos opciones garantizan que se gestionarán todos los paquetes, sin tener en cuenta el equipo (o dirección IP) que los envió y el equipo (o dirección IP) que los recibirá.

5.  En la página cuatro, seleccione **TCP y UDP** en la lista desplegable **Seleccione el protocolo para el que se aplica esta directiva de QoS**. TCP (Protocolo de control de transmisión) y UDP (Protocolo de datagramas de usuario) son los dos protocolos de red más usados por Lync Server y sus aplicaciones cliente.

6.  En el encabezado **especifique el número de puerto de destino**, seleccione **desde este intervalo o puerto de destino**. En el cuadro de texto que acompaña a esta opción, escriba el intervalo de puertos reservado a las transmisiones de audio. Por ejemplo, si ha reservado los puertos 49152 a través de los puertos 57500 para el tráfico de audio, escriba el intervalo de puertos con este formato: **49152:57500**. Haga clic en **Finalizar**.

Una vez que haya creado la directiva QoS para el tráfico de audio, debe crear una segunda Directiva para el tráfico de vídeo. Para crear una directiva destinada al vídeo, siga el mismo procedimiento básico que llevó a cabo al crear la directiva de audio, sustituyendo lo siguiente:

  - Utilice un nombre de directiva diferente (y único) (por ejemplo, **Vídeo Lync Server**).

  - Establezca el valor de DSCP **34** en lugar de 46. (Tenga en cuenta que no es necesario usar el valor de DSCP 34. El único requisito es usar un valor de DSCP distinto para el vídeo del que se usó para el audio.)

  - Utilice el intervalo de puertos configurado previamente para el tráfico de vídeo. Por ejemplo, si ha reservado los puertos del 57501 al 65535 para el vídeo, establezca el intervalo de puertos así: **57501:65535**. De nuevo, debe configurarse como el intervalo de puertos de destino.

Si decide crear una directiva para administrar el tráfico de uso compartido de aplicaciones, debe crear una tercera directiva, sustituyendo lo siguiente:

  - Utilice un nombre de directiva diferente (y único) (por ejemplo, **Uso compartido de aplicaciones Lync Server**).

  - Establezca el valor de DSCP **24** en lugar de 46. (De nuevo, tenga en cuenta que no es necesario usar el valor de DSCP 24. El único requisito es usar un valor de DSCP distinto para el uso compartido de aplicaciones de los que se usaron para el audio y el vídeo.)

  - Utilice el intervalo de puertos configurado previamente para el tráfico de vídeo. Por ejemplo, si ha reservado los puertos del 40803 al 49151 para el uso compartido de aplicaciones, establezca el intervalo de puertos así: **40803:49151**.

Las nuevas directivas que ha creado no tendrán efecto hasta que la Directiva de grupo se haya actualizado en los servidores perimetrales. Aunque la directiva de grupo se actualiza periódicamente por sí misma, puede forzar una actualización inmediata ejecutando el siguiente comando en cada equipo donde sea necesario actualizar la directiva de grupo:

    Gpudate.exe /force

Este comando se puede ejecutar desde dentro de Lync Server o desde cualquier ventana de comandos que se ejecute con credenciales de administrador. Para ejecutar una ventana de comandos con credenciales de administrador, haga clic en **Inicio**, haga clic con el botón secundario en **Símbolo del sistema** y, a continuación, haga clic en **Ejecutar como administrador**. Tenga en cuenta que es posible que tenga que reiniciar el servidor perimetral incluso después de ejecutar Gpudate.exe.

Para asegurarse de que los paquetes de red se marquen con el valor de DSCP adecuado, debe crear también una nueva entrada del Registro en cada equipo, mediante el siguiente procedimiento:

1.  Haga clic en **Inicio** y, a continuación, en **Ejecutar**.

2.  En el cuadro de diálogo **Ejecutar**, escriba **regedit** y, a continuación, presione ENTRAR.

3.  En el editor del registro, expanda el ** \_ \_ equipo local HKEY**, expanda **sistema**, expanda **CurrentControlSet**, expanda **servicios**y, a continuación, expanda **TCPIP**.

4.  Haga clic con el botón secundario en **Tcpip**, elija **Nuevo** y, a continuación, haga clic en **Clave**. Después de que se cree una nueva clave del Registro, escriba **QoS** y presione ENTRAR para cambiar el nombre de la clave.

5.  Haga clic con el botón secundario en **QoS**, elija **Nuevo** y, a continuación, haga clic en **Valor de cadena**. Después de que se cree un nuevo valor del Registro, escriba **No usar NLA** y presione ENTRAR para cambiar el nombre del valor.

6.  Haga clic con el botón secundario en **No usar NLA**. En el cuadro de diálogo **Editar cadena**, escriba **1** en el cuadro **Información del valor** y, a continuación, haga clic en **Aceptar**.

7.  Cierre el Editor del Registro y reinicie el equipo.

</div>

<span> </span>

</div>

</div>

</div>

