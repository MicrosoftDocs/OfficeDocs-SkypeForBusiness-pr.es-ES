---
title: 'Lync Server 2013: modificar las opciones de configuración del tronco del SIP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify SIP trunk configuration settings
ms:assetid: 7d68b09c-9ea0-43bd-997c-df887869d607
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688104(v=OCS.15)
ms:contentKeyID: 49733703
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 809f7a94a4ab211f1bf21483729519cd53de2a2d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756924"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-sip-trunk-configuration-settings-in-lync-server-2013"></a>Modificar la configuración de los enlaces de SIP en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-22_

Los ajustes de configuración del tronco del SIP definen la relación y las capacidades entre un servidor de mediación y la puerta de enlace de red de telefonía pública conmutada (RTC), una central de conmutación (PBX) IP o un controlador de borde de sesión (SBC) en el proveedor de servicios. Estas opciones de configuración especifican:

  - Si se debe activar la omisión de medios en los troncos.

  - Las condiciones en que se envían paquetes de protocolo de control de transporte (RTCP) en tiempo real.

  - Si se requiere o no cifrado de protocolo en tiempo real seguro (SRTP) en cada tronco.

Al instalar Microsoft Lync Server 2013, se crea una colección global de parámetros de configuración del tronco del SIP. Los administradores también pueden crear colecciones de valores personalizadas en el ámbito del sitio o servicio (solo para el servicio de puerta de enlace de RTC). Cualquiera de estas colecciones se puede modificar posteriormente con el panel de control de Lync Server o Windows PowerShell.

Al modificar las opciones de configuración del tronco del SIP mediante el panel de control de Lync Server, las siguientes opciones están disponibles:


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Valor de IU</th>
<th>Parámetro de PowerShell</th>
<th>Descripción</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Nombre</p></td>
<td><p>Identity</p></td>
<td><p>Identificador único para la colección. Esta propiedad es de solo lectura; no puede cambiar la Identidad de una colección o las opciones de configuración de troncos.</p></td>
</tr>
<tr class="even">
<td><p>Descripción</p></td>
<td><p>Description</p></td>
<td><p>Proporciona un método para que los administradores almacenen información adicional acerca de la configuración (por ejemplo, el propósito de la configuración de troncos).</p></td>
</tr>
<tr class="odd">
<td><p>Número máximo de diálogos iniciales admitidos</p></td>
<td><p>MaxEarlyDialogs</p></td>
<td><p>Cantidad máxima de respuestas bifurcadas que puede recibir una puerta de enlace RTC, IP-PBX o SBC en el proveedor de servicio para una invitación enviada al Servidor de mediación.</p></td>
</tr>
<tr class="even">
<td><p>Nivel de compatibilidad de cifrado</p></td>
<td><p>SRTPMode</p></td>
<td><p>Indica el nivel de compatibilidad para proteger el tráfico de medios entre el Servidor de mediación y la puerta de enlace RTC, IP-PBX o SBC en el proveedor de servicio. Para los casos de omisión de medios, este valor debe ser compatible con la configuración de EncryptionLevel en la configuración de medios. La configuración multimedia se establece mediante los cmdlets <a href="https://docs.microsoft.com/powershell/module/skype/New-CsMediaConfiguration">New-CsMediaConfiguration</a> y <a href="https://docs.microsoft.com/powershell/module/skype/Set-CsMediaConfiguration">set-CsMediaConfiguration</a> .</p>
<p>Los valores permitidos son:</p>
<ul>
<li><p>Requeridos: debe usarse el cifrado SRTP.</p></li>
<li><p>Opcional: el SRTP se usará si la puerta de enlace lo admite.</p></li>
<li><p>No admitido: el cifrado SRTP no está admitido y, por lo tanto, no se usará.</p></li>
</ul>
<p>El SRTPMode se usa solo si la puerta de enlace está configurada para usar la Seguridad de la capa de transporte (TLS). Si la puerta de enlace está configurada con el Protocolo de control de transporte (TCP) como transporte, SRTPMode se configura internamente como No admitido.</p></td>
</tr>
<tr class="odd">
<td><p>Compatibilidad con referencias</p></td>
<td><p>Enable3pccRefer</p>
<p>EnableReferSupport</p></td>
<td><p>Si se establece en <strong>Habilitar referencias de envío a la puerta de enlace</strong>, indica que el tronco admite la recepción de Solicitudes de referencia del Servidor de mediación.</p>
<p>Si se establece en en <strong>Habilitar referencia mediante el control de llamadas a terceros</strong>, indica que se puede usar el protocolo 3pcc para permitir llamadas transferidas para omitir el sitio hospedado. 3pcc también se conoce como &quot;control de terceros&quot; y se produce cuando se usa un tercero para conectar un par de personas que llaman (por ejemplo, un operador que llama a la persona a a la persona B).</p></td>
</tr>
<tr class="even">
<td><p>Habilitar omisión de medios</p></td>
<td><p>EnableBypass</p></td>
<td><p>Indica si la omisión de medios está habilitada para este tronco. La omisión de medios solo puede estar habilitada si la opción <strong>Procesamiento de medios centralizado</strong> también está habilitada.</p></td>
</tr>
<tr class="odd">
<td><p>Procesamiento de medios centralizado</p></td>
<td><p>ConcentratedTopology</p></td>
<td><p>Indica si existe un punto de terminación de medios conocido. (Un ejemplo de punto de terminación de medios conocido puede ser una puerta de enlace RTC donde una terminación de medios tiene la misma IP que la terminación de señal).</p></td>
</tr>
<tr class="even">
<td><p>Habilitar cierre RTP</p></td>
<td><p>EnableRTPLatching</p></td>
<td><p>Indica si los troncos admiten o no el cierre RTP. El cierre RTP es una tecnología que permite la conectividad RTP/RTCP mediante un firewall o dispositivo NAT (traductor de direcciones de red).</p></td>
</tr>
<tr class="odd">
<td><p>Habilitar el historial de llamadas reenviadas</p></td>
<td><p>ForwardCallHistory</p></td>
<td><p>Indica si la información del historial de llamadas se reenviará a través del tronco.</p></td>
</tr>
<tr class="even">
<td><p>Habilitar el reenvío de datos P-Asserted-Identity</p></td>
<td><p>ForwardPAI</p></td>
<td><p>Indica si el encabezado P-Asserted-Identity (PAI) se reenviará junto con la llamada. El encabezado PAI proporciona un método para comprobar la identidad de la persona que realiza la llamada.</p></td>
</tr>
<tr class="odd">
<td><p>Habilitar temporizador de conmutación por error del enrutamiento de salida</p></td>
<td><p>EnableFastFailoverTimer</p></td>
<td><p>Indica que si las llamadas salientes no son respondidas por la puerta de enlace en el plazo de 10 segundos se enrutarán al siguiente tronco disponible; si no existen troncos adicionales, la llamada se perderá automáticamente. En una organización con redes y respuestas de puerta de enlace lentas, esto puede tener como resultado que las llamadas se pierdan innecesariamente.</p></td>
</tr>
<tr class="even">
<td><p>Usos de la RTC asociados</p></td>
<td><p>PSTNUsages</p></td>
<td><p>Colección de usos de RTC asignados al tronco.</p></td>
</tr>
<tr class="odd">
<td><p>Número traducido para probar</p></td>
<td><p>N/D</p></td>
<td><p>Número telefónico que puede usare para realizar una prueba ad hoc de la configuración del tronco.</p></td>
</tr>
<tr class="even">
<td><p>Reglas de conversión asociadas</p></td>
<td><p>OutboundTranslationRulesList</p></td>
<td><p>Recopilación de reglas de conversión de números telefónicos que se aplican a las llamadas administradas por el Enrutamiento de salida (llamadas enrutadas a destinos PBX o RTC).</p></td>
</tr>
<tr class="odd">
<td><p>Reglas de traducción de números llamados</p></td>
<td><p>OutboundCallingNumberTranslationRulesList</p></td>
<td><p>Colección de reglas de conversión de números de llamadas salientes asignadas al tronco.</p></td>
</tr>
<tr class="even">
<td><p>Número de teléfono para probar</p></td>
<td><p>N/D</p></td>
<td><p>Número telefónico que puede usarse para realizar una prueba ad hoc de las reglas de conversión.</p></td>
</tr>
<tr class="odd">
<td><p>Número que llamada</p></td>
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


<div>


> [!NOTE]  
> Los cmdlets de CsTrunkConfiguration de Lync Server admiten propiedades adicionales que no se muestran en el panel de control de Lync Server. Para obtener más información, consulte el tema de ayuda para el cmdlet <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsTrunkConfiguration">set-CsTrunkConfiguration</A> .



</div>

<div>

## <a name="to-modify-sip-trunk-configuration-settings-by-using-lync-server-control-panel"></a>Para modificar los ajustes de configuración del tronco del Protocolo de PREENLACE SIP con el panel de control de Lync Server

1.  En el panel de control de Lync Server, haga clic en **enrutamiento de voz**y luego en **configuración troncal**.

2.  En la pestaña **Configuración de tronco**, haga doble clic en las opciones de configuración de tronco que se modificarán. Tenga en cuenta que solo puede editar un grupo de opciones de configuración a la vez. Si desea realizar los mismos cambios en varias colecciones, use Windows PowerShell.

3.  En el cuadro de diálogo **Editar configuración de tronco**, realice las selecciones apropiadas y seleccione **Aceptar**.

4.  La propiedad **Estado** para la colección se actualizará a **No confirmado**. Para confirmar los cambios y eliminar la colección, haga clic en **Confirmar** y luego en **Confirmar todo**.

5.  En el cuadro de diálogo **Valores de configuración de voz no confirmados**, haga clic en **Aceptar**.

6.  En el cuadro de diálogo **Panel de control de Microsoft Lync Server 2013** , haga clic en **Aceptar**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

