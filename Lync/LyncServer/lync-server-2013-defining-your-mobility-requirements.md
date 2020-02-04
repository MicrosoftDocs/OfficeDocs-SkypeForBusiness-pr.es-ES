---
title: 'Lync Server 2013: Definir los requisitos de movilidad'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining your mobility requirements
ms:assetid: b7608335-cdeb-4aae-8e4b-d80c55f0d62b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690039(v=OCS.15)
ms:contentKeyID: 48185226
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2721f88ce703fe4c26fbc7a9a6cd02cdde6b14a8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762758"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-your-mobility-requirements-for-lync-server-2013"></a>Definir los requisitos de movilidad para Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-14_

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

Durante la fase de planeación de la característica de movilidad de Lync Server 2013, cuando usa Lync 2010 Mobile y los clientes móviles de Lync 2013, toma decisiones que determinen los pasos de implementación.

Estas son las decisiones que debe considerar:

  - **¿Desea usar el descubrimiento automático para clientes móviles de Lync?**
    
    Si desea admitir el descubrimiento automático, necesita crear nuevos registros internos y externos del sistema de nombres de dominio (DNS), agregar nombres alternativos de asunto a los certificados de los servidores front-end, directores y proxy inverso, y modificar las reglas de publicación existentes. en el proxy inverso. Para obtener más información, consulte [requisitos técnicos para la movilidad en Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md). Con el descubrimiento automático, los usuarios pueden ubicar automáticamente los servicios Web de Lync Server 2013 desde cualquier lugar dentro o fuera de la red corporativa, sin tener que escribir las direcciones URL en la configuración de su dispositivo móvil.
    
    Si usa la configuración manual en lugar del descubrimiento automático, los usuarios móviles deberán introducir manualmente las siguientes direcciones URL en sus dispositivos móviles:
    
      - https://\<ExtPoolFQDN\>/Autodiscover/autodiscoverservice.SVC/root para acceso externo
    
      - https://\<IntPoolFQDN\>/AutoDiscover/Autodiscoverservice. SVC/root para acceso interno
    
    Se recomienda usar el descubrimiento automático. El uso principal de la configuración manual es para la solución de problemas.

  - **Si decide admitir el descubrimiento automático, ¿está dispuesto a actualizar los certificados en el proxy inverso con nombres alternativos de asunto para cada dominio SIP?**
    
    Si tiene muchos dominios SIP, la actualización de certificados públicos en el proxy inverso puede resultar muy costosa. Si este es el caso, puede optar por implementar el descubrimiento automático para que la solicitud del servicio de detección automática inicial use HTTP en el puerto 80, en lugar de usar HTTPS en el puerto 443. Sin embargo, este enfoque no es el recomendado. Si decide elegir esta alternativa, no es necesario actualizar los certificados en el proxy inverso, pero debe crear una regla de publicación web para HTTP en el puerto 80. Para obtener más información, consulte [requisitos técnicos para la movilidad en Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md).

  - **¿Quiere admitir clientes móviles de Lync internos y externos en la red corporativa o solo admite clientes dentro de la red corporativa?**
    
    Si desea admitir clientes móviles internos y externos a la red, los dispositivos móviles pueden acceder a las características de movilidad desde cualquier ubicación. La configuración predeterminada es admitir clientes internos y externos a la red corporativa.
    
    Aunque la configuración predeterminada permite que el tráfico de los clientes móviles pase por el sitio externo, puede restringir el tráfico de los clientes móviles a la red corporativa interna. Al restringir el tráfico a la red interna, los usuarios pueden usar las aplicaciones móviles de Lync en sus dispositivos móviles solo cuando se encuentren dentro de la red.
    
    Para las implementaciones que admiten movilidad con el servicio de movilidad de MCX y Lync 2010 Mobile, ejecute el cmdlet **set-CsMcxConfiguration** . Para establecer la movilidad solo para uso interno, usaría un comando similar al siguiente:
    
        Set-CsMcxConfiguration -Identity site:Redmond -ExposedWebURL Internal
    
    <div>
    

    > [!NOTE]  
    > No es necesario realizar ninguna configuración adicional para UCWA. UCWA no tiene una configuración de solo interno equivalente.

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > Si usa un servidor front-end de&nbsp;lync Server 2013 o agrupaciones front end y <STRONG>no tiene</STRONG> servidores front-end de&nbsp;Lync Server 2010 o grupos front-end, no hay <STRONG>necesidad de persistencia basada en cookies</STRONG>. Si necesita conservar los servidores front-end de&nbsp;lync Server 2010 o las agrupaciones front end, se siguen aplicando las mismas reglas de lync Server 2010 para la persistencia basada en cookies.

    
    </div>

  - **¿Deseas admitir las notificaciones de inserción para dispositivos iOS de Apple y teléfonos con Windows?**
    
    Si admite las notificaciones de inserción, los dispositivos Apple iOS y los teléfonos Windows compatibles reciben una notificación de eventos que se producen cuando la aplicación móvil no está activa. Debe configurar el servidor perimetral para que tenga una relación de Federación con el servicio de notificaciones de inserción de Lync Server basado en la nube, que se encuentra en el centro de administración de Lync Online, y ejecutar un cmdlet para habilitar las notificaciones de inserción.
    
    Si desea admitir notificaciones de inserción sobre su red Wi-Fi, además de admitir notificaciones de inserción a través de redes de datos o 3G de proveedores de dispositivos móviles, debe abrir el puerto 5223 de salida en su red Wi-Fi de su empresa. La compatibilidad con las notificaciones de inserción en la red Wi-Fi es compatible con dispositivos móviles que usan solo dispositivos Wi-Fi y móviles que tienen una mala cobertura interior.
    
    <div>
    

    > [!IMPORTANT]  
    > El puerto de apertura TCP 5223 solo es necesario cuando se admiten dispositivos Apple que ejecuten el cliente móvil Lync 2010.

    
    </div>
    
    Si no admite las notificaciones de inserción, los usuarios de dispositivos móviles de Apple y Windows Phone no averiguarán los eventos, como las invitaciones de mensajería instantánea o los mensajes perdidos, que se producen cuando la aplicación móvil está inactiva.
    
    <div>
    

    > [!NOTE]  
    > Los clientes móviles de Lync 2013 en dispositivos Apple no requieren una notificación push. Los clientes móviles de Lync 2013 en Windows Phone usan notificaciones Push. La planificación de la notificación de inserción y el centro de notificaciones push siguen siendo los mismos para Lync Mobile en Windows Phone y los dispositivos Apple que no pueden ejecutar el cliente móvil Lync 2013.

    
    </div>

  - **¿Desea que todos los usuarios tengan acceso a las características de movilidad o desea poder especificar los usuarios que tienen acceso a estas características?**
    
    En la tabla se describen las características disponibles para los usuarios en Lync Server 2013. Los valores predeterminados permiten llamar a través del trabajo, permitir voz sobre IP (VoIP) y habilitar la movilidad. Este es el conjunto completo de opciones disponibles:
    
    
    <table>
    <colgroup>
    <col style="width: 33%" />
    <col style="width: 33%" />
    <col style="width: 33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>Nombre o ámbito de la característica/parámetro (los nombres de parámetro de Directiva pueden no ser iguales)</th>
    <th>Descripción</th>
    <th>Adoptado</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>Permitir movilidad</p>
    <p>Nombre del parámetro:<code>EnableMobility</code></p>
    <p>Ámbito: global/sitio/usuario</p></td>
    <td><p>Configuración administrativa para controlar los usuarios de un ámbito dado que tienen instalado Lync Mobile, si la Directiva se establece en false, el usuario no podrá iniciar sesión en el cliente.</p>
    <p>El valor predeterminado es true.</p></td>
    <td><p>Actualización acumulativa para Lync Server 2010:2011 de noviembre</p></td>
    </tr>
    <tr class="even">
    <td><p>Habilitar voz externa</p>
    <p>Nombre del parámetro:<code>EnableOutsideVoice</code></p>
    <p>Ámbito: global/sitio/usuario</p></td>
    <td><p>Controla la capacidad de un usuario para usar las llamadas a través del trabajo, una característica que permite a los usuarios realizar y recibir llamadas con su número del trabajo en lugar de con su número de teléfono móvil. Si se establece en falso, el usuario no podrá realizar ni recibir llamadas a través de su número de trabajo desde su dispositivo móvil.</p>
    <p>La configuración predeterminada es verdadero</p></td>
    <td><p>Actualización acumulativa para Lync Server 2010:2011 de noviembre</p></td>
    </tr>
    <tr class="odd">
    <td><p>Permitir Audio y vídeo IP</p>
    <p>Nombre del parámetro:<code>EnableIPAudioVideo</code></p>
    <p>Ámbito: global/sitio/usuario</p></td>
    <td><p>Controla si un usuario puede usar VoIP para hacer o recibir llamadas o videollamadas en su dispositivo móvil. Si se establece en falso, el usuario no podrá hacer ni recibir llamadas de VoIP o de vídeo en su dispositivo.</p>
    <p>El valor predeterminado es true.</p></td>
    <td><p>Microsoft Lync Server 2013</p></td>
    </tr>
    <tr class="even">
    <td><p>Requerir Wi-Fi para audio IP</p>
    <p>Nombre del parámetro:<code>RequireWiFiForIPAudio</code></p>
    <p>Ámbito: global/sitio/usuario</p></td>
    <td><p>Esta configuración define si el cliente tendrá que realizar y recibir llamadas a través de VoIP en WiFi en lugar de la red de datos de telefonía móvil. Si se establece en true, el usuario podrá hacer y recibir llamadas de VoIP solo cuando esté conectado a una red WiFi.</p>
    <p>El valor predeterminado es falso.</p></td>
    <td><p>Microsoft Lync Server 2013</p></td>
    </tr>
    <tr class="odd">
    <td><p>Requerir Wi-Fi para vídeo IP</p>
    <p>Nombre del parámetro:<code>RequireWiFiForIPVideo</code></p>
    <p>Ámbito: global/sitio/usuario</p></td>
    <td><p>Esta configuración define si el cliente tendrá que realizar y recibir videollamadas en Wi-Fi en lugar de hacerlo en la red de datos de telefonía móvil. Si se establece en true, el usuario podrá hacer y recibir videollamadas solo cuando esté conectado a una red Wi-Fi.</p>
    <p>El valor predeterminado es falso.</p></td>
    <td><p>Microsoft Lync Server 2013</p></td>
    </tr>
    </tbody>
    </table>
    
    Para obtener una descripción de la configuración de la Directiva que puede configurar y sobre cómo administrar las directivas, consulte [New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy), [set-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsMobilityPolicy), [Get-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsMobilityPolicy), [Grant-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsMobilityPolicy) y [Remove-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsMobilityPolicy).

  - **¿Quiere que los usuarios que no tienen habilitada la telefonía IP empresarial puedan usar hacer clic para unirse a conferencias?**
    
    Para que los usuarios tengan acceso a las características de movilidad y llamar por trabajo, deben estar habilitadas para telefonía IP empresarial. Sin embargo, los usuarios que no tienen habilitada la telefonía IP empresarial pueden unirse a las conferencias haciendo clic en el vínculo de su dispositivo móvil, siempre que tengan asignada una directiva de voz adecuada. Puede asignar una directiva de voz específica a estos usuarios o asegurarse de que exista una directiva global o una directiva de nivel de sitio que les apliquen. La Directiva de voz que asigne debe tener registros de uso y rutas de red de telefonía pública conmutada (RTC) que definan las áreas a las que los usuarios pueden llamar para unirse a una conferencia. Para obtener más información sobre cómo configurar la Directiva de voz, los registros de uso de RTC y las rutas, consulte [configuración de directivas de voz, registros de uso de RTC y rutas de voz en Lync Server 2013](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md).
    
    <div>
    

    > [!NOTE]  
    > Los usuarios móviles que deseen usar hacer clic para participar requieren una directiva de voz, junto con los registros de uso de RTC y las rutas de voz relacionados, porque al hacer clic en el vínculo en el dispositivo móvil se produce una llamada saliente desde Lync Server 2013.

    
    </div>

<div>

## <a name="see-also"></a>Vea también


[Requisitos técnicos para la movilidad en Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md)  


[Configuración de directivas de voz, registros de uso de RTC y rutas de voz en Lync Server 2013](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

