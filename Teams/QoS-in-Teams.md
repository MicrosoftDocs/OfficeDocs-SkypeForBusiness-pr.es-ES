---
title: Implementar Calidad de servicio en Microsoft Teams
author: rmw2890
ms.author: MyAdvisor
manager: Serdars
ms.date: 12/17/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
description: Prepare la red de su organización para la calidad de servicio (QoS) en Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
MS.collection: Teams_ITAdmin_PracticalGuidance
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8aa4bb6858fceb45fbf6abca8fe475ba49dbe1ba
ms.sourcegitcommit: 6205201cb1314e753f672654dade11dd4adbfe8a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2019
ms.locfileid: "29742866"
---
# <a name="implement-quality-of-service-qos-in-microsoft-teams"></a>Implementar la calidad de servicio (QoS) en los equipos de Microsoft

En este artículo le ayudará a preparar la red de su organización para calidad de servicio (QoS) en Microsoft Teams.

Puede usar QoS para dar prioridad al tráfico de red que es sensible a retrasos en la red a través de tráfico que es menos sensible. Una simple analogía es que QoS crea virtual "pistas de automóviles de uso compartido" en los datos por lo que algunos tipos de datos de red nunca o raramente encontrará los retrasos.
Cuando establezca prioridades para el tráfico de comunicaciones en tiempo real, como las llamadas o las reuniones compartidas en los equipos que se puede más confiable ofrecen una experiencia de usuario a nivel empresarial. Sin algún tipo de QoS, es posible que vea los siguientes problemas de calidad de voz y vídeo:

- Vibración – que llegan a los distintos tipos de paquetes de medios.
- Pérdida de paquetes – paquetes descartados, lo que puede provocar que faltan palabras o sílabas.
- Tiempo de retrasada ida y vuelta (RTT) – los paquetes multimedia tarda mucho tiempo para llegar a sus destinos.

Para que QoS ser verdaderamente eficaces, es necesario aplicar de extremo a extremo en su organización (usuario PCs, conmutadores de red y los enrutadores a la nube), debido a que cualquier parte de la ruta de acceso que se produce un error para admitir sus prioridades QoS puede reducir la calidad de las llamadas de la configuración de QoS coherente , vídeo y recursos compartidos de la pantalla.

QoS es un mecanismo que puede utilizar para dar prioridad a determinados tipos de tráfico de red que son sensibles a los retrasos en la red a través del resto del tráfico que es menos sensible. Una simple analogía es que QoS crea virtual "pistas de automóviles de uso compartido" en los datos de la red, por lo que algunos tipos de datos nunca o raramente encontrará los retrasos.

Cuando establezca prioridades para el tráfico de comunicaciones en tiempo real, como las llamadas o las reuniones compartidas en los equipos que se puede más confiable ofrecen una experiencia de usuario a nivel empresarial. Cuando no se implementa QoS, pueden inmovilizar pantallas compartidas en las reuniones, vídeo puede pixellate y cambio de color y las llamadas de voz pueden convertirse en intermitente y difícil o imposible comprender. Para que QoS ser verdaderamente eficaces, es necesario aplicar de extremo a extremo en su organización (usuario PCs, conmutadores de red y los enrutadores a la nube), debido a que cualquier parte de la ruta de acceso que se produce un error para admitir sus prioridades QoS puede reducir la calidad de las llamadas de la configuración de QoS coherente , vídeo y recursos compartidos de la pantalla.

![La relación entre una organización redes y servicios de Office 365: local de red y dispositivos que se conectan con una red de interconexión, lo que a su vez se conecta con los servicios de voz de Office 365 en la nube y conferencias de Audio.](media/Qos-in-Teams-Image1.png) 

Una opción disponible para QoS to-end de direcciones es [ExpressRoute de Azure](https://azure.microsoft.com/documentation/articles/expressroute-introduction/). Aun así, es recomendable que implemente QoS en la red local. Esto aumentará la calidad de las cargas de trabajo de comunicación en tiempo real en toda la implementación y mitigar los puntos de restricción. 

En la mayoría de los casos, la red conectar su empresa a la nube será una conexión a internet red no administrada donde podrá establecer fiable QoS. Una de las opciones disponible para permitir la QoS verdaderamente end-to-end es [ExpressRoute de Azure](https://azure.microsoft.com/documentation/articles/expressroute-introduction/). Aun así, es recomendable que implemente QoS en las partes de la red de extremo a extremo tiene control sobre, es decir, la red local. Esto aumentará la calidad de las cargas de trabajo de comunicación en tiempo real en toda la implementación y mitigar los puntos de restricción en la implementación existente.

## <a name="prioritize-teams-network-traffic-for-qos"></a>Establecer prioridades para el tráfico de red de los equipos para QoS 

En este artículo se centra en cómo dar prioridad al tráfico de comunicaciones en tiempo real de los equipos, es decir, voz y vídeo. También puede dar prioridad a otros tipos de tráfico, según sus necesidades.

Hay varias maneras para dar prioridad al tráfico, pero el más común es mediante el uso de marcas de (DSCP) punto de código de servicios diferenciados. Se pueden aplicar ("con etiqueta") en función de los intervalos de puertos o a través de objetos de directiva de grupo. Trataremos ambos tipos en este artículo. Se recomienda que use etiquetas temáticas según los intervalos de puertos debido a que funcionará para todos los dispositivos, no sólo los que se unen al dominio.

Controlar el marcado DSCP a través de objetos de directiva de grupo se asegura de que los equipos unidos a un dominio reciben la configuración correcta y que sólo un administrador puede administrarlos.

Es importante comprender que QoS sólo funciona cuando se implementa en todos los vínculos que se conectan el autor de la llamada a otra. Si utiliza QoS en la red interna y un usuario inicia sesión desde una ubicación remota, sólo puede dar prioridad a dentro de la red interna, administrada. Aunque las ubicaciones remotas pueden recibir una conexión administrada mediante la implementación de una red privada virtual (VPN), se recomienda que evite la ejecución de tráfico de comunicaciones en tiempo real a través de la VPN.

> [!NOTE]
> Se recomienda que implemente túnel dividido para que usuarios remotos conectados a VPN maximizar la calidad de la experiencia del usuario. Descargue el documento [Deploy de orientación-VPN dividido túnel](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_9 ) desde MyAdvisor para obtener más información.

En una organización global con vínculos administradas que abarcan continentes, se recomienda encarecidamente QoS debido a que el ancho de banda para esos vínculos es limitado en comparación con la LAN.

## <a name="qos-queues"></a>Colas de QoS

Para proporcionar QoS, dispositivos de red deben tener una forma de clasificar el tráfico y deben ser capaz de distinguir de voz o vídeo desde otro tráfico de red. 

Servicios diferenciados (DiffServ) se utiliza el tipo de campo de servicios (ToS) en el encabezado de un paquete IPv4 o IPv6 para establecer la prioridad de dispositivos de red. Los seis bits más significativos del campo DiffServ son el punto de código de servicios diferenciados o DSCP. Con esto, el tráfico puede se clasifica como un tipo determinado (por ejemplo, voz) y, a continuación, marca (101110 o 46 en decimal para el tráfico de voz), por lo que cuando estas marcas del proceso de dispositivos de red, el tráfico puede ser prioriza según corresponda (EF reenvío, en en este ejemplo).

Cuando el tráfico de red entra en un enrutador, el tráfico se coloca en una cola. Si no hay ningún QoS en su lugar, hay sólo una cola y los datos se tratan como, primero en salir. Esto significa que el tráfico de voz (que es muy sensible a los retrasos) es posible que se bloquee detrás de tráfico de servicios en línea de transmisión por secuencias. Cuando se implementan QoS, puede definir varias colas mediante el uso de las características de administración de congestión diferentes (por ejemplo, de Cisco colas de prioridad y basada en la clase promedio ponderado razonable cola [CBWFQ]) y las características de prevención de congestión (por ejemplo, promedio ponderado [aleatorio de detección temprana WRED]).

![El ancho de banda disponible total se divide entre varias colas: audio, vídeo y otro tipo de tráfico, que se han asignado prioridades diferentes.] (media/Qos-in-Teams-Image2.png "El ancho de banda disponible total se divide entre varias colas: audio, vídeo y otro tipo de tráfico, que se han asignado prioridades diferentes.")

_La figura 2. Ejemplos de colas de QoS_

Después de que estas piezas están en su lugar, es posible entregar predecible QoS debido a que la red ahora sabe cómo clasificar, marcar y establecer prioridades de tráfico. Desde la perspectiva de los equipos, el paso de configuración más importante es la clasificación y el marcado de paquetes, pero para que QoS to-end a realizarse correctamente también necesita alinear cuidadosamente la configuración de la aplicación con la configuración de red subyacente.

## <a name="teams-qos-scenarios"></a>Escenarios de QoS de equipos

Las instrucciones para la implementación de QoS para equipos se basan en cuatro situaciones:

*  **Escenario 1:** Ha implementado o a implementar los equipos y piensa implementar QoS a través de etiquetado basado en puerto. Basado en el puerto etiquetado es el método más confiable porque todo el mundo funciona en todas las plataformas y es más fácil de implementar.  

*  **Escenario 2:** Ha implementado o a implementar los equipos y piensa implementar QoS a través de etiquetado de objeto de directiva de grupo. Este método se usa en ocasiones en combinación con el escenario 1. Aunque este escenario es totalmente válido, sólo funciona para los clientes Unidos a un dominio de Windows. Cualquier dispositivo que no es un cliente de Windows unido a un dominio no estará activado para DSCP etiquetado.

*  **Escenario 3:** Ha implementado Skype para profesionales Online, incluido el etiquetado de QoS y ahora están implementando los equipos. Si ese es su caso, Teams respetará la configuración existente y usará los mismos intervalos de puertos y el mismo etiquetado que el cliente de Skype Empresarial. En la mayoría de los casos, no se necesitarán ninguna configuración adicional. 

    > [!NOTE]
    > Si utiliza QoS de nombre de aplicación de etiquetas temáticas a través de directiva de grupo, debe agregar Teams.exe como el nombre de la aplicación.

*  **Escenario 4:** Ha implementado o a implementar los equipos y desea implementar QoS a través de basado en el puerto etiquetado mediante el uso de un intervalo de puertos personalizados.

## <a name="implement-qos"></a>Implementar QoS

En un nivel muy alto, la implementación de QoS requiere estos pasos:

1. Determinar los requisitos de ancho de banda y la ruta.

2. Use marcados de DSCP e intervalos de puertos para clasificar el tráfico.

3. Configurar la configuración de QoS basada en Directiva dentro de un objeto de directiva de grupo.

4. Compruebe los intervalos de puertos en el objeto de directiva de grupo.

5. Validar QoS mediante el análisis de tráfico de los equipos de la red.

Preparación para implementar QoS, tenga en cuenta las siguientes instrucciones:

- La ruta de acceso más corta a Office 365 es mejor.

- Cierre de los puertos sólo llevará a degradación de la calidad.

- Cualquier obstáculo intermedias, como los servidores proxy, no se recomienda.

- Limitar el número de saltos de:

    - Cliente de perímetro de red – saltos de 3 a 5.
    - ISP para el perímetro de red de Microsoft – 3 saltos
    - Perímetro de red de Microsoft a un destino final – irrelevante 

Para obtener información acerca de cómo configurar los puertos de firewall, vaya a [las direcciones URL de Office 365 e intervalos IP](office-365-urls-ip-address-ranges.md).

## <a name="determine-bandwidth-requirements"></a>Determinación de los requisitos de ancho de banda

Antes de configurar QoS para Microsoft Teams, es importante preparar la red para Microsoft Teams y determinar los requisitos de ancho de banda. Proporcionar QoS en la red requiere la reserva de una cantidad de ancho de banda definida en cada vínculo para el tráfico en tiempo real. (Si ese ancho de banda no es necesaria para el tráfico en tiempo real en cualquier momento, se puede utilizar para el tráfico de otro.)

Congestión del tráfico a través de una red tendrá un impacto en gran medida calidad de los medios. Por lo que una falta de clientes potenciales de ancho de banda a la degradación del rendimiento y una experiencia de usuario deficiente, considere la posibilidad de ancho de banda como punto de partida para la implementación de los equipos de planeación. A medida que crece el uso y la adopción de los equipos, usar informes para realizar los ajustes necesarios. 

El organizador de red disponible en FastTrack es útil al determinar los requisitos de ancho de banda.

### <a name="requirements-for-a-connection-from-your-network-to-microsoft-network-edge"></a>Requisitos para una conexión de la red de perímetro de red de Microsoft

Para obtener la mejor calidad de medios, los objetivos de rendimiento de red o los umbrales que se muestra en la tabla 1 son necesarios para una conexión de red de su organización para el perímetro de red de Microsoft.

> [!IMPORTANT]
> Conectividad entre un cliente de los equipos en la red de su empresa a los servicios de Office 365 debe cumplir los siguientes requisitos de rendimiento de red.

_La tabla 1. Métricas de rendimiento de red - cliente de servicios de Office 365_

| Métrica | Destino  |
|--------|--------|
| Latencia (unidireccional) | < 50 milisegundos |
| Latencia (tiempo de ida y vuelta (RTT) | < 100 milisegundos |
| Pérdida de paquetes de ráfaga | 10% de < durante cualquier intervalo de 200 milisegundos |
| Pérdida de paquetes | < 1% durante los 15 segundos |
| Vibración de llegada entre granjas de paquetes | < 30 milisegundos durante cualquier intervalo de segundo 15 |
| Reordenamiento de paquetes | < 0,05% fuera de los paquetes de orden |

El destino de métricas de latencia supone que su sitio de empresa o los sitios y los bordes de Microsoft son en el mismo continente.

El sitio de su compañía a la conexión de perímetro de red de Microsoft incluye primer salto acceso a la red, que puede ser WiFi u otra tecnología inalámbrica.

Ancho de banda adecuado o QoS de planeación, supone el destino de rendimiento de red. En otras palabras, los requisitos se aplican directamente al tráfico de medios en tiempo real de los equipos cuando la conexión de red está bajo una carga máxima.

### <a name="requirements-for-a-connection-from-your-network-edge-to-microsoft-network-edge"></a>Requisitos para una conexión desde el perímetro de red a Microsoft de la red perimetral

La tabla 2 muestra los umbrales que son necesarios para la conexión entre el perímetro de red y el perímetro de red de Microsoft o los objetivos de rendimiento de red. Esto excluye de la red interna de la organización o WAN y está diseñada como una guía cuando se prueba el tráfico de red que se envía a través de internet o a través de una red de socios de ExpressRoute.

> [!IMPORTANT]
> Conectividad entre el perímetro de red de su compañía a los bordes de la red de Microsoft debe cumplir los siguientes requisitos de rendimiento de red.

_Tabla 2. Métricas de rendimiento de red - lado a lado_

| Métrica | Destino  |
|--------|--------|
| Latencia (unidireccional) | < 30 milisegundos |
| Latencia (tiempo de ida y vuelta (RTT) | < 60 milisegundos |
| Pérdida de paquetes de ráfaga | < 1% durante cualquier intervalo de 200 milisegundos |
| Pérdida de paquetes | < 0,1% durante los 15 segundos |
| Vibración de llegada entre granjas de paquetes | < 15 milisegundos durante cualquier intervalo de segundo 15 |
| Reordenamiento de paquetes | < 0,01% fuera de los paquetes de orden |


## <a name="recommended-dscp-markings"></a>Marcas de DSCP recomendados

Cuando esté listo para configurar QoS, el primer paso es clasificar los flujos de tráfico (como audio y vídeo) mediante la asignación de valores de DSCP para los intervalos de puertos único, no se superpongan. El valor DSCP asignado aquí determinará la prioridad del tráfico que pasa a través de la red, en función de la configuración de red. Cada carga de trabajo obtiene su propio valor DSCP, aunque no necesariamente un valor único, es posible que desee establecer el mismo valor para las cargas de trabajo de voz y vídeo, para concederles la misma prioridad en la red.  

El valor de DSCP para usar depende de cómo desea dar prioridad a la carga de trabajo. Por ejemplo, es posible que determinan los requisitos empresariales que dar a aplicación de uso compartido de la misma prioridad que el vídeo (y, por tanto, se marca con el mismo valor DSCP como vídeo). Otros entornos podrían tener una estrategia de QoS existente en su lugar, que le ayudarán a determinar la prioridad de las cargas de trabajo de la red. 

Tabla 3 se muestran las marcas DSCP necesarias para los equipos con ExpressRoute. Estas marcas pueden servir como un buen punto de partida para los clientes que no están seguro de qué se va a utilizar en sus propios entornos. Para obtener más información, lea [Requisitos de QoS ExpressRoute](https://docs.microsoft.com/azure/expressroute/expressroute-qos).

_Tabla 3. Marcados de DSCP_

| Intervalo de puertos de origen de cliente |Protocolo|Categoría del medio|Valor de DSCP|Clase de DSCP|
|---------|---------|---------|---------|---------|
| 50.000 – 50,019|TCP/UDP|Audio|46|Desvío rápido (EF)|
| 50,020 – 50,039|TCP/UDP|Vídeo|34|Desvío garantizado (AF41)|
| 50,040 – 50,059|TCP/UDP|Uso compartido de aplicaciones y escritorio|18|Reenvío (AF21) asegurado|

Tenga en cuenta lo siguiente cuando use la información en la tabla 3:

-  Si piensa implementar ExpressRoute en el futuro y aún no ha implementado QoS, se recomienda que siga las instrucciones en la tabla 3 para que los valores DSCP son los mismos del remitente al receptor. 

-  Todos los clientes, incluidos los clientes móviles y dispositivos de los equipos, va a usar estos intervalos de puertos y se verán afectados por implementar cualquier directiva DSCP que usa estos intervalos de puerto de origen. Los únicos clientes que seguirán usando puertos dinámicos son los clientes basados en explorador (es decir, los clientes que permiten que los participantes unirse a reuniones mediante sus exploradores).

-  Aunque el cliente de Mac usa los mismos intervalos de puertos, también usa valores codificado de forma rígida para (EF) de audio y vídeo (AF41). Estos valores no son configurables.


## <a name="source-ports-used-by-teams"></a>Puertos de origen que usa Teams

En Teams, QoS se debe configurar en función de los puertos de origen que utilizan las diferentes cargas de trabajo. Actualmente, ninguno de los dos intervalos de puertos de servidor ni de cliente son configurables. 

Los intervalos de puertos de origen de cliente que aparecen en la tabla 3 también se aplican a los equipos y usar sus marcas DSCP QoS asociadas.

Es el método recomendado de la implementación de estas directivas de QoS utilizar los puertos de origen del cliente con una dirección IP de origen y de destino de "cualquiera". Esta forma detectará tanto el tráfico de medios entrantes y salientes en la red interna. 

> [!NOTE]
> Si ya ha configurado QoS según los intervalos de puertos de origen para Skype para profesionales en línea, se aplicará la misma configuración a los equipos y no se requerirá ningún cambio adicional. Si ha implementado Skype para Business Server local, debe volver a examinar las directivas de QoS y ajustarlas si es necesario.

## <a name="set-dscp-markings"></a>Establecer marcados de DSCP

Existen varios enfoques para establecer las marcas DSCP adecuadas para la clasificación del tráfico:

-  **El marcado DSCP en el punto final:** Por lo general es la opción preferida, debido a que el propio extremo proporciona los marcadores adecuados. Actualmente esto puede realizarse mediante el uso de un objeto de directiva de grupo, pero sólo puede utilizarse en los clientes Unidos a un dominio de Windows. Los clientes móviles no proporcionan un mecanismo para marcar el tráfico mediante el uso de los valores DSCP. Si bien no se puede configurar que no sean&ndash;unido a un dominio los clientes de Windows para el tráfico de etiqueta, los clientes como Mac OS tienen etiquetas codificado de forma rígida y siempre se etiqueta el tráfico como se describió anteriormente.

-  **DSCP basado en el puerto etiquetado mediante el uso de listas de control de acceso (ACL) en los enrutadores:** Esto es una opción muy comunes encontrada en entornos heterogéneos de Windows y Mac. En este escenario, el equipo de red marca el tráfico en los enrutadores de entrada/salida (normalmente se encuentra en la WAN) en función de los intervalos de puertos de origen definidos para cada modalidad. Aunque esto funciona a través de plataformas, sólo marca el tráfico en el borde WAN: no completamente en el equipo cliente y por lo tanto, incurre en sobrecarga de administración.

-  **Una combinación de marcado de DSCP en el extremo y las ACL basadas en puerto en los enrutadores:** Se recomienda esta combinación, si es posible en su entorno. Utilice un objeto de directiva de grupo para detectar la mayoría de los clientes y también usan DSCP basado en el puerto etiquetado para asegurarse de que mobile, Mac y otros clientes seguirán recibiendo tratamiento de QoS (por lo menos parcialmente).

Puede usar QoS basada en Directiva dentro de la directiva de grupo para establecer el valor de DSCP para el intervalo de puertos de origen predefinido en el cliente de los equipos. Usar los intervalos de puertos especificados en la tabla 3 para crear una directiva para cada carga de trabajo.

Una vez que ha identificado los intervalos de puertos, el siguiente paso es configurar la configuración de QoS basada en Directiva dentro de un objeto de directiva de grupo. Puede encontrar más información acerca de estos pasos en la [configuración de intervalos de puertos y una directiva de calidad de servicio para los clientes en Skype para Business Server](https://docs.microsoft.com/SkypeForBusiness/manage/network-management/qos/configuring-port-ranges-for-your-skype-clients#configure-quality-of-service-policies-for-clients-running-on-windows-10).

Para crear una directiva de audio de QoS para equipos Windows 10, primero inicie sesión en un equipo en el que se ha instalado Administración de directivas de grupo. Abra Administración de directivas de grupo (haga clic en Inicio, elija Herramientas administrativas y, a continuación, haga clic en administración de directivas de grupo) y, a continuación, complete los siguientes pasos:

1. En administración de directivas de grupo, busque el contenedor donde se debe crear la nueva directiva. Por ejemplo, si todos los equipos cliente se encuentran en una unidad organizativa denominada **clientes**, se debe crear la nueva directiva en la unidad organizativa de cliente.

2. Haga clic en el contenedor adecuado y, a continuación, haga clic en **crear un GPO en este dominio y vincularlo aquí**.

3. En el cuadro de diálogo **Nuevo GPO** , escriba un nombre para el nuevo objeto de directiva de grupo en el cuadro **nombre** y, a continuación, haga clic en **Aceptar**.

4. Haga clic en la directiva recién creada y, a continuación, haga clic en **Editar**.

5. En el Editor de administración de directiva de grupo, expanda **Configuración del equipo**, expanda **Configuración de Windows**, haga clic en **QoS basada en directiva**y, a continuación, haga clic en **Crear nueva directiva**.

6. En el cuadro de diálogo de **QoS basada en directiva** , en la página de apertura, escriba un nombre para la nueva directiva en el cuadro **nombre** . Seleccione **Especificar el valor de DSCP** y establezca el valor **46**. Deje **Especificar velocidad de aceleración saliente** no está seleccionada y, a continuación, haga clic en **siguiente**.

7. En la página siguiente, seleccione **sólo las aplicaciones con este nombre del archivo ejecutable** y escriba el nombre **Teams.exe**y, a continuación, haga clic en **siguiente**. Esta opción indica a la directiva de solo dar prioridad al tráfico coincidente desde el cliente de los equipos.

8. En la tercera página, asegúrese de que **cualquier dirección IP de origen** y **cualquier dirección IP de destino** están seleccionados y, a continuación, haga clic en **siguiente**. Estos dos valores Asegúrese de que se administrarán los paquetes independientemente de qué equipo (dirección IP) envía los paquetes y qué equipo (dirección IP) recibirán los paquetes.

9. En la cuarta página, seleccione **TCP y UDP** en la lista desplegable **Seleccione el protocolo que se aplica esta directiva de QoS** . TCP (Protocolo de Control de transmisión) y UDP (Protocolo de datagramas de usuario) son los dos protocolos de red usados con más frecuencia.

10. Bajo el encabezado, **Especifique el número de puerto de origen**, seleccione **desde este intervalo o el puerto de origen**. En el cuadro de texto que lo acompaña, escriba el intervalo de puertos reservado para las transmisiones de audioconferencias. Por ejemplo, si ha reservado puertos 50000 a través de puertos 50019 para el tráfico de audio, escriba el intervalo de puertos con este formato: **50000:50019**. Haga clic en **Finalizar**.

11. Repita los pasos del 5 al 10 para crear directivas para vídeo y uso compartido de aplicaciones y escritorio, sustituyendo los valores apropiados en los pasos 6 y 10.

Las nuevas directivas que se ha creado no surtirán efecto hasta que se ha actualizado la directiva de grupo en los equipos cliente. Aunque la directiva de grupo se actualiza periódicamente en su propio, puede forzar una actualización inmediata.

### <a name="force-group-policy-refresh"></a>Actualización de la directiva de grupo Force

1. En cada equipo para el que desea actualizar la directiva de grupo, abra una consola de comandos. Asegúrese de que la consola de comandos está establecida en Ejecutar como administrador.

2. En el símbolo del sistema, escriba
   ```
    gpupdate.exe /force
   ```

## <a name="verify-dscp-markings-in-the-group-policy-object"></a>Compruebe los marcados de DSCP en el objeto de directiva de grupo

Para comprobar que se han establecido los valores desde el objeto de directiva de grupo, realice los pasos siguientes.

1. Abra una consola de comandos. Asegúrese de que la consola de comandos está establecida en Ejecutar como administrador.

2. En el símbolo del sistema, escriba 
   ```
   gpresult /R > gp.txt
   ```

   Esto generará un informe y enviarlo a un archivo de texto denominado gp.txt. Como alternativa, puede escribir el comando siguiente para generar los mismos datos en un informe HTML más legible llamado gp.html:
   ```
   gpresult /H >gp.html
   ```
 ![Captura de pantalla de la ventana de la consola que se ejecuta el comando gpresult.] (media/Qos-in-Teams-Image3.png "Captura de pantalla de la ventana de la consola que se ejecuta el comando gpresult.")

3. En el archivo generado, busque el encabezado **Aplica objetos de directiva de grupo** y compruebe que los nombres de los objetos de directiva de grupo que creó anteriormente están en la lista de directivas aplicadas. 

4. Abra el Editor del registro y vaya a:

   HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\QoS\

   Compruebe los valores de las entradas del registro que aparecen en la tabla 4.

   _Tabla 4. Valores de las entradas del registro de Windows para QoS_


   |          Nombre          |  Tipo  |    Datos     |
   |------------------------|--------|-------------|
   |    Nombre de la aplicación    | REG_SZ |  Teams.exe  |
   |       Valor de DSCP       | REG_SZ |     46      |
   |        IP local        | REG_SZ |     \*      |
   | Longitud del prefijo de IP local | REG_SZ |     \*      |
   |       Puerto local       | REG_SZ | 50000-50019 |
   |        Protocolo        | REG_SZ |     \*      |
   |       IP remota        | REG_SZ |     \*      |
   |    Prefijo de dirección IP remota    | REG_SZ |     \*      |
   |      Puerto remoto       | REG_SZ |     \*      |
   |     Velocidad de limitación      | REG_SZ |     -1      |


5. Compruebe que es correcto para el cliente que está utilizando el valor de la entrada de nombre de la aplicación y compruebe que el valor de DSCP y el puerto Local entradas reflejan la configuración en el objeto de directiva de grupo.

## <a name="validate-qos-by-analyzing-teams-traffic-on-the-network"></a>Validar QoS mediante el análisis de tráfico de los equipos de la red

Para QoS para ser eficaces, el valor de DSCP de valor conjunto por el objeto de directiva de grupo debe estar presente en ambos extremos de una llamada. Mirando el tráfico generado por el cliente de los equipos, puede comprobar que el valor de DSCP no está cambiado o se eliminan cuando el tráfico de carga de trabajo de los equipos recorre los movimientos a través de la red.

Preferiblemente, capturar el tráfico en el punto de salida de la red. Puede utilizar la duplicación de puertos en un conmutador o enrutador para ayudar con esto.

### <a name="use-network-monitor-to-verify-dscp-values"></a>Utilice el Monitor de red para comprobar los valores DSCP

Monitor de red es una herramienta que se puede [descargar de Microsoft](https://www.microsoft.com/download/4865) para analizar el tráfico de red.

1. En el PC que ejecuta el Monitor de red, conecte con el puerto en el que se ha configurado para la creación de reflejo de puerto y capturar paquetes de inicio. 

2. Realizar una llamada mediante el cliente de los equipos. Asegúrese de que se ha establecido medios antes de colgar la llamada. 

3. Detenga la captura.

4. En el campo de **Filtro de presentación** , utilice la dirección IP de origen del PC que realizó la llamada y refinar el filtro mediante la definición de valor DSCP 46 (hex 0xb8) como criterios de búsqueda, como se muestra en el ejemplo siguiente:

    Source == "192.168.137.201" AND IPv4.DifferentiatedServicesField == 0xb8 

    ![Captura de pantalla del cuadro de diálogo Filtro de visualización en el Monitor de red, que muestra los filtros que se debe aplicar.] (media/Qos-in-Teams-Image4.png "Captura de pantalla del cuadro de diálogo Filtro de visualización en el Monitor de red, que muestra los filtros que se debe aplicar.")

5. Seleccione **Aplicar** para activar el filtro.

6. En la ventana de **Marco de resumen** , seleccione el primer paquete de UDP.

7. En la ventana de **Marco de detalles** , expanda el elemento de lista IPv4 y tenga en cuenta el valor al final de la línea que comienza con **DSCP**. 

    ![Captura de pantalla del cuadro de diálogo Detalles de las tramas en el Monitor de red, el resaltado de configuración DSCP.] (media/Qos-in-Teams-Image5.png "Captura de pantalla del cuadro de diálogo Detalles de las tramas en el Monitor de red, el resaltado de configuración DSCP.")

En este ejemplo, se establece el valor de DSCP a 46. Esto es correcto, debido a que el puerto de origen usado es 50019, lo que indica que se trata de una carga de trabajo de voz. 

Repita la verificación para cada carga de trabajo que marque el GPO. 

## <a name="more-information"></a>Más información

[Vídeo: Planeación de red](https://aka.ms/teams-networking)

[Preparar la red de la organización para Microsoft Teams](prepare-network.md)

[Requisitos de ExpressRoute QoS](https://docs.microsoft.com/azure/expressroute/expressroute-qos)
