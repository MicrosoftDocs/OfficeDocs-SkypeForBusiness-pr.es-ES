---
title: 'Lync Server 2013: Información general sobre el control de admisión de llamadas'
TOCTitle: Información general sobre el control de admisión de llamadas
ms:assetid: 6fda0195-4c89-4dea-82e8-624f03e3d062
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398529(v=OCS.15)
ms:contentKeyID: 48275642
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Información general sobre el control de admisión de llamadas en Lync Server 2013

 

_**Última modificación del tema:** 2012-09-22_

Las comunicaciones en tiempo real son sensibles a la latencia y la pérdida de paquetes que pueden producirse en las redes congestionadas. El control de admisión de llamadas (CAC) determina, en base al ancho de banda de la red disponible, si está permitido establecer sesiones de comunicación en tiempo real, como son las llamadas de voz o vídeo. El diseño del CAC de Lync Server 2013 ofrece cuatro atributos principales:

  - Es fácil de implementar y administrar, y no requiere equipamiento adicional, como ocurre con los enrutadores especialmente configurados.

  - Está dirigido a casos de uso de comunicaciones unificadas críticas, como los escenarios con usuarios remotos o múltiples puntos de presencia. Las directivas del CAC se aplican de acuerdo con el lugar donde se ubica el extremo, no con el lugar donde se hospeda el usuario.

  - Además de las llamadas de voz, puede aplicarse a otro tráfico, como las videollamadas y las sesiones de conferencia de audio/vídeo.

  - Proporciona la flexibilidad necesaria para habilitar la representación de varios tipos de topologías de red. Para ver ejemplos, consulte [Componentes y topologías para CAC en Lync Server 2013](lync-server-2013-components-and-topologies-for-cac.md).

Si una sesión de vídeo o voz nueva supera los límites de ancho de banda que se han establecido en un vínculo WAN, la sesión se bloquea o (solo para llamadas telefónicas) se desvía al RTC.

El CAC controla el tráfico en tiempo real solo para voz y vídeo. No controla el tráfico de datos.

Los administradores definen las directivas del CAC, que aplica el servicio de directivas de ancho de banda que hay instalado en cada uno de los Grupo de servidores front-end. La configuración del CAC se propaga automáticamente a todos los Servidores front-end de Lync Server de la red.

Para las llamadas en las que se produce un error debido a las directivas del CAC, el orden de prioridad para desviar la llamada es el siguiente:

1.  Internet

2.  RTC

3.  Correo de voz

Información de las capturas del registro de detalles de llamadas (CDR) acerca de las llamadas que se desvían al RTC o al correo de voz. El CDR no captura información acerca de las llamadas que se desvían a Internet, ya que Internet se considera una ruta alternativa en lugar de una opción secundaria.


> [!NOTE]
> Los depósitos de correo de voz no se denegarán por restricciones del ancho de banda.



El servicio de directivas de ancho de banda genera dos tipos de archivo de registro en formato de valores separados por comas (CSV). El archivo de registro de **errores de comprobación** captura información cuando se deniegan las solicitudes de ancho de banda. El archivo de registro de **uso de vínculos** captura una instantánea de la topología de red y del uso del ancho de banda del vínculo WAN. Estos dos archivos de registro pueden ayudarle a ajustar las directivas del CAC en base al uso.

## Consideraciones relacionadas con el control de admisión de llamadas

El administrador elige instalar el Servicio de directiva de ancho de banda en el primer grupo de servidores configurado en la ubicación central. Dado que hay una única ubicación central por región de red, solo hay un servicio de directivas de ancho de banda en cada región de red, que gestiona la directiva de ancho de banda para dicha región, sus sitios asociados y los vínculos a esos sitios. El servicio de directivas de ancho de banda se ejecuta como parte de los Servidores front-end, y por tanto la alta disponibilidad está integrada dentro de ese grupo de servidores. El servicio de directivas de ancho de banda que se ejecuta en cada Servidor front-end se sincroniza cada 15 segundos. Si falla el Grupo de servidores front-end, las directivas de CAC ya no se imponen para dicho sitio hasta que el Grupo de servidores front-end y, por consiguiente, el servicio de directivas de ancho de banda vuelven a estar operativos. Esto implica que todas las llamadas pasarán mientras el servicio de directivas de ancho de banda esté fuera de servicio. Por tanto, existe la posibilidad de saturación del ancho de banda de los enlaces durante este período.

El servicio de directivas de ancho de banda proporciona alta disponibilidad dentro de un Grupo de servidores front-end; sin embargo, no proporciona redundancia entre Grupos de servidores front-end. El servicio de directivas de ancho de banda no puede conmutar por error de un Grupo de servidores front-end a otro. Una vez restaurado el servicio al Grupo de servidores front-end, el servicio de directivas de ancho de banda se reanuda y puede imponer de nuevo la directiva de ancho de banda.

## Consideraciones relacionadas con la red

Aunque el servicio de directivas de ancho de banda aplica la restricción de ancho de banda al audio y al vídeo en Lync Server 2013, esta restricción no se aplica en el enrutador de red (nivel 2 y 3). El CAC de Lync Server 2010 no puede evitar que una aplicación de datos, por ejemplo, consuma todo el ancho de banda de la red con un vínculo WAN, incluido el ancho de banda que la directiva del CAC reserva para el audio y el vídeo. Para proteger el ancho de banda necesario en su red, puede implementar un protocolo de Calidad de servicio (QoS) como, por ejemplo, los servicios diferenciados (DiffServ). Así pues, el procedimiento recomendado es coordinar las directivas de ancho de banda del CAC que defina con cualquier configuración de QoS que pueda implementar.

## Rutas de señalización y medios sobre VPN

Si su empresa admite medios a través de VPN, asegúrese de que tanto la secuencia de medios como la secuencia de señalización pasan por la VPN o están enrutadas a través de Internet. De forma predeterminada, las secuencias de medios y de señalización pasan por el túnel VPN.

## Control de admisión de llamadas de usuarios externos

El servicio de control de admisión de llamadas no se aplica a usuarios remotos cuando el tráfico de red fluye a través de Internet. Como el tráfico de medios pasa por Internet, y este no está administrado por Lync Server, no puede aplicarse el CAC. No obstante, se llevarán a cabo comprobaciones de CAC en la parte de la llamada que fluya a través de la red de la empresa.

## Control de admisión de llamadas de conexiones RTC

El servicio de control de admisión de llamadas es aplicable en el Servidor de mediación, independientemente de si está conectado a un sistema IP/PBX, a una puerta de enlace RTC o a un tronco SIP. Como el Servidor de mediación es un agente de usuario opuesto (B2BUA), finaliza los medios. Tiene dos lados de conexión: un lado conectado a Lync Server y un lado de puerta de enlace, que está conectado a puertas de enlace RTC, sistemas IP/PBX o troncos SIP. Para más información sobre las conexiones RTC, consulte [Planeación de la conectividad con RTC en Lync Server 2013](lync-server-2013-planning-for-pstn-connectivity.md).

El CAC puede aplicarse a ambos lados del Servidor de mediación, a menos que el desvío de medios esté habilitado. Si está habilitado, el tráfico de medios no pasará por el Servidor de mediación, sino que fluirá directamente entre el cliente de Lync y la puerta de enlace. En este caso, el CAC no es necesario. Para más información, consulte [Planificar la omisión de medios en Lync Server 2013](lync-server-2013-planning-for-media-bypass.md).

En la siguiente figura se muestra cómo se aplica el CAC a las conexiones RTC con el desvío de medios habilitado e inhabilitado.

**Aplicación del control de admisión de llamadas en conexiones al RTC**

![Aplicación de la conexión de desvío de medios del control de admisión de llamadas de voz](images/Gg398703.4d66d529-0912-4de1-abec-266f54272eb3(OCS.15).jpg "Aplicación de la conexión de desvío de medios del control de admisión de llamadas de voz")

## Compatibilidad del control de admisión de llamadas con versiones anteriores de Office Communications Server

El servicio de control de admisión de llamadas solo puede habilitarse en los extremos habilitados para Lync Server 2010 y versiones posteriores.

El control de admisión de llamadas no puede habilitarse en extremos que ejecutan Office Communicator 2007 R2 o anterior.

**Aplicación del CAC en diferentes versiones de Lync Server**

![Diagrama de comparación de versiones del control de admisión de llamadas de voz](images/Gg398529.fdbfee7e-15fc-445b-949d-8d61e61ac350(OCS.15).jpg "Diagrama de comparación de versiones del control de admisión de llamadas de voz")

