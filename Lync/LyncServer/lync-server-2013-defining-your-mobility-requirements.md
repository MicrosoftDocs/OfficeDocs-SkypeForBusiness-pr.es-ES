---
title: 'Lync Server 2013: definición de los requisitos de movilidad'
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
ms.openlocfilehash: 2da630e422aaf7068a4252333d5221f552bce525
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42198353"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="defining-your-mobility-requirements-for-lync-server-2013"></a>Definición de los requisitos de movilidad para Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-14_

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

Durante la fase de planeación de la característica de movilidad de Lync Server 2013, cuando se usan clientes móviles de Lync 2010 Mobile y Lync 2013, se toman decisiones que determinan los pasos de implementación.

Estas son las decisiones que debe tener en cuenta:

  - **¿Quiere usar la detección automática para clientes móviles de Lync?**
    
    Si desea admitir la detección automática, debe crear nuevos registros internos y externos del sistema de nombres de dominio (DNS), agregar nombres alternativos del sujeto a certificados en los servidores front-end, directores y proxy inverso, y modificar las reglas de publicación existentes. en el proxy inverso. Para obtener más información, consulte [Technical Requirements for Mobility in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md). Con la detección automática, los usuarios pueden ubicar automáticamente los servicios Web de Lync Server 2013 desde cualquier lugar dentro o fuera de la red corporativa, sin especificar las direcciones URL en la configuración del dispositivo móvil.
    
    Si usa la configuración manual en lugar de la detección automática, los usuarios móviles deben especificar manualmente las siguientes direcciones URL en sus dispositivos móviles:
    
      - https://\<ExtPoolFQDN\>/Autodiscover/autodiscoverservice.SVC/root para acceso externo
    
      - https://\<IntPoolFQDN\>/AutoDiscover/Autodiscoverservice. SVC/root para acceso interno
    
    Se recomienda encarecidamente usar la detección automática. El uso principal de los parámetros manuales es para solucionar problemas.

  - **Si decide admitir la detección automática, ¿está dispuesto a actualizar certificados en el proxy inverso con nombres alternativos de sujeto para cada dominio SIP?**
    
    Si tiene muchos dominios SIP, actualizar certificados públicos en el proxy inverso puede resultar muy caro. Si este es el caso, puede optar por implementar la detección automática para que la solicitud del servicio Detección automática inicial use HTTP en el puerto 80, en lugar de usar HTTPS en el puerto 443. Sin embargo, no se trata del método recomendado. Si decide elegir esta alternativa, no necesita actualizar los certificados en el proxy inverso, pero debe crear una regla de publicación web para HTTP en el puerto 80. Para obtener más información, consulte [Technical Requirements for Mobility in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md).

  - **¿Desea admitir clientes móviles de Lync internos y externos a la red corporativa, o admitir solamente clientes internos de la red corporativa?**
    
    Si desea admitir clientes móviles internos y externos a la red corporativa, los dispositivos móviles pueden tener acceso a características de movilidad desde cualquier ubicación. La configuración predeterminada es admitir clientes internos y externos a la red corporativa.
    
    Aunque la configuración predeterminada permite que el tráfico del cliente móvil circule a través del sitio externo, puede restringir el tráfico del cliente móvil a la red corporativa interna. Al restringir el tráfico a la red corporativa interna, los usuarios pueden usar aplicaciones móviles de Lync en sus dispositivos móviles solo cuando están dentro de la red.
    
    Para las implementaciones que admiten movilidad con MCX Mobility Service y Lync 2010 Mobile, ejecute el cmdlet **set-CsMcxConfiguration** . Para establecer la movilidad solo para uso interno, debe usar un comando similar al siguiente:
    
        Set-CsMcxConfiguration -Identity site:Redmond -ExposedWebURL Internal
    
    <div>
    

    > [!NOTE]  
    > No es necesario realizar ninguna configuración adicional para UCWA. UCWA no tiene una configuración de solo interno equivalente.

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > Si usa un servidor front-end de&nbsp;lync Server 2013 o grupos de servidores front-end y <STRONG>no tiene</STRONG> servidores Front-&nbsp;end de Lync Server 2010 o grupos de servidores front-end, no hay <STRONG>ningún requisito para la persistencia basada en cookies</STRONG>. Si necesita conservar los servidores front-end de&nbsp;lync Server 2010 o los grupos de servidores front-end, se siguen aplicando las mismas reglas que en lync Server 2010 para la persistencia basada en cookies.

    
    </div>

  - **¿Desea admitir las notificaciones de inserción para dispositivos Apple iOS y Windows Phone?**
    
    Si admite notificaciones de inserción, los dispositivos Apple iOS y Windows Phone admitidos reciben una notificación de eventos que ocurren cuando la aplicación móvil está inactiva. Debe configurar el servidor perimetral para que tenga una relación de Federación con el servicio de notificación de inserción de Lync Server basado en la nube, que se encuentra en el centro de servicios de Lync Online, y ejecutar un cmdlet para habilitar las notificaciones de inserción.
    
    Si desea admitir notificaciones de inserción a través de la red Wi-Fi, además de admitir notificaciones de inserción a través de redes de datos o 3G de proveedores de dispositivos móviles, debe abrir el puerto 5223 de salida en la red Wi-Fi de su empresa. La admisión de notificaciones de inserción a través de la red Wi-Fi es compatible con dispositivos móviles que usan solo Wi-Fi y dispositivos móviles que tienen una recepción interior débil.
    
    <div>
    

    > [!IMPORTANT]  
    > La apertura del puerto TCP 5223 solo es necesaria cuando se admiten dispositivos Apple que ejecutan el cliente móvil de Lync 2010.

    
    </div>
    
    Si no admite las notificaciones de inserción, los usuarios de dispositivos móviles Apple y Windows Phone no obtendrán información sobre eventos, como invitaciones a mensajes instantáneos o mensajes perdidos, que se producen cuando la aplicación móvil está inactiva.
    
    <div>
    

    > [!NOTE]  
    > Los clientes móviles de Lync 2013 en dispositivos Apple no necesitan una notificación de inserción. Los clientes móviles de Lync 2013 en Windows Phone usan la notificación de inserción. La planeación de las notificaciones de inserción y el centro de notificaciones de inserción siguen siendo los mismos para Lync Mobile en Windows Phone y los dispositivos Apple que no pueden ejecutar el cliente móvil de Lync 2013.

    
    </div>

  - **¿Desea que todos los usuarios tengan acceso a las características de movilidad o desea poder especificar qué usuarios tienen acceso a estas características?**
    
    En la tabla se describen las características disponibles para los usuarios en Lync Server 2013. Los valores predeterminados permiten la llamada a través del trabajo, permiten la voz sobre IP (VoIP) y habilitan la movilidad. Este es el conjunto completo de opciones disponibles:
    
    
    <table>
    <colgroup>
    <col style="width: 33%" />
    <col style="width: 33%" />
    <col style="width: 33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>Nombre/ámbito de la característica/parámetro (los nombres de parámetro de Directiva pueden no ser los mismos)</th>
    <th>Descripción</th>
    <th>Agregado</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>Habilitar la movilidad</p>
    <p>Nombre del parámetro:<code>EnableMobility</code></p>
    <p>Ámbito: global, sitio o usuario</p></td>
    <td><p>Configuración administrativa para controlar a los usuarios de un ámbito determinado que tienen Lync Mobile instalado, si la Directiva se establece en false, el usuario no podrá iniciar sesión en el cliente.</p>
    <p>El valor predeterminado es True.</p></td>
    <td><p>Actualización acumulativa de Lync Server 2010:2011 de noviembre</p></td>
    </tr>
    <tr class="even">
    <td><p>Habilitar voz externa</p>
    <p>Nombre del parámetro:<code>EnableOutsideVoice</code></p>
    <p>Ámbito: global, sitio o usuario</p></td>
    <td><p>Controla la capacidad de un usuario de usar llamadas vía trabajo, una característica que permite a los usuarios realizar y recibir llamadas mediante su número de trabajo en lugar de su número de teléfono móvil. Si se establece en false, el usuario no podrá realizar o recibir llamadas a través de su número de trabajo desde su dispositivo móvil.</p>
    <p>El valor predeterminado es true.</p></td>
    <td><p>Actualización acumulativa de Lync Server 2010:2011 de noviembre</p></td>
    </tr>
    <tr class="odd">
    <td><p>Habilitar audio y vídeo IP</p>
    <p>Nombre del parámetro:<code>EnableIPAudioVideo</code></p>
    <p>Ámbito: global, sitio o usuario</p></td>
    <td><p>Controla si un usuario puede usar VoIP para realizar o recibir llamadas de voz o vídeo en su dispositivo móvil. Si se establece en false, el usuario no podrá realizar o recibir llamadas de VoIP o vídeo en su dispositivo.</p>
    <p>El valor predeterminado es True.</p></td>
    <td><p>Microsoft Lync Server 2013</p></td>
    </tr>
    <tr class="even">
    <td><p>Requerir Wi-Fi para audio IP</p>
    <p>Nombre del parámetro:<code>RequireWiFiForIPAudio</code></p>
    <p>Ámbito: global, sitio o usuario</p></td>
    <td><p>Esta configuración define si el cliente tendrá que realizar y recibir llamadas a través de VoIP en WiFi en lugar de hacerlo en la red de datos de telefonía móvil. Si se establece en true, el usuario solo puede realizar y recibir llamadas de VoIP cuando esté conectado a una red WiFi.</p>
    <p>El valor predeterminado es false.</p></td>
    <td><p>Microsoft Lync Server 2013</p></td>
    </tr>
    <tr class="odd">
    <td><p>Requerir Wi-Fi para vídeo IP</p>
    <p>Nombre del parámetro:<code>RequireWiFiForIPVideo</code></p>
    <p>Ámbito: global, sitio o usuario</p></td>
    <td><p>Esta configuración define si el cliente tendrá que realizar y recibir llamadas de vídeo en Wi-Fi en lugar de hacerlo en la red de datos de telefonía móvil. Si se establece en true, el usuario solo puede realizar y recibir llamadas de vídeo cuando esté conectado a una red Wi-Fi.</p>
    <p>El valor predeterminado es false.</p></td>
    <td><p>Microsoft Lync Server 2013</p></td>
    </tr>
    </tbody>
    </table>
    
    Para obtener una descripción de la configuración de la Directiva que puede configurar y cómo administrar las directivas, consulte [New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy), [set-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsMobilityPolicy), [Get-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsMobilityPolicy), [Grant-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsMobilityPolicy) y [Remove-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsMobilityPolicy).

  - **¿Desea que los usuarios no habilitados a Telefonía IP empresarial puedan usar Click to Join para unirse a conferencias?**
    
    Para que los usuarios puedan tener acceso a las características de movilidad y Vía trabajo, deben estar habilitados para Telefonía IP empresarial. Sin embargo, los usuarios que no están habilitados para telefonía IP empresarial pueden unirse a conferencias haciendo clic en el vínculo de su dispositivo móvil, si tienen asignada una directiva de voz adecuada. Puede asignar una directiva de voz específica a estos usuarios o asegurarse de que existe una directiva global o una directiva de nivel de sitio que se aplica a ellos. La Directiva de voz que asigne debe tener registros y rutas de uso de la red telefónica conmutada (RTC) que definen las áreas a las que los usuarios pueden llamar para unirse a una conferencia. Para obtener información detallada sobre cómo configurar la Directiva de voz, los registros de uso de RTC y las rutas, vea [configurar directivas de voz, registros de uso de RTC y rutas de voz en Lync Server 2013](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md).
    
    <div>
    

    > [!NOTE]  
    > Los usuarios móviles que quieren usar hacer clic para unirse requieren una directiva de voz, junto con los registros de uso de RTC y las rutas de voz relacionados, porque al hacer clic en el vínculo del dispositivo móvil se produce una llamada saliente desde Lync Server 2013.

    
    </div>

<div>

## <a name="see-also"></a>Consulta también


[Requisitos técnicos para la movilidad en Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md)  


[Configurar directivas de voz, registros de uso de RTC y rutas de voz en Lync Server 2013](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

