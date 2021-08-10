---
title: Configuración de intervalos de puertos y una directiva de calidad de servicio para los servidores de conferencia, aplicación y mediación
ms.reviewer: ''
ms:assetid: 4d6eaa5d-0127-453f-be6a-e55384772d83
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204872(v=OCS.15)
ms:contentKeyID: 48184074
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
description: En este artículo se describe cómo configurar intervalos de puertos y una directiva de calidad de servicio para los servidores de conferencia, aplicación y mediación.
ms.openlocfilehash: 14a9bd1b4e32ab68b01746edaca77337654ea391737f38129c7e482fdcd49324
ms.sourcegitcommit: 0e9516c51105e4d89c550d2ea2bd8e7649a1163b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/06/2021
ms.locfileid: "54591084"
---
# <a name="configuring-port-ranges-and-a-quality-of-service-policy-for-your-conferencing-application-and-mediation-servers"></a>Configuración de intervalos de puertos y una directiva de calidad de servicio para los servidores de conferencia, aplicación y mediación

En este artículo se describe cómo configurar intervalos de puertos y una directiva de calidad de servicio para los servidores de conferencia, aplicación y mediación.

## <a name="configure-port-ranges"></a>Configurar intervalos de puertos

Para implementar la calidad del servicio, debe configurar intervalos de puertos idénticos para el uso compartido de audio, vídeo y aplicaciones en los servidores de conferencia, aplicación y mediación; Además, esos intervalos de puertos no deben superponerse de ninguna manera. Para usar un ejemplo sencillo, suponga que usa los puertos 10000 hasta 10999 para vídeo en los servidores de conferencias. Eso significa que también deben reservar los puertos 10000 hasta 10999 para vídeo en sus servidores de aplicaciones y mediación. Si no lo haces, QoS no funcionará como se espera.

Del mismo modo, suponga que reserva los puertos 10000 hasta 10999 para vídeo, pero luego reserva los puertos 10500 hasta 11999 para audio. Esto puede crear problemas de Calidad de servicio, porque los intervalos de puerto se superponen. Con QoS, cada modalidad debe tener un conjunto único de puertos: si usa puertos de 10000 a 10999 para vídeo, tendrá que usar un intervalo diferente (por ejemplo, de 11000 a 11999, para audio).

De forma predeterminada, los intervalos de puertos de audio y vídeo no se superponen en Skype Empresarial Server; sin embargo, los intervalos de puertos asignados al uso compartido de aplicaciones se superponen con los intervalos de puertos de audio y vídeo. (Lo que, a su vez, significa que ninguno de estos rangos es único). Puede comprobar los intervalos de puertos existentes para los servidores de conferencia, aplicación y mediación ejecutando los tres comandos siguientes desde el Shell de administración de Skype Empresarial Server:

  Get-CsService -ConferencingServer | Select-Object Identity, AudioPortStart, AudioPortCount, VideoPortStart, VideoPortCount, AppSharingPortStart, AppSharingPortCount
    
  Get-CsService -ApplicationServer | Select-Object Identity, AudioPortStart, AudioPortCount
    
  Get-CsService -MediationServer | Select-Object Identity, AudioPortStart, AudioPortCount

> [!WARNING]  
> Como puede ver en los comandos anteriores, a cada tipo de puerto: audio, vídeo y uso compartido de aplicaciones se les asigna dos valores de propiedad separados: el puerto de inicio y el número de puerto. El inicio de puerto indica el primer puerto que se usa para esa modalidad; por ejemplo, si el puerto de inicio de audio es igual a 50000, significa que el primer puerto que se usa para el tráfico de audio es puerto 50000. Si el número de puertos de audio es 2 (que no es un valor válido, pero se usa aquí para fines ilustrativos), significa que solo se asignan dos puertos para audio. Si el primer puerto es el puerto 50000 y hay un total de dos puertos, eso significa que el segundo puerto debe ser el 50001 (los intervalos de puertos tienen que ser contiguos). Como resultado, el intervalo de puertos de audio sería del puerto 50000 hasta el 50001, incluidos.<BR><br>Tenga en cuenta que el servidor de aplicaciones y el servidor de mediación solo admiten QoS para audio; no necesita cambiar el vídeo o el uso compartido de aplicaciones de puertos en sus servidores de aplicaciones o mediación.

Si ejecuta los tres comandos anteriores, verá que los valores de puerto predeterminados para Skype Empresarial Server están configurados de esta manera:

<table>
<colgroup>
</colgroup>
<thead>
<tr class="header">
<th>Propiedad</th>
<th>Servidor de conferencias</th>
<th>Servidor de aplicaciones</th>
<th>Servidor de mediación</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>AudioPortStart</p></td>
<td><p>49152</p></td>
<td><p>49152</p></td>
<td><p>49152</p></td>
</tr>
<tr class="even">
<td><p>AudioPortCount</p></td>
<td><p>8348</p></td>
<td><p>8348</p></td>
<td><p>8348</p></td>
</tr>
<tr class="odd">
<td><p>VideoPortStart</p></td>
<td><p>57501</p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
<tr class="even">
<td><p>VideoPortCount</p></td>
<td><p>8034</p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
<tr class="odd">
<td><p>ApplicationSharingPortStart</p></td>
<td><p>49152</p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
<tr class="even">
<td><p>ApplicationSharingPortCount</p></td>
<td><p>16383</p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
</tbody>
</table>

Como se mencionó anteriormente, al configurar puertos Skype Empresarial Server para QoS, debe asegurarse de que: 1) la configuración de puertos de audio sea idéntica en los servidores de conferencia, aplicación y mediación; y, 2) los intervalos de puertos no se superponen. Si observa detenidamente la tabla anterior, verá que los intervalos de puertos son idénticos a través de los tres tipos de servidores. Por ejemplo, el puerto de inicio de audio se establece en Puerto 49152 en cada tipo de servidor y el número total de puertos reservados en cada servidor de audio también es idéntico: 8348. Sin embargo, el intervalo de puertos se superpone: los puertos de audio comienzan en el puerto 49152, pero, al hacerlo así, los puertos se reservan para uso compartido de aplicaciones. Para usar correctamente la Calidad de servicio, el uso compartido de aplicaciones debe configurarse para utilizar un único intervalo de puertos. Por ejemplo, podría configurar el uso compartido de aplicaciones para que se inicie en el puerto 40803 y use 8348 puertos. ¿Por qué 8348 puertos? Si agrega esos valores juntos (40803 + 8348), significa que el uso compartido de aplicaciones usará los puertos 40803 a través del puerto 49150. Ya que los puertos de audio no comienzan hasta el puerto 49152, ya no tendrá ningún intervalo de puertos superpuestos.

Después de seleccionar el nuevo intervalo de puertos para el uso compartido de aplicaciones, puede realizar el cambio mediante el cmdlet Set-CsConferencingServer aplicación. Este cambio no tiene que hacerse en los servidores de aplicaciones o en los servidores de mediación, porque estos servidores no controlan tráfico de uso compartido de aplicaciones. Solo necesita cambiar los valores del puerto en estos servidores si decide volver a asignar los puertos usados para el tráfico de audio.

Para modificar los valores de puerto para el uso compartido de aplicaciones en un único servidor de conferencia, ejecute un comando similar a este desde el Shell de administración de Skype Empresarial Server:

  **Set-CsConferenceServer -Identity ConferencingServer:atl-cs-001.litwareinc.com -AppSharingPortStart 40803 -AppSharingPortCount 8348**

Si desea realizar estos cambios en todos los servidores de conferencia, puede ejecutar este comando en su lugar:

  **Get-CsService -ConferencingServer | ForEach-Object {Set-CsConferenceServer -Identity $_. Identity -AppSharingPortStart 40803 -AppSharingPortCount 8348}**

Después de cambiar la configuración de puerto, debe detener y reiniciar cada servicio afectado por los cambios.

No es obligatorio que los servidores de conferencias, servidores de aplicaciones y servidores de mediación compartan el mismo intervalo de puertos exacto; el único requisito real es que reserve intervalos de puertos únicos en todos los servidores. Sin embargo, la administración suele ser más fácil si se usa el mismo conjunto de puertos en todos los servidores.

## <a name="configure-a-quality-of-service-policy-in-skype-for-business-server-for-your-conferencing-application-and-mediation-servers"></a>Configurar una directiva de calidad de servicio en Skype Empresarial Server para los servidores de conferencia, aplicación y mediación

Configurar intervalos de puertos facilita el uso de Calidad de servicio, al hacer que todo el tráfico de un determinado tipo (por ejemplo, todo el tráfico de audio) se transmita a través del mismo conjunto de puertos. De este modo, resulta fácil para el sistema identificar y marcar un cierto paquete: si el puerto 49152 está reservado al tráfico de audio, todos los paquetes que se transmiten a través del puerto 49152 se pueden marcar con un código DSCP que indica que se trata de paquetes de audio. A su vez, esto permite a los enrutadores identificar el paquete como un paquete de audio y darle mayor prioridad que a los paquetes sin marcar (por ejemplo, los paquetes que se usan para copiar un archivo de un servidor a otro).

Sin embargo, el solo hecho de restringir un conjunto de puertos a un tipo específico de tráfico no hace que los paquetes que se transmiten a través de esos puertos se marquen con el código DSCP correspondiente. Además de definir intervalos de puertos, también debe crear directivas de calidad de servicio que especifiquen el código DSCP que se asociará a cada intervalo de puertos. Por Skype Empresarial Server, esto suele significar la creación de dos directivas: una para audio y otra para vídeo.

Las directivas de calidad de servicio se crean y administran con mayor facilidad mediante la directiva de grupo. (Estas mismas directivas también se pueden crear mediante directivas de seguridad locales. Sin embargo, eso requiere que repita el mismo procedimiento en todos y cada uno de los equipos). El conjunto inicial de directivas de QoS (una para audio y otra para vídeo) solo se debe aplicar Skype Empresarial Server los equipos que ejecutan el servidor de conferencia, el servidor de aplicaciones o los servicios de servidor de mediación. Si todos estos equipos se encuentran en la misma unidad organizativa de Active Directory, simplemente puede asignar el nuevo objeto de directiva de grupo (GPO) a esa unidad organizativa. Como alternativa, puede realizar otros pasos para dirigir la nueva directiva a los equipos especificados; Por ejemplo, puede colocar los equipos adecuados en un grupo de seguridad y, a continuación, usar el filtrado de seguridad de directivas de grupo para aplicar el GPO solo a ese grupo de seguridad.

Para crear una directiva de calidad de servicio para administrar audio, inicie sesión en un equipo donde se haya instalado la administración de directivas de grupo. Abra la Administración de directivas de grupo (haga clic en **Inicio**, seleccione **Herramientas administrativas** y, a continuación, haga clic en **Administración de directivas de grupo**) y, a continuación, complemente el siguiente procedimiento:

1.  En la Administración de directivas de grupo, busque el contenedor en el que se deba crear la nueva directiva. Por ejemplo, si todos los Skype Empresarial Server están ubicados en una OU denominada Skype Empresarial Server, la nueva directiva debe crearse en la unidad organizativa Skype Empresarial Server usuario.

2.  Haga clic con el botón secundario en el contenedor adecuado y, a continuación, haga clic en Crear un GPO en este **dominio y vincule aquí**.

3.  En el cuadro de diálogo Nuevo **GPO,** escriba un  nombre para el nuevo objeto de directiva de grupo en el cuadro Nombre (por ejemplo, **Skype Empresarial Server QoS)** y, a continuación, haga clic en **Aceptar**.

4.  Haga clic con el botón secundario en la directiva recién creada y, a continuación, haga clic **en Editar**.

5.  En el Editor de administración de directivas de grupo, expanda **Configuración del equipo**, expanda **Directivas**, expanda **Configuración de Windows**, haga clic con el botón secundario en **QoS basada en directivas** y, a continuación, haga clic en **Crear nueva directiva**.

6.  En el cuadro de diálogo **QoS** basado en directivas, en la página de apertura, escriba un nombre para la nueva directiva (por ejemplo, Skype Empresarial Server **QoS**) en el cuadro **Nombre.** Seleccione **Especificar el valor de DSCP** y, a continuación, defina el valor en **46**. Deje sin seleccionar **Especificar velocidad de salida del acelerador** y, a continuación, haga clic en **Siguiente**.

7.  En la página siguiente, asegúrese de que **todas las aplicaciones** están seleccionadas y, a continuación, haga clic en **Siguiente**. Esto sirve, simplemente, para hacer que todas las aplicaciones relacionen los paquetes del intervalo de puertos especificado con el código DSCP especificado.

8.  En la tercera página, asegúrese de que todas las direcciones IP de origen y cualquier dirección **IP** de destino están seleccionadas y, a continuación, haga clic **en Siguiente**. Con estas dos opciones de configuración activadas, los paquetes se administrarán sin importar qué equipo (dirección IP) los envió ni qué equipo (dirección IP) los recibirá.

9.  En la página cuatro, seleccione **TCP y UDP** en la lista desplegable **Seleccione el protocolo para el que se aplica esta directiva de QoS**. TCP (Transmission Control Protocol) y UDP (User Datagram Protocol) son los dos protocolos de red más usados por Skype Empresarial Server y sus aplicaciones cliente.

10. Debajo del encabezado **Especifique el número de puerto de origen**, seleccione **Desde este intervalo o puerto de origen**. En el cuadro de texto que acompaña a esta opción, escriba el intervalo de puertos reservado a las transmisiones de audio. Por ejemplo, si reservó los puertos 49152 a través de los puertos 57500 para el tráfico de audio, escriba el intervalo de puertos con este formato: **49152:57500**. Haga clic en **Finalizar**.

> [!NOTE]  
> El valor de DSCP de 46 es algo arbitrario: aunque DSCP 46 se utiliza a menudo para marcar paquetes de audio, no es necesario que use DSCP 46 para las comunicaciones de audio. Si ya ha implementado QoS y está usando un código DSCP diferente para audio (por ejemplo, DSCP 40), debe configurar la directiva de calidad de servicio para que use ese mismo código (es decir, 40 para audio). Si está implementando Calidad de servicio ahora, se recomienda usar DSCP 46 para el audio, simplemente, porque es el valor que se suele usar para marcar paquetes de audio.

Después de crear la directiva QoS para el tráfico de audio, debe crear una segunda directiva para el tráfico de vídeo (y, opcionalmente, una tercera directiva para administrar el tráfico de uso compartido de aplicaciones). Para crear una directiva destinada al vídeo, siga el mismo procedimiento básico que llevó a cabo al crear la directiva de audio, sustituyendo lo siguiente:

  - Use un nombre de directiva diferente (y único) (por ejemplo, **Skype Empresarial Server Video**).

  - Establezca el valor de DSCP **34** en lugar de 46. (Tenga en cuenta que no es necesario usar el valor de DSCP 34. El único requisito es usar un valor de DSCP distinto para el vídeo del que se usó para el audio.)

  - Use el intervalo de puertos configurado anteriormente para el tráfico de vídeo. Por ejemplo, si tiene reservados los puertos 57501 a 65535 para vídeo, establezca el intervalo de puertos en: **57501:65535**.

Si decide crear una directiva para administrar el tráfico compartido de aplicaciones, debe crear una tercera directiva, realizando las siguientes sustituciones:

  - Use un nombre de directiva diferente (y único) (por ejemplo, **Skype Empresarial Server uso compartido de aplicaciones).**

  - Establezca el valor de DSCP **24** en lugar de 46. (De nuevo, tenga en cuenta que no es necesario usar el valor de DSCP 24. El único requisito es usar un valor de DSCP distinto para el uso compartido de aplicaciones de los que se usaron para el audio y el vídeo.)

  - Use el intervalo de puertos configurado anteriormente para el tráfico de vídeo. Por ejemplo, si tiene reservados los puertos 40803 a 49151 para uso compartido de aplicaciones, establezca el intervalo de puertos en: **40803:49151**.

Las nuevas directivas que haya creado no tendrán efecto hasta que la directiva de grupo se haya actualizado en los Skype Empresarial Server equipos. Aunque la directiva de grupo se actualiza periódicamente por sí misma, puede forzar una actualización inmediata ejecutando el siguiente comando en cada equipo donde sea necesario actualizar la directiva de grupo:

  **Gpupdate.exe /force**

Este comando se puede ejecutar desde el Shell Skype Empresarial Server de administración o desde cualquier ventana de comandos que se ejecute con credenciales de administrador. Para ejecutar una ventana de comandos con credenciales de administrador, haga clic en **Inicio**, haga clic con el botón secundario en **Símbolo del sistema** y, a continuación, haga clic en **Ejecutar como administrador**.

Para comprobar que se han aplicado las nuevas directivas de QoS, haga lo siguiente:

1.  En un equipo Skype Empresarial Server, haga clic **en Inicio** y, a continuación, haga clic en **Ejecutar**.

2.  En el **cuadro de** diálogo Ejecutar, escriba **regedit** y, a continuación, presione ENTRAR.

3.  En el Editor del Registro, expanda Equipo **,** expanda **HKEY LOCAL \_ \_ MACHINE**, **expanda SOFTWARE**, expanda **Directivas**, **expanda Microsoft**, expanda Windows y, **a** continuación, haga clic en **QoS**. Debajo de **QoS**, debería ver las claves del Registro de cada una de las directivas de QoS que acaba de crear. Por ejemplo, si creó dos directivas nuevas (una denominada Skype Empresarial Server Audio QoS y la otra denominada Skype Empresarial Server Video QoS), debería ver las entradas del Registro para Skype Empresarial Server Audio QoS y Skype Empresarial Server Video QoS.

Para asegurarse de que los paquetes de red se marquen con el valor de DSCP adecuado, debe crear también una nueva entrada del Registro en cada equipo, mediante el siguiente procedimiento:

1.  Haga clic en **Inicio** y luego en **Ejecutar**.

2.  En el **cuadro de** diálogo Ejecutar, escriba **regedit** y, a continuación, presione ENTRAR.

3.  En el Editor del Registro, expanda **HKEY \_ LOCAL \_ MACHINE**, **expanda SYSTEM**, **expand CurrentControlSet**, expand **services** y, a continuación, **expande Tcpip**.

4.  Haga clic con el botón secundario en **Tcpip**, elija **Nuevo** y, a continuación, haga clic en **Clave**. Después de crear la nueva clave del Registro, escriba **QoS** y, a continuación, presione ENTRAR para cambiar el nombre de la clave.

5.  Haga clic con el botón secundario en **QoS**, elija **Nuevo** y, a continuación, haga clic en **Valor de cadena**. Después de crear el nuevo valor del Registro, escriba **No usar NLA** y, a continuación, presione ENTRAR para cambiar el nombre del valor.

6.  Haga doble clic en **No usar NLA**. En el cuadro de diálogo Editar **cadena,** escriba **1** en el cuadro **Datos de** valor y, a continuación, haga clic en **Aceptar**.

7.  Cierre el Editor del Registro y reinicie el equipo.
