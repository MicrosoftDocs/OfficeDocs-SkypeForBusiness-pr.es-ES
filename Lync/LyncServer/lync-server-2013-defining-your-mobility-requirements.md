---
title: 'Lync Server 2013: Definir los requisitos de movilidad'
TOCTitle: Definir los requisitos de movilidad
ms:assetid: b7608335-cdeb-4aae-8e4b-d80c55f0d62b
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Hh690039(v=OCS.15)
ms:contentKeyID: 48276459
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Definir los requisitos de movilidad para Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

Durante la fase de planeación de la característica de movilidad de Lync Server 2013 en clientes de Lync 2010 Mobile Mobile y Lync 2013, debe tomar decisiones que marquen los pasos de la implementación.

Estos son los aspectos sobre los que deberá tomar una decisión:

  - **¿Quiere usar la detección automática para los clientes móviles de Lync?**
    
    Si desea admitir la detección automática, debe crear registros internos y externos del Sistema de nombres de dominio (DNS), agregar nombres alternativos del firmante a los certificados en los Servidores front-end, los Directores y el proxy inverso y modificar las reglas de publicación existentes en el proxy inverso. Para más información, vea [Requisitos técnicos para la movilidad en Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md). Con la detección automática, los usuarios pueden localizar automáticamente los servicios web de Lync Server 2013 desde cualquier parte, ya sea dentro o fuera de la red corporativa, sin escribir direcciones URL en los parámetros del dispositivo móvil.
    
    Si usa parámetros manuales en lugar de la detección automática, los usuarios móviles deberán escribir manualmente las siguientes direcciones URL en su dispositivo móvil:
    
      - https://\<FQDNGrupoExt\>/Autodiscover/autodiscoverservice.svc/Raíz para acceso externo
    
      - https://\<FQDNGrupoInt\>/AutoDiscover/ autodiscoverservice.svc/Raíz para acceso interno
    
    Recomendamos usar la detección automática. El principal uso de los parámetros manuales es para solucionar problemas.

  - **Si decide admitir la detección automática, ¿está dispuesto a actualizar los certificados en el proxy inverso con nombres alternativos del firmante para cada dominio SIP?**
    
    Si tiene muchos dominios SIP, actualizar los certificados públicos en el proxy inverso puede resultar muy costoso. Si es así, puede optar por implementar la detección automática de modo que la solicitud inicial del servicio de detección automática use HTTP en el puerto 80, en lugar de usar HTTPS en el puerto 443. Con todo, este no es el método recomendado. Si se decanta por esta alternativa, no necesitará actualizar los certificados en el proxy inverso, pero tendrá que crear una regla de publicación web para HTTP en el puerto 80. Para más información, vea [Requisitos técnicos para la movilidad en Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md).

  - **¿Desea admitir clientes móviles de Lync internos y externos a la red corporativa, o admitir solamente clientes dentro de la red corporativa?**
    
    Si desea admitir clientes móviles internos y externos a la red corporativa, los dispositivos móviles pueden tener acceso a las características de movilidad desde cualquier ubicación. La configuración predeterminada es admitir clientes internos y externos a la red corporativa.
    
    Aunque la configuración predeterminada permite que el tráfico del cliente móvil circule a través del sitio externo, puede limitar el tráfico del cliente móvil a la red corporativa interna. Al restringir el tráfico a la red corporativa interna, los usuarios pueden usar aplicaciones móviles de Lync en sus dispositivos móviles solo cuando estén dentro de la red.
    
    En aquellas implementaciones que admiten movilidad por medio del servicio de movilidad Mcx y Lync 2010 Mobile, se debe ejecutar el cmdlet **Set-CsMcxConfiguration**. Para configurar la movilidad para uso interno únicamente, usaríamos un comando parecido al siguiente:
    
        Set-CsMcxConfiguration -Identity site:Redmond -ExposedWebURL Internal
    

    > [!NOTE]
    > No se necesita ninguna configuración más para UCWA. UCWA carece de una configuración solo para uso interno equivalente.

    
    > [!IMPORTANT]  
    > Si usa un Servidor front-end o Grupos de servidores front-end de Lync Server 2013, y <strong>no tiene</strong>Servidores front-end ni Grupos de servidores front-end de Lync Server 2010, <strong>no existe ningún requisito para la persistencia basada en cookies</strong>. Si necesita conservar los Servidores front-end o Grupos de servidores front-end de Lync Server 2010, siguen siendo válidas las mismas reglas que en Lync Server 2010 para la persistencia basada en cookies.
    


  - **¿Desea admitir las notificaciones de inserción para dispositivos Apple iOS y Windows Phone?**
    
    Si admite las notificaciones de inserción, los dispositivos Apple iOS y Windows Phone admitidos reciben una notificación sobre los eventos que ocurren cuando la aplicación móvil está inactiva. Debe configurar el Servidor perimetral para tener una relación de federación con el servicio de notificaciones de inserción basado en la nube de Lync Server, que se encuentra en el Centro de datos de Lync Online, y ejecutar un cmdlet para habilitar las notificaciones de inserción.
    
    Si desea admitir las notificaciones de inserción a través de la red Wi-Fi, además de admitir las notificaciones de inserción a través de redes de datos o 3G de proveedores de dispositivos móviles, debe abrir el puerto 5223 en la red Wi-Fi de su empresa. El uso de notificaciones de inserción a través de la red Wi-Fi es compatible con dispositivos móviles que usan solo Wi-Fi y dispositivos móviles que tienen una recepción débil en interiores.
    
    > [!IMPORTANT]  
    > Abrir el puerto TCP 5223 solo es necesario para admitir dispositivos Apple que ejecutan el cliente Lync 2010 Mobile.
    
    
    Si no desea admitir las notificaciones de inserción, los usuarios de dispositivos móviles Apple o Windows Phone no recibirán información sobre los eventos (como invitaciones por mensajes instantáneos o mensajes perdidos) que ocurren cuando la aplicación móvil está inactiva.
    

    > [!NOTE]
    > Los clientes de Lync 2013 Mobile en dispositivos Apple no precisan de notificaciones de inserción. Los clientes de Lync 2013 Mobile en Windows Phone usan notificaciones de inserción. La planeación de las notificaciones de inserción y del centro de enrutamiento de notificaciones de inserción es la misma para Lync Mobile en dispositivos de Windows Phone y de Apple que no pueden ejecutar el cliente móvil de Lync 2013.



  - **¿Desea que todos los usuarios tengan acceso a las características de movilidad o desea especificar qué usuarios tendrán acceso a estas características?**
    
    En esta tabla se recogen las características disponibles para los usuarios en Lync Server 2013. De forma predeterminada, se permite Vía trabajo, voz sobre IP (VoIP) y la movilidad. A continuación detallamos el conjunto completo de opciones disponibles:
    
    
    <table>
    <colgroup>
    <col style="width: 33%" />
    <col style="width: 33%" />
    <col style="width: 33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>Característica/Nombre de parámetro/Ámbito (los nombres de parámetro de directiva pueden variar)</th>
    <th>Descripción</th>
    <th>Aparición</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>Permitir movilidad</p>
    <p>Nombre del parámetro: <code>EnableMobility</code></p>
    <p>Ámbito: Global/Sitio/Usuario</p></td>
    <td><p>Opción administrativa que controla los usuarios en un ámbito determinado que tienen Lync Mobile instalado. Si la directiva está establecida en False, el usuario no podrá iniciar sesión en el cliente.</p>
    <p>La configuración predeterminada es True.</p></td>
    <td><p>Actualización acumulativa para Lync Server 2010: noviembre 2011</p></td>
    </tr>
    <tr class="even">
    <td><p>Permitir voz externa</p>
    <p>Nombre de parámetro: <code>EnableOutsideVoice</code></p>
    <p>Ámbito: Global/Sitio/Usuario</p></td>
    <td><p>Controla la capacidad de un usuario para usar Vía trabajo, una característica con la que los usuarios pueden efectuar y recibir llamadas a través de su número de teléfono del trabajo, en lugar de su número de teléfono móvil. Si se establece en False, no se podrán realizar ni recibir llamadas con el número de teléfono del trabajo desde el dispositivo móvil.</p>
    <p>La configuración predeterminada es True.</p></td>
    <td><p>Actualización acumulativa para Lync Server 2010: noviembre 2011</p></td>
    </tr>
    <tr class="odd">
    <td><p>Permitir Audio y vídeo IP</p>
    <p>Nombre de parámetro: <code>EnableIPAudioVideo</code></p>
    <p>Ámbito: Global/Sitio/Usuario</p></td>
    <td><p>Controla si un usuario puede usar VoIP para realizar o recibir llamadas de voz o de vídeo en su dispositivo móvil. Si se establece en False, no se podrán realizar ni recibir llamadas de VoIP o vídeo en el dispositivo móvil.</p>
    <p>La configuración predeterminada es True.</p></td>
    <td><p>Microsoft Lync Server 2013</p></td>
    </tr>
    <tr class="even">
    <td><p>Requerir Wi-Fi para audio IP</p>
    <p>Nombre de parámetro: <code>RequireWiFiForIPAudio</code></p>
    <p>Ámbito: Global/Sitio/Usuario</p></td>
    <td><p>Esta opción define si el cliente deberá realizar y recibir llamadas mediante VoIP por Wi-Fi en lugar de por la red de datos de telefonía móvil. Si se establece en True, solo se podrán realizar y recibir llamadas de VoIP cuando se establezca una conexión con una red Wi-Fi.</p>
    <p>La configuración predeterminada es False.</p></td>
    <td><p>Microsoft Lync Server 2013</p></td>
    </tr>
    <tr class="odd">
    <td><p>Requerir Wi-Fi para vídeo IP</p>
    <p>Nombre de parámetro: <code>RequireWiFiForIPVideo</code></p>
    <p>Ámbito: Global/Sitio/Usuario</p></td>
    <td><p>Esta opción define si el cliente deberá realizar y recibir llamadas de vídeo por Wi-Fi en lugar de por la red de datos de telefonía móvil. Si se establece en True, solo se podrán realizar y recibir llamadas de vídeo cuando se establezca una conexión con una red Wi-Fi.</p>
    <p>La configuración predeterminada es False.</p></td>
    <td><p>Microsoft Lync Server 2013</p></td>
    </tr>
    </tbody>
    </table>
    
    Para ver una descripción de las configuraciones de directiva que se pueden establecer, así como el modo de administrar directivas, vea [New-CsMobilityPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsMobilityPolicy), [Set-CsMobilityPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsMobilityPolicy), [Get-CsMobilityPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsMobilityPolicy), [Grant-CsMobilityPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsMobilityPolicy) y [Remove-CsMobilityPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsMobilityPolicy).

  - **¿Desea que los usuarios no habilitados para Telefonía IP empresarial puedan hacer clic para unirse a conferencias?**
    
    Para que los usuarios puedan tener acceso a las características de movilidad y Vía trabajo, deben estar habilitados para Telefonía IP empresarial. Sin embargo, los usuarios que no están habilitados para Telefonía IP empresarial, pueden unirse a conferencias haciendo clic en el vínculo de su dispositivo móvil si se les ha asignado una directiva de voz apropiada. Puede asignar una directiva de voz específica para estos usuarios o procurar que haya una directiva global o de nivel de sitio que se aplique a ellos. La directiva de voz que asigne debe tener registros de uso de la red telefónica conmutada (RTC) y rutas que definan las áreas a las que los usuarios pueden marcar para unirse a una conferencia. Para más información sobre la configuración de la directiva de voz, los registros de uso de RTC y las rutas, vea [Configuración de directivas de voz, registros de uso de RTC y rutas de voz en Lync Server 2013](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md).
    

    > [!NOTE]
    > Los usuarios móviles que deseen hacer clic para unirse a conferencias necesitan una directiva de voz, junto con los registros de uso de RTC y las rutas de voz relacionados, porque se genera una llamada saliente desde Lync Server 2013 al hacer clic en el vínculo del dispositivo móvil.



## Vea también

#### Conceptos

[Requisitos técnicos para la movilidad en Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md)  

#### Otros recursos

[Configuración de directivas de voz, registros de uso de RTC y rutas de voz en Lync Server 2013](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md)

