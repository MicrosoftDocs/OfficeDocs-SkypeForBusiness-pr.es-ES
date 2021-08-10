---
title: Configuración de intervalos de puertos y calidad de servicio para los servidores perimetrales
ms.reviewer: ''
ms:assetid: 6f0ae442-6624-4e3f-849a-5b9e387fb8cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204996(v=OCS.15)
ms:contentKeyID: 48184469
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
description: En este artículo se describe cómo configurar intervalos de puertos para servidores perimetrales y cómo configurar una directiva de calidad de servicio para los servidores perimetrales A/V.
ms.openlocfilehash: f21a5612889e0368a93bc8a55e5f023a28b226a9aa8843275faa696675b94d7e
ms.sourcegitcommit: 0e9516c51105e4d89c550d2ea2bd8e7649a1163b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/06/2021
ms.locfileid: "54591134"
---
# <a name="configuring-port-ranges-and-a-quality-of-service-policy-for-your-edge-servers-in-skype-for-business-server"></a>Configuración de intervalos de puertos y una directiva de calidad de servicio para los servidores perimetrales en Skype Empresarial Server

En este artículo se describe cómo configurar intervalos de puertos para servidores perimetrales y cómo configurar una directiva de calidad de servicio para los servidores perimetrales A/V.

## <a name="configure-port-ranges"></a>Configurar intervalos de puertos

Con los servidores perimetrales, no es necesario configurar intervalos de puertos independientes para el uso compartido de audio, vídeo y aplicaciones; Del mismo modo, los intervalos de puertos usados para los servidores perimetrales no tienen que coincidir con los intervalos de puertos usados con los servidores de conferencia, aplicación y mediación. Antes de continuar con nuestro ejemplo, es importante destacar que, aunque existe esta opción, se recomienda no cambiar los intervalos de puertos, ya que esto puede afectar negativamente a algunos escenarios si se sale del intervalo de puertos de 50000.

Por ejemplo, supongamos que ha configurado los servidores de conferencia, aplicación y mediación para usar estos intervalos de puertos:


<table>
<colgroup>
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


Como puede ver, los intervalos de puertos para el uso compartido de aplicaciones, vídeo y audio comienzan en el puerto 40803 y abarcan un total de 24732 puertos. Si lo prefiere, puede configurar un servidor perimetral determinado para que use estos valores de puerto generales ejecutando un comando similar a este desde el Shell de administración de Skype Empresarial Server:

  **Set-CsEdgeServer -Identity EdgeServer:atl-edge-001.litwareinc.com -MediaCommunicationPortStart 40803 -MediaCommunicationPortCount 24730**

También puede usar el comando siguiente para configurar simultáneamente todos los servidores perimetrales de su organización:

  **Get-CsService -EdgeServer | ForEach-Object {Set-CsEdgeServer -Identity $_. Identity -MediaCommunicationPortStart 40803 -MediaCommunicationPortCount 24730}**

Puede comprobar la configuración de puerto actual de los servidores perimetrales mediante este comando Skype Empresarial Server Shell de administración:

  **Get-CsService -EdgeServer | Select-Object Identity, MediaCommunicationPortStart, MediaCommunicationPortCount**

De nuevo, aunque proporcionamos estas opciones, se recomienda encarecidamente que deje las cosas tal como están para la configuración del puerto.

## <a name="configure-a-qos-policy-for-your-av-edge-servers"></a>Configurar una directiva de QoS para los servidores perimetrales A/V

Además de crear directivas de QoS para los servidores de conferencia, aplicación y mediación, también debe crear directivas de audio y vídeo para el lado interno de los servidores perimetrales A/V. Sin embargo, las directivas usadas en los servidores perimetrales son diferentes de las directivas usadas en los servidores de conferencia, aplicación y mediación. Para los servidores de conferencia, aplicación y mediación, especificó un intervalo de puertos de origen; con los servidores perimetrales, debe especificar un intervalo de puertos de destino. Debido a esto, simplemente no puede aplicar las directivas qoS del servidor de conferencia, aplicación y mediación a los servidores perimetrales: estas directivas simplemente no funcionarán. En su lugar, debe crear nuevas directivas y aplicar esas directivas solo a los servidores perimetrales.

El siguiente procedimiento describe el proceso para crear objetos de directiva de grupo de Active Directory que se pueden usar para administrar la calidad del servicio en servidores perimetrales. Por supuesto, es posible que los servidores perimetrales sean servidores independientes que no tengan cuentas de Active Directory. Si ese es el caso, puede usar la directiva de grupo local en lugar de la directiva de grupo de Active Directory: la única diferencia es que debe crear estas directivas locales mediante el Editor de directivas de grupo local y debe crear individualmente el mismo conjunto de directivas en cada servidor perimetral. Para iniciar el Editor de directivas de grupo local en un servidor perimetral, haga lo siguiente:

1.  Haga clic en **Inicio** y luego en **Ejecutar**.

2.  En el **cuadro de** diálogo Ejecutar, escriba **gpedit.msc** y, a continuación, presione ENTRAR.

Si va a crear directivas basadas en Active Directory, debe iniciar sesión en un equipo donde se haya instalado la administración de directivas de grupo. En ese caso, abra Administración de directivas de grupo (haga clic en Inicio **,** elija Herramientas administrativas y, a continuación, haga clic en **Administración** de directivas de grupo) y, a continuación, siga estos pasos:

1.  En Administración de directivas de grupo, busque el contenedor donde se deba crear la nueva directiva. Por ejemplo, si todos los Skype Empresarial Server están ubicados en una unidad organizativa denominada Skype Empresarial Server, la nueva directiva debe crearse en la unidad organizativa Skype Empresarial Server usuario.

2.  Haga clic con el botón secundario en el contenedor adecuado y, a continuación, haga clic en Crear un GPO en este **dominio y vincule aquí**.

3.  En el cuadro de diálogo Nuevo **GPO,** escriba un  nombre para el nuevo objeto de directiva de grupo en el cuadro Nombre (por ejemplo, **Skype Empresarial Server Audio)** y, a continuación, haga clic en **Aceptar**.

4.  Haga clic con el botón secundario en la directiva recién creada y, a continuación, haga clic **en Editar**.

Desde aquí, el proceso es idéntico independientemente de si está creando una directiva de Active Directory o una directiva local:

1.  En el Editor de administración de directivas de grupo o en el Editor de directivas de grupo local, expanda Configuración del equipo **,** expanda Directivas **,** expanda **Windows Configuración**, haga clic con el botón secundario en **QoS** basada en directivas y, a continuación, haga clic en Crear **nueva directiva.**

2.  En el **cuadro de diálogo QoS** basado en directivas, en la página de apertura, escriba un nombre para la nueva directiva (por ejemplo, **Skype Empresarial Server Audio)** en el cuadro **Nombre.** Seleccione **Especificar el valor de DSCP** y, a continuación, defina el valor en **46**. Deje sin seleccionar **Especificar velocidad de salida del acelerador** y, a continuación, haga clic en **Siguiente**.

3.  En la página siguiente, asegúrese de que **todas las aplicaciones** están seleccionadas y, a continuación, haga clic en **Siguiente**. Esta configuración indica a la red que busque todos los paquetes con el valor 46 para DSCP, y no solo los paquetes creados por una aplicación en particular.

4.  En la tercera página, asegúrese de que todas las direcciones **IP** de origen y cualquier dirección **IP** de destino están seleccionadas y, a continuación, haga clic **en Siguiente**. Con estas dos opciones de configuración activadas, los paquetes se administrarán sin importar qué equipo (dirección IP) los envió ni qué equipo (dirección IP) los recibirá.

5.  En la página cuatro, seleccione **TCP y UDP** en la lista desplegable **Seleccione el protocolo para el que se aplica esta directiva de QoS**. TCP (Transmission Control Protocol) y UDP (User Datagram Protocol) son los dos protocolos de red más usados por Skype Empresarial Server y sus aplicaciones cliente.

6.  Bajo el encabezado **Especifique el número de puerto de destino**, seleccione Desde este puerto o intervalo de **destino**. En el cuadro de texto que acompaña a esta opción, escriba el intervalo de puertos reservado a las transmisiones de audio. Por ejemplo, si reservó los puertos 49152 a través de los puertos 57500 para el tráfico de audio, escriba el intervalo de puertos con este formato: **49152:57500**. Haga clic en **Finalizar**.

Después de crear la directiva QoS para el tráfico de audio, debe crear una segunda directiva para el tráfico de vídeo. Para crear una directiva destinada al vídeo, siga el mismo procedimiento básico que llevó a cabo al crear la directiva de audio, sustituyendo lo siguiente:

  - Use un nombre de directiva diferente (y único) (por ejemplo, **Skype Empresarial Server Video**).

  - Establezca el valor de DSCP **34** en lugar de 46. (Tenga en cuenta que no es necesario usar el valor de DSCP 34. El único requisito es usar un valor de DSCP distinto para el vídeo del que se usó para el audio.)

  - Use el intervalo de puertos configurado anteriormente para el tráfico de vídeo. Por ejemplo, si tiene reservados los puertos 57501 a 65535 para vídeo, establezca el intervalo de puertos en: **57501:65535**. De nuevo, esto debe configurarse como el intervalo de puertos de destino.

Si decide crear una directiva para administrar el tráfico compartido de aplicaciones, debe crear una tercera directiva, realizando las siguientes sustituciones:

  - Use un nombre de directiva diferente (y único) (por ejemplo, **Skype Empresarial Server uso compartido de aplicaciones).**

  - Establezca el valor de DSCP **24** en lugar de 46. (De nuevo, tenga en cuenta que no es necesario usar el valor de DSCP 24. El único requisito es usar un valor de DSCP distinto para el uso compartido de aplicaciones de los que se usaron para el audio y el vídeo.)

  - Use el intervalo de puertos configurado anteriormente para el tráfico de vídeo. Por ejemplo, si tiene reservados los puertos 40803 a 49151 para uso compartido de aplicaciones, establezca el intervalo de puertos en: **40803:49151**.

Las nuevas directivas que haya creado no surtendrán efecto hasta que la directiva de grupo se haya actualizado en los servidores perimetrales. Aunque la directiva de grupo se actualiza periódicamente por sí misma, puede forzar una actualización inmediata ejecutando el siguiente comando en cada equipo donde sea necesario actualizar la directiva de grupo:

 **Gpudate.exe /force**

Este comando se puede ejecutar desde el Skype Empresarial Server o desde cualquier ventana de comandos que se ejecute con credenciales de administrador. Para ejecutar una ventana de comandos con credenciales de administrador, haga clic en **Inicio**, haga clic con el botón secundario en **Símbolo del sistema** y, a continuación, haga clic en **Ejecutar como administrador**. Tenga en cuenta que es posible que tenga que reiniciar el servidor perimetral incluso después de ejecutar Gpudate.exe.

Para asegurarse de que los paquetes de red se marquen con el valor de DSCP adecuado, debe crear también una nueva entrada del Registro en cada equipo, mediante el siguiente procedimiento:

1.  Haga clic en **Inicio** y luego en **Ejecutar**.

2.  En el **cuadro de** diálogo Ejecutar, escriba **regedit** y, a continuación, presione ENTRAR.

3.  En el Editor del Registro, expanda **HKEY \_ LOCAL \_ MACHINE**, **expanda SYSTEM**, **expand CurrentControlSet**, expand **services** y, a continuación, **expande Tcpip**.

4.  Haga clic con el botón secundario en **Tcpip**, elija **Nuevo** y, a continuación, haga clic en **Clave**. Después de crear la nueva clave del Registro, escriba **QoS** y, a continuación, presione ENTRAR para cambiar el nombre de la clave.

5.  Haga clic con el botón secundario en **QoS**, elija **Nuevo** y, a continuación, haga clic en **Valor de cadena**. Después de crear el nuevo valor del Registro, escriba **No usar NLA** y, a continuación, presione ENTRAR para cambiar el nombre del valor.

6.  Haga clic con el botón secundario en **No usar NLA**. En el cuadro de diálogo Editar **cadena,** escriba **1** en el cuadro **Datos de** valor y, a continuación, haga clic en **Aceptar**.

7.  Cierre el Editor del Registro y reinicie el equipo.
