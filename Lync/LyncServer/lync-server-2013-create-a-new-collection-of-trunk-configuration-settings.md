---
title: "Crear nuevo conjunto de opciones de configuración de troncos en Lync Server 2013"
TOCTitle: "Création d’une coll. de par. de conf. d’une jonction dans Lync Server 2013"
ms:assetid: 4ebd710c-38cd-4cff-9a45-df029d424580
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ688054(v=OCS.15)
ms:contentKeyID: 49889081
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Creación de un nuevo conjunto de opciones de configuración de troncos en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

Los parámetros de configuración del tronco SBP definen la relación y las capacidades entre el servidor de mediación y la puerta de enlace de la red telefónica conmutada (RTC) pública, una central de conmutación pública de IP (PBX) o un controlador de borde de sesión (SBC) en el proveedor de servicios. Estos parámetros hacen cosas como especificar:

  - Si el desvío de medios debe habilitarse en los troncos.

  - Las condiciones en las que se envían paquetes de protocolo de control de transporte en tiempo real (RTCP).

  - Si se necesita el cifrado del protocolo en tiempo real seguro (SRTP) en cada tronco.

Al instalar Microsoft Lync Server 2013, se crea una colección global de parámetros de configuración de troncos SIP. Además, los administradores pueden crear colecciones de parámetros personalizados en el ámbito del sitio o en el ámbito del servicio (solo para el servicio de puerta de enlace RTC).

Al crear parámetros de configuración del tronco SBP con Panel de control de Lync Server, están disponibles las siguientes opciones:


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Configuración de IU</th>
<th>Parámetro PowerShell</th>
<th>Descripción</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Nombre</p></td>
<td><p>Identidad</p></td>
<td><p>Identificador único de la colección. Esta propiedad es de solo lectura; no se puede cambiar la identidad de una colección de parámetros de configuración de troncos.</p></td>
</tr>
<tr class="even">
<td><p>Descripción</p></td>
<td><p>Descripción</p></td>
<td><p>Proporciona una manera para que los administradores almacenen información adicional sobre los parámetros (por ejemplo, el propósito de la configuración del tronco).</p></td>
</tr>
<tr class="odd">
<td><p>Número máximo de diálogos iniciales admitidos</p></td>
<td><p>MaxEarlyDialogs</p></td>
<td><p>El número máximo de respuestas bifurcadas que una puerta de enlace RTC, un sistema IP-PBX o el SBC del proveedor de servicios puede recibir para una invitación (Invite) enviada al servidor de mediación.</p></td>
</tr>
<tr class="even">
<td><p>Nivel de compatibilidad de cifrado</p></td>
<td><p>SRTPMode</p></td>
<td><p>Indica el nivel de compatibilidad para proteger el tráfico de medios entre el servidor de mediación y la puerta de enlace RTC, el sistema IP-PBX o el controlador SBC en el proveedor de servicios. En los casos de desvío de medios, este valor debe ser compatible con el valor de EncryptionLevel en la configuración de medios. La configuración de medios se define mediante los cmdlets <a href="https://docs.microsoft.com/en-us/powershell/module/skype/New-CsMediaConfiguration">New-CsMediaConfiguration</a> y <a href="https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsMediaConfiguration">Set-CsMediaConfiguration</a>.</p>
<p>Los valores permitidos son:</p>
<ul>
<li><p>- Required: debe usarse el cifrado SRTP.</p></li>
<li><p>- Optional: se usará el cifrado SRTP si la puerta de enlace lo admite.</p></li>
<li><p>- NotSupported: el cifrado SRTP no está admitido y, por tanto, no se usará.</p></li>
</ul>
<p>SRTPMode solo se utiliza si la puerta de enlace está configurada para usar TLS (Seguridad de la capa de transporte). Si la puerta de enlace está configurada con TCP (Protocolo de control de transmisión) como transporte, SRTPMode se establece internamente en NotSupported.</p></td>
</tr>
<tr class="odd">
<td><p>Compatibilidad con referencias</p></td>
<td><p>Enable3pccRefer</p>
<p>EnableReferSupport</p></td>
<td><p>Si se establece en <strong>Habilitar el envío de referencias a la puerta de enlace</strong>, indica que el tronco admite la recepción de solicitudes de referencias desde el servidor de mediación.</p>
<p>Si se establece en <strong>habilitar que la referencia use el control de llamadas de terceros</strong>, indica que se puede usar el protocolo 3pcc para permitir que las llamadas transferidas omitan el sitio del host. 3pcc también se conoce como &quot;control de terceros&quot; y ocurre cuando se usa un tercero para conectar un par de autores de llamadas (por ejemplo, un operador que coloca una llamada de la persona A a la persona B).</p></td>
</tr>
<tr class="even">
<td><p>Habilitar desvío de medios</p></td>
<td><p>EnableBypass</p></td>
<td><p>Indica si está habilitado el desvío de medios para este tronco. El desvío de medios solo se puede habilitar si también está habilitado <strong>Procesamiento de medios centralizado</strong>.</p></td>
</tr>
<tr class="odd">
<td><p>Procesamiento de medios centralizado</p></td>
<td><p>ConcentratedTopology</p></td>
<td><p>(Un ejemplo de un punto de terminación de medios conocido sería una puerta de enlace RTC cuya terminación de medios tenga la misma IP que la terminación de señalización).</p></td>
</tr>
<tr class="even">
<td><p>Habilitar cierre RTP</p></td>
<td><p>EnableRTPLatching</p></td>
<td><p>Indica si los troncos SIP admiten el cierre RTP. El cierre RTP es una tecnología que permite la conectividad RTP/RTCP a través de un dispositivo NAT (traductor de direcciones de red) o firewall.</p></td>
</tr>
<tr class="odd">
<td><p>Habilitar el reenvío del historial de llamadas</p></td>
<td><p>ForwardCallHistory</p></td>
<td><p>Indica si la información del historial de llamadas se reenviará a través del tronco.</p></td>
</tr>
<tr class="even">
<td><p>Habilitar reenvío de datos de la identidad afirmada</p></td>
<td><p>ForwardPAI</p></td>
<td><p>Indica si el encabezado de la identidad afirmada (PAI) se enviará junto con la llamada. El encabezado PAI proporciona una manera de comprobar la identidad del autor de la llamada.</p></td>
</tr>
<tr class="odd">
<td><p>Habilitar el temporizador de conmutación por error de enrutamiento saliente</p></td>
<td><p>EnableFastFailoverTimer</p></td>
<td><p>Indica si se enrutarán al siguiente tronco disponible las llamadas salientes no respondidas por la puerta de enlace en 10 segundos; si no hay troncos adicionales, la llamada quitará se automáticamente. En una organización con respuestas de la puerta de enlace y redes lentas, podría hacer que las llamadas se quitaran innecesariamente.</p></td>
</tr>
<tr class="even">
<td><p>Usos de la RTC asociados</p></td>
<td><p>PSTNUsages</p></td>
<td><p>Colección de usos de RTC asignados al tronco.</p></td>
</tr>
<tr class="odd">
<td><p>Número traducido para probar</p></td>
<td><p>N/D</p></td>
<td><p>Número de teléfono que puede usarse para hacer una prueba ad-hoc de los parámetros de configuración del tronco.</p></td>
</tr>
<tr class="even">
<td><p>Reglas de conversión asociadas</p></td>
<td><p>OutboundTranslationRulesList</p></td>
<td><p>Colección de reglas de conversión de números de teléfono que se aplican a las llamadas administradas por el enrutamiento saliente (llamadas enrutadas a destinos PBX o RTC).</p></td>
</tr>
<tr class="odd">
<td><p>Reglas de conversión de números llamados</p></td>
<td><p>OutboundCallingNumberTranslationRulesList</p></td>
<td><p>Colección de reglas de conversión de números de llamadas saliente asignados al tronco.</p></td>
</tr>
<tr class="even">
<td><p>Número de teléfono para probar</p></td>
<td><p>N/D</p></td>
<td><p>Número de teléfono que puede usarse para hacer una prueba ad-hoc de las reglas de conversión.</p></td>
</tr>
<tr class="odd">
<td><p>Número que llama</p></td>
<td><p>N/D</p></td>
<td><p>Indica que el número de teléfono para probar es el número de teléfono del que llama.</p></td>
</tr>
<tr class="even">
<td><p>Número llamado</p></td>
<td><p>N/D</p></td>
<td><p>Indica que el número de teléfono para probar es el número de teléfono de la persona a la que se llama.</p></td>
</tr>
</tbody>
</table>



> [!NOTE]
> Los cmdlets CsTrunkConfiguration de Lync Server admiten propiedades adicionales que no aparecen en el Panel de control de Lync Server. Para más información, vea el tema de ayuda del cmdlet <A href="https://docs.microsoft.com/en-us/powershell/module/skype/New-CsTrunkConfiguration">New-CsTrunkConfiguration</A>.



## Creación de nuevos parámetros de configuración de troncos con Panel de control de Lync Server

1.  En Panel de control de Lync Server, haga clic en **Enrutamiento de voz** y luego en **Configuración de tronco**.

2.  En la pestaña **Configuración de tronco**, haga clic en **Nuevo** y luego haga clic en **Tronco de sitio** para crear el nuevo parámetro en el ámbito del sitio o en **Tronco de grupo** para crear el nuevo parámetro en el ámbito del servicio.

3.  En el cuadro de diálogo **Seleccionar un sitio** o **Seleccionar un servicio** (el cuadro de diálogo que aparece depende de si va a crear parámetros de ámbito de sitio o ámbito de servicio) seleccione la ubicación para los nuevos parámetros de configuración y luego haga clic en **Aceptar**. Si el cuadro de diálogo está en blanco, significa que no hay lugar para crear los nuevos parámetros; por ejemplo, si el cuadro de diálogo **Seleccionar un sitio** está en blanco significa que todos los sitios ya se han asignado una colección de sitios de configuración del tronco y cada sitio (y cada servicio) solo puede alojar una de esas colecciones. En ese caso, puede eliminar la colección existente y crear una nueva o simplemente cambiar la colección existente.

4.  En el cuadro de diálogo **Nueva configuración de tronco**, relacione las selecciones adecuadas y haga clic en **Aceptar**.

5.  La propiedad **Estado** de la colección se actualizará a **No confirmado**. Para confirmar los cambios y eliminar la colección, haga clic en **Confirmar** y luego en **Confirmar todo**.

6.  En el cuadro de diálogo **Valores de configuración de voz no confirmados**, haga clic en **Aceptar**.

7.  En el cuadro de diálogo **Panel de control de Microsoft Lync Server 2013**, haga clic en **Aceptar**.

