---
title: 'Lync Server 2013: crear una nueva colección de opciones de configuración de tronco'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a new collection of trunk configuration settings
ms:assetid: 4ebd710c-38cd-4cff-9a45-df029d424580
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688054(v=OCS.15)
ms:contentKeyID: 49733647
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f07e5dc814887a7304a48602e04f48a00137bf8f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144987"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-a-new-collection-of-trunk-configuration-settings-in-lync-server-2013"></a>Crear una nueva colección de opciones de configuración de tronco en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-11-01_

Los valores de configuración de tronco SIP definen la relación y las capacidades entre un servidor de mediación y la puerta de enlace de la Red telefónica conmutada (RTC), una central de conmutación pública de IP (PBX) o un controlador de borde de sesión (SBC) en el proveedor de servicios. Estos valores determinan lo siguiente:

  - Si se debe habilitar el desvío de medios en los troncos.

  - Las condiciones en las que se envían los paquetes de protocolo de control de transporte en tiempo real (RTCP).

  - Si se requiere o no el cifrado del protocolo de tiempo real seguro (SRTP) en cada tronco.

Al instalar Microsoft Lync Server 2013, se crea una colección global de opciones de configuración de tronco SIP. Los administradores también pueden crear colecciones de valores personalizadas en el ámbito del sitio o servicio (solo para el servicio de puerta de enlace de RTC).

Al crear opciones de configuración de tronco SIP mediante el panel de control de Lync Server, están disponibles las siguientes opciones:


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
<td><p>Name</p></td>
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
<td><p>Indica el nivel de apoyo para proteger el tráfico de medios entre el Servidor de mediación y la puerta de enlace RTC, IP-PBX, o SBC en el proveedor de servicio. Para los casos de desvío de medios, este valor debe ser compatible con la configuración de EncryptionLevel en la configuración de medios. La configuración de medios se establece con los cmdlets <a href="https://docs.microsoft.com/powershell/module/skype/New-CsMediaConfiguration">New-CsMediaConfiguration</a> y <a href="https://docs.microsoft.com/powershell/module/skype/Set-CsMediaConfiguration">set-CsMediaConfiguration</a> .</p>
<p>Los valores permitidos son:</p>
<ul>
<li><p>Requeridos: debe usarse el cifrado SRTP.</p></li>
<li><p>Opcional: el SRTP se utilizará si la puerta de enlace lo admite.</p></li>
<li><p>No admitido: el cifrado SRTP no está admitido y, por lo tanto, no se utilizará.</p></li>
</ul>
<p>El SRTPMode se utiliza solo si la puerta de enlace está configurada para usar la Seguridad de la capa de transporte (TLS). Si la puerta de enlace está configurada con el Protocolo de control de transporte (TCP) como transporte, el SRTPMode se configura internamente como No admitido.</p></td>
</tr>
<tr class="odd">
<td><p>Hacer referencia al soporte</p></td>
<td><p>Parámetro enable3pccrefer</p>
<p>EnableReferSupport</p></td>
<td><p>Si se configura en <strong>Habilitar enviar referencia a la puerta de enlace</strong>, indica que el tronco admite la recepción de Solicitudes de referencia desde el Servidor de mediación.</p>
<p>Si está establecido como <strong>Habilitar la referencia mediante un control de llamadas de terceros</strong>, indica que el protocolo 3pcc puede ser utilizado para permitir llamadas transferidas para desviar el sitio hospedado. 3pcc también se conoce como &quot;control de terceros&quot; y se produce cuando se usa un tercero para conectar un par de llamadores (por ejemplo, un operador que realiza una llamada de la persona a a la persona B).</p></td>
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


<div>


> [!NOTE]  
> Los cmdlets de Lync Server CsTrunkConfiguration admiten propiedades adicionales que no se muestran en el panel de control de Lync Server. Para obtener más información, consulte el tema de ayuda del cmdlet <A href="https://docs.microsoft.com/powershell/module/skype/New-CsTrunkConfiguration">New-CsTrunkConfiguration</A> .



</div>

<div>

## <a name="to-create-new-trunk-configuration-settings-by-using-lync-server-control-panel"></a>Para crear nuevas opciones de configuración de tronco con el panel de control de Lync Server

1.  En el panel de control de Lync Server, haga clic en **enrutamiento de voz**y, a continuación, en **configuración de tronco**.

2.  En la pestaña **Configuración de tronco**, haga clic en **Nuevo** y luego haga clic en **Tronco de sitio** para crear el nuevo parámetro en el ámbito del sitio o en **Tronco de grupo** para crear el nuevo parámetro en el ámbito del servicio.

3.  En el cuadro de diálogo **Seleccionar un sitio** o **Seleccionar un servicio** (el cuadro de diálogo que aparece depende de si va a crear parámetros de ámbito de sitio o ámbito de servicio) seleccione la ubicación para los nuevos parámetros de configuración y luego haga clic en **Aceptar**. Si el cuadro de diálogo está en blanco, significa que no hay lugar para crear los nuevos parámetros; por ejemplo, si el cuadro de diálogo **Seleccionar un sitio** está en blanco significa que todos los sitios ya se han asignado una colección de sitios de configuración del tronco y cada sitio (y cada servicio) solo puede alojar una de esas colecciones. En ese caso, puede eliminar la colección existente y crear una nueva o simplemente cambiar la colección existente.

4.  En el cuadro de diálogo **Nueva configuración de tronco**, relacione las selecciones adecuadas y haga clic en **Aceptar**.

5.  La propiedad **Estado** de la colección se actualizará a **No confirmado**. Para confirmar los cambios y eliminar la colección, haga clic en **Confirmar** y luego en **Confirmar todo**.

6.  En el cuadro de diálogo **Configuración de voz sin confirmar**, haga clic en **Aceptar**.

7.  En el cuadro de diálogo **Panel de control de Microsoft Lync Server 2013**, haga clic en **Aceptar**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

