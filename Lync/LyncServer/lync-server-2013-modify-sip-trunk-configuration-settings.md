---
title: "Modificación de las opciones de configuración de troncos SIP en Lync Server 2013"
TOCTitle: "Modif. des paramètres de conf. d’une jonction SIP dans Lync Server 2013"
ms:assetid: 7d68b09c-9ea0-43bd-997c-df887869d607
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ688104(v=OCS.15)
ms:contentKeyID: 49889243
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Modificación de las opciones de configuración de troncos SIP en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

Las opciones de configuración de troncos SIP definen la relación y funcionalidades entre el Servidor de Mediación y la puerta de enlace de la red telefónica conmutada (RTC), una central de conmutación de IP pública (PBX) o un controlador de borde de sesión (SBC) en el proveedor de servicio. Estas opciones de configuración hacen estas cosas como se especifica:

  - Si el desvío de medios debe habilitarse en los troncos.

  - Las condiciones en que se envían los paquetes de Protocolo de control de transporte en tiempo real (RTP).

  - Si se necesita o no un protocolo seguro en tiempo real (SRTP) en cada tronco.

Cuando instala Microsoft Lync Server 2013, una colección global de opciones de configuración de enlaces troncales SIP se crea por usted. Además, los administradores pueden crear colecciones de configuración personalizada en el ámbito del sitio o del servicio (solo para el servicio de puerta de enlace RTC). Cualquiera de estas colecciones luego puede modificarse mediante el Panel de control de Lync Server o Windows PowerShell.

Al modificar las opciones de configuración de troncos SIP con Panel de control de Lync Server, se ofrecen las siguientes opciones:


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Configuración de la IU</th>
<th>Parámetro PowerShell</th>
<th>Descripción</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Nombre</p></td>
<td><p>Identidad</p></td>
<td><p>Identificador único para la colección. Esta propiedad es de solo lectura; no puede cambiar la Identidad de una colección o las opciones de configuración de troncos.</p></td>
</tr>
<tr class="even">
<td><p>Descripción</p></td>
<td><p>Descripción</p></td>
<td><p>Proporciona una manera para que los administradores almacenen información adicional acerca de la configuración (por ejemplo, el propósito de la configuración de troncos).</p></td>
</tr>
<tr class="odd">
<td><p>Cantidad máxima de cuadros de diálogo admitidos</p></td>
<td><p>MaxEarlyDialogs</p></td>
<td><p>La cantidad máxima de respuestas bifurcadas que puede recibir una puerta de enlace RTC, IP-PBX o SBC en el proveedor de servicio para una invitación enviada al Servidor de mediación.</p></td>
</tr>
<tr class="even">
<td><p>Nivel de compatibilidad con el cifrado</p></td>
<td><p>SRTPMode</p></td>
<td><p>Indica el nivel de apoyo para proteger el tráfico de medios entre el Servidor de mediación y la puerta de enlace RTC, IP-PBX, o SBC en el proveedor de servicio. Para los casos de desvío de medios, este valor debe ser compatible con la configuración de EncryptionLevel en la configuración de medios. La configuración de medios se establece con los cmdlets <a href="https://docs.microsoft.com/en-us/powershell/module/skype/New-CsMediaConfiguration">New-CsMediaConfiguration</a> y <a href="https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsMediaConfiguration">Set-CsMediaConfiguration</a>.</p>
<p>los valores permitidos son los siguientes:</p>
<ul>
<li><p>Requeridos: debe usarse el cifrado SRTP.</p></li>
<li><p>Opcional: el SRTP se utilizará si la puerta de enlace lo admite.</p></li>
<li><p>No admitido: el cifrado SRTP no está admitido y, por lo tanto, no se utilizará.</p></li>
</ul>
<p>El SRTPMode se utiliza solo si la puerta de enlace está configurada para usar la Seguridad de la capa de transporte (TLS). Si la puerta de enlace está configurada con el Protocolo de control de transporte (TCP) como transporte, el SRTPMode se configura internamente como No admitido.</p></td>
</tr>
<tr class="odd">
<td><p>Hacer referencia al soporte</p></td>
<td><p>Enable3pccRefer</p>
<p>EnableReferSupport</p></td>
<td><p>Si se configura en <strong>Habilitar enviar referencia a la puerta de enlace</strong>, indica que el tronco admite la recepción de Solicitudes de referencia desde el Servidor de mediación.</p>
<p>Si está establecido como <strong>Habilitar la referencia mediante un control de llamadas de terceros</strong>, indica que el protocolo 3pcc puede ser utilizado para permitir llamadas transferidas para desviar el sitio hospedado. 3pcc también se conoce como &quot;control de terceros&quot; y ocurre cuando un tercero se utiliza para conectar un par de personas que llaman (por ejemplo, un operador que realiza una llamada de la persona A a una persona B).</p></td>
</tr>
<tr class="even">
<td><p>Habilitar el desvío de medios</p></td>
<td><p>EnableBypass</p></td>
<td><p>Indica si la omisión de medios se encuentra habilitado para este tronco. La omisión de medios solo puede estar habilitada si el <strong>Procesamiento de medios centralizado</strong> también está habilitado.</p></td>
</tr>
<tr class="odd">
<td><p>Procesamiento de medios centralizado</p></td>
<td><p>ConcentratedTopology</p></td>
<td><p>Indica si existe un punto de terminación de medios conocido. (Un ejemplo de punto de terminación de medios conocido puede ser una puerta de enlace RTC donde una terminación de medios tiene la misma IP que la terminación de señal).</p></td>
</tr>
<tr class="even">
<td><p>Habilitar el cierre RTP</p></td>
<td><p>EnableRTPLatching</p></td>
<td><p>Indica si los troncos admiten o no el cierre RTP. El cierre RTP es una tecnología que permite la conectividad RTP/RTCP mediante un firewall o dispositivo NAT (traductor de direcciones de red).</p></td>
</tr>
<tr class="odd">
<td><p>Habilitar el historial de desvío de llamadas</p></td>
<td><p>ForwardCallHistory</p></td>
<td><p>Indica si la información del historial de llamadas se reenviará mediante el tronco.</p></td>
</tr>
<tr class="even">
<td><p>Habilitar los datos de reenvío de la identidad p-asserted</p></td>
<td><p>ForwardPAI</p></td>
<td><p>Indica si el encabezado de la identidad p-asserted (PAI) se reenviará junto con la llamada. El encabezado PAI proporciona una forma de verificar la identidad de la persona que realiza la llamada.</p></td>
</tr>
<tr class="odd">
<td><p>Habilitar el temporizador de desvío de conmutación por error saliente</p></td>
<td><p>EnableFastFailoverTimer</p></td>
<td><p>Indica que si las llamadas salientes no son respondidas por la puerta de enlace dentro de los 10 segundos se enrutarán al siguiente tronco disponible; si no existen troncos adicionales, la llamada se perderá automáticamente. En una organización con redes y respuestas de puerta de enlace lentas, esto puede tener como resultado que se pierdan innecesariamente las llamadas.</p></td>
</tr>
<tr class="even">
<td><p>Usos asociados de la RTC</p></td>
<td><p>PSTNUsages</p></td>
<td><p>Recopilación de los usos de RTC asignados al tronco.</p></td>
</tr>
<tr class="odd">
<td><p>Número traducido para probar</p></td>
<td><p>N/D</p></td>
<td><p>Número telefónico que puede utilizarse para realizar una prueba ad hoc de la configuración del tronco.</p></td>
</tr>
<tr class="even">
<td><p>Reglas asociadas de traducción</p></td>
<td><p>OutboundTranslationRulesList</p></td>
<td><p>Recopilación de reglas de traducción de números telefónicos que se aplican a las llamadas administradas por el Enrutamiento de salida (llamadas enrutadas a destinos PBX o RTC).</p></td>
</tr>
<tr class="odd">
<td><p>Reglas de traducción de los números llamados</p></td>
<td><p>OutboundCallingNumberTranslationRulesList</p></td>
<td><p>Colección de reglas de traducción para números de llamada saliente asignadas al tronco.</p></td>
</tr>
<tr class="even">
<td><p>Número de teléfono que se debe probar</p></td>
<td><p>N/D</p></td>
<td><p>Número telefónico que puede utilizarse para realizar una prueba ad hoc de las reglas de traducción.</p></td>
</tr>
<tr class="odd">
<td><p>Número de llamada</p></td>
<td><p>N/D</p></td>
<td><p>Indica que el número de teléfono que se debe probar es el número telefónico de la persona que llama.</p></td>
</tr>
<tr class="even">
<td><p>Número llamado</p></td>
<td><p>N/D</p></td>
<td><p>Indica que el número de teléfono que se debe probar es el número telefónico de la persona llamada.</p></td>
</tr>
</tbody>
</table>



> [!NOTE]
> Loas cmdlets Lync Server CsTrunkConfiguration admiten propiedades adicionales que no se muestran en Panel de control de Lync Server. Para más información, vea la ayuda para el cmdlet <A href="https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsTrunkConfiguration">Set-CsTrunkConfiguration</A>.



## Modificar las opciones de configuración de troncos SIP con Panel de control de Lync Server

1.  En Panel de control de Lync Server, haga clic en **Enrutamiento de voz** y luego en **Configuración de tronco**.

2.  En la pestaña **Configuración de tronco** haga doble clic en las opciones de configuración de troncos que se modificarán. Tenga en cuenta que solo puede editar un grupo de opciones de configuración a la vez. Si desea realizar los mismos cambios en varias colecciones, utilice Windows PowerShell.

3.  En el cuadro de diálogo **Editar configuración de tronco**, realice las selecciones apropiadas y seleccione **Aceptar**.

4.  La propiedad **Estado** para la colección se actualizará a **No confirmado**. Para confirmar los cambios y eliminar la colección, haga clic en **Confirmar** y luego en **Confirmar todo**.

5.  En el cuadro de diálogo **Valores de configuración de voz no confirmados** haga clic en **Aceptar**.

6.  En el cuadro de diálogo **Panel de control de Microsoft Lync Server 2013** haga clic en **Aceptar**.

