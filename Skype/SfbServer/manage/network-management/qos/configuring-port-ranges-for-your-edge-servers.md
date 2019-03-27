---
title: Configuración de intervalos de puertos y una calidad de servicio para los servidores perimetrales
ms.reviewer: ''
ms:assetid: 6f0ae442-6624-4e3f-849a-5b9e387fb8cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204996(v=OCS.15)
ms:contentKeyID: 48184469
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: En este artículo se describe cómo configurar intervalos de puertos para los servidores perimetrales y cómo configurar una directiva de calidad de servicio para el o los servidores perimetrales A/v.
ms.openlocfilehash: 11fdb542c6256c21e169480194bc5154bf1c1428
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30886377"
---
# <a name="configuring-port-ranges-and-a-quality-of-service-policy-for-your-edge-servers-in-skype-for-business-server"></a>Configuración de intervalos de puertos y una directiva de calidad de servicio para los servidores perimetrales en Skype para Business Server

En este artículo se describe cómo configurar intervalos de puertos para los servidores perimetrales y cómo configurar una directiva de calidad de servicio para el o los servidores perimetrales A/v.

## <a name="configure-port-ranges"></a>Configurar intervalos de puertos

Con los servidores perimetrales, no es necesario configurar los intervalos de puerto independiente de audio, vídeo y uso compartido de aplicaciones; del mismo modo, los intervalos de puertos utilizados para los servidores perimetrales no es necesario para que coincida con los intervalos de puertos se utiliza con los servidores de mediación, conferencia y aplicaciones. Antes de continuar con nuestro ejemplo, es importante destacar que mientras existe esta opción, se recomienda no cambiar los intervalos de puertos, como esto puede afectar negativamente a algunos escenarios de mover fuera del intervalo de 50000 puerto.

Por ejemplo, suponga que ha configurado los servidores de mediación, conferencia y aplicaciones para usar estos intervalos de puertos:


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Tipo de paquete</th>
<th>Puerto inicial</th>
<th>Número de puertos reservados</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Uso compartido de aplicaciones</p></td>
<td><p>40803</p></td>
<td><p>8348</p></td>
</tr>
<tr class="even">
<td><p>Audio</p></td>
<td><p>49152</p></td>
<td><p>8348</p></td>
</tr>
<tr class="odd">
<td><p>Vídeo</p></td>
<td><p>57500</p></td>
<td><p>8034</p></td>
</tr>
<tr class="even">
<td><p><strong>Totales</strong></p></td>
<td><p>--</p></td>
<td><p>24730</p></td>
</tr>
</tbody>
</table>


Como puede ver, los intervalos de puertos de audio, vídeo y uso compartido de inicio en el puerto 40803 de aplicaciones y abarcar un total de 24732 puertos. Si lo prefiere, puede configurar un servidor perimetral determinado para utilizar estos valores de puerto general mediante la ejecución de un comando similar a este desde dentro de la Skype para Shell de administración de servidor empresarial:

    Set-CsEdgeServer -Identity EdgeServer:atl-edge-001.litwareinc.com -MediaCommunicationPortStart 40803 -MediaCommunicationPortCount 24730

O bien, use el siguiente comando para configurar simultáneamente todos los servidores perimetrales de la organización:

    Get-CsService -EdgeServer | ForEach-Object {Set-CsEdgeServer -Identity $_.Identity -MediaCommunicationPortStart 40803 -MediaCommunicationPortCount 24730}

Puede comprobar la configuración de puerto actual para los servidores perimetrales mediante el uso de este Skype para el comando de Shell de administración de servidor empresarial:

    Get-CsService -EdgeServer | Select-Object Identity, MediaCommunicationPortStart, MediaCommunicationPortCount

Una vez más, mientras que podamos proporcionar estas opciones, se recomienda encarecidamente que dejar las cosas que se utilizan para la configuración del puerto.

## <a name="configure-a-qos-policy-for-your-av-edge-servers"></a>Configurar una directiva de QoS para el o los servidores perimetrales A/v

Además de crear las directivas de QoS para los servidores de conferencia, aplicación y mediación, también debe crear las directivas de audioconferencias y vídeo para el lado interno de su A / servidores perimetrales A/v. Sin embargo, las directivas que se usa en los servidores perimetrales son diferentes de las directivas que se usa en los servidores de mediación, conferencia y aplicaciones. Para los servidores de conferencia, aplicación y mediación, ha especificado un intervalo de puerto de origen; con los servidores perimetrales, debe especificar un intervalo de puerto de destino. Por este motivo, simplemente no se puede aplicar las directivas de QoS de servidor de mediación, conferencia y aplicaciones a los servidores perimetrales: estas directivas simplemente no funcionarán. En su lugar, debe crear nuevas directivas y aplicar estas directivas a los servidores perimetrales sólo.

El siguiente procedimiento describe el proceso de creación de objetos de directiva de grupo de Active Directory que se pueden usar para administrar la calidad de servicio en los servidores perimetrales. Por supuesto, es posible que los servidores perimetrales son servidores independientes que no tienen cuentas de Active Directory. Si ese es el caso, puede usar la directiva de grupo local en lugar de directiva de grupo de Active Directory: la única diferencia es que se deben crear estas directivas locales mediante el Editor de directivas de grupo Local y debe crear individualmente el mismo conjunto de directivas en cada servidor perimetral. Para iniciar el Editor de directivas de grupo Local en un servidor perimetral, haga lo siguiente:

1.  Haga clic en  **Inicio ** y en  **Ejecutar **.

2.  En el cuadro de diálogo **Ejecutar** , escriba **gpedit.msc**y, a continuación, presione ENTRAR.

Si va a crear directivas basadas en Active Directory, debe iniciar sesión en un equipo donde se ha instalado Administración de directivas de grupo. En ese caso, abra Administración de directivas de grupo (haga clic en **Inicio**, elija **Herramientas administrativas**y, a continuación, haga clic en **Administración de directivas de grupo**) y, a continuación, complete los siguientes pasos:

1.  En administración de directivas de grupo, busque el contenedor donde se debe crear la nueva directiva. Por ejemplo, si todos los su Skype para equipos Business Server se encuentra en una unidad organizativa denominada Skype para Business Server, se debe crear la nueva directiva en el Skype para la unidad organizativa de servidor empresarial.

2.  Haga clic en el contenedor adecuado y, a continuación, haga clic en **crear un GPO en este dominio y vincularlo aquí**.

3.  En el cuadro de diálogo **Nuevo GPO** , escriba un nombre para el nuevo objeto de directiva de grupo en el cuadro **nombre** (por ejemplo, **Skype para Audio del servidor empresarial**) y, a continuación, haga clic en **Aceptar**.

4.  Haga clic en la directiva recién creada y, a continuación, haga clic en **Editar**.

Desde aquí el proceso es idéntico independientemente de si está creando una directiva de Active Directory o una directiva local:

1.  En el Editor de administración de directiva de grupo o el Editor de directivas de grupo Local, expanda **Configuración del equipo**, expanda **directivas**, expanda **Configuración de Windows**, haga clic en **QoS basada en directiva de**y, a continuación, haga clic en **Crear nueva directiva**.

2.  En el cuadro de diálogo de **QoS basada en directiva** , en la página de apertura, escriba un nombre para la nueva directiva (por ejemplo, **Skype para Audio del servidor empresarial**) en el cuadro **nombre** . Seleccione **Especificar el valor de DSCP** y establezca el valor **46**. Deje **Especificar velocidad de aceleración saliente** no está seleccionada y, a continuación, haga clic en **siguiente**.

3.  En la página siguiente, asegúrese de que **todas las aplicaciones** está activada y, a continuación, haga clic en **siguiente**. Esta opción indica a la red para buscar todos los paquetes con un marcado DSCP 46, no sólo de paquetes de creados mediante una aplicación específica.

4.  En la tercera página, asegúrese de que **cualquier dirección IP de origen** y **cualquier dirección IP de destino** están seleccionados y, a continuación, haga clic en **siguiente**. Estos dos valores Asegúrese de que se administrarán los paquetes independientemente de qué equipo (dirección IP) enviado esos paquetes y qué equipo (dirección IP) recibirán los paquetes.

5.  En la cuarta página, seleccione **TCP y UDP** en la lista desplegable **Seleccione el protocolo que se aplica esta directiva de QoS** . TCP (Protocolo de Control de transmisión) y UDP (Protocolo de datagramas de usuario) son los dos protocolos de red más utilizados por Skype para Business Server y sus aplicaciones de cliente.

6.  Bajo el encabezado, **Especifique el número de puerto de destino**, seleccione **desde este intervalo o el puerto de destino**. En el cuadro de texto que lo acompaña, escriba el intervalo de puertos reservado para las transmisiones de audioconferencias. Por ejemplo, si ha reservado puertos 49152 a través de puertos 57500 para el tráfico de audio, escriba el intervalo de puertos con este formato: **49152:57500**. Haga clic en **Finalizar**.

Después de haber creado la directiva de QoS para el tráfico de audio, debe crear una segunda directiva para el tráfico de vídeo. Para crear una directiva para el vídeo, siga el mismo procedimiento básico seguido al crear la directiva de audio, realizar las siguientes sustituciones:

  - Use un nombre de directiva diferente (y único) (por ejemplo, **Skype para vídeo de servidor empresarial**).

  - Establezca el valor DSCP a **34** en lugar de 46. (Tenga en cuenta que no es necesario usar un valor DSCP de 34. El único requisito es usar un valor DSCP diferente para el vídeo que se utiliza para el audio.)

  - Usar el intervalo de puerto configurado anteriormente para el tráfico de vídeo. Por ejemplo, si lo ha reservado puertos 57501 y 65535 para vídeo, establezca el intervalo de puertos a la siguiente: **57501:65535**. Una vez más, esto debe configurarse como el intervalo de puertos de destino.

Si decide crear una directiva para administrar el tráfico de uso compartido de aplicaciones, debe crear una tercera Directiva, sustituyendo lo siguiente:

  - Use un nombre de directiva diferente (y único) (por ejemplo, **Skype para compartir aplicaciones de servidor de negocio**).

  - Establezca el valor de DSCP en **24** en lugar de 46. (De nuevo, no es necesario usar un valor DSCP de 24. El único requisito es que usar un valor DSCP diferente para uso compartido de aplicaciones que usa para el audio o de vídeo.)

  - Usar el intervalo de puerto configurado anteriormente para el tráfico de vídeo. Por ejemplo, si lo ha reservado puertos 40803 y 49151 para uso compartido de aplicaciones, puede establecer el intervalo de puertos a la siguiente: **40803:49151**.

Las nuevas directivas que ha creado no tendrán efecto hasta que se ha actualizado la directiva de grupo en los servidores perimetrales. Aunque la directiva de grupo se actualiza periódicamente por sí misma, se puede forzar una actualización inmediata si se ejecuta el siguiente comando en cada equipo en el que se tenga que actualizar la directiva de grupo:

    Gpudate.exe /force

Este comando se puede ejecutar desde dentro de la Skype para Business Server o desde cualquier ventana de comandos que se ejecuta con credenciales de administrador. Para abrir una ventana de comandos con las credenciales del administrador, haga clic en **Inicio**, haga clic con el botón derecho en **Símbolo del sistema** y, a continuación, haga clic en **Ejecutar como administrador**. Tenga en cuenta que es posible que necesite reiniciar el servidor perimetral incluso después de ejecutar Gpudate.exe.

Para ayudar a garantizar que los paquetes de red están marcados con el valor DSCP adecuado, también debe crear una nueva entrada del registro en cada equipo completando el procedimiento siguiente:

1.  Haga clic en  **Inicio ** y en  **Ejecutar **.

2.  En el cuadro de diálogo **Ejecutar** , escriba **regedit**y, a continuación, presione ENTRAR.

3.  En el Editor del registro, expanda **HKEY\_LOCAL\_máquina**, expanda **SYSTEM**, expanda **CurrentControlSet**, expanda **Servicios**y, a continuación, expanda **Tcpip**.

4.  Secundario **Tcpip**, elija **nuevo**y, a continuación, haga clic en **clave**. Una vez creada la nueva clave del registro, escriba **QoS**y, a continuación, presione ENTRAR para cambiar el nombre de la clave.

5.  Secundario **QoS**, elija **nuevo**y, a continuación, haga clic en **Valor de tipo String**. Una vez creado el nuevo valor del registro, escriba **no use NLA**y, a continuación, presione ENTRAR para cambiar el nombre del valor.

6.  Haga doble clic en **no utilizan NLA**. En el cuadro de diálogo **Editar cadena** , escriba **1** en el cuadro **datos de valor** y, a continuación, haga clic en **Aceptar**.

7.  Cierre el Editor del registro y reinicie el equipo.
