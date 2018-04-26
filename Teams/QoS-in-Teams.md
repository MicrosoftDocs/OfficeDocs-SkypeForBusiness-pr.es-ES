---
title: QoS en equipos de Microsoft - equipos de Microsoft
author: rmw2890
ms.author: MyAdvisor
manager: Serdars
ms.date: 04/23/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
description: Prepare la red de su organización para la calidad de servicio (QoS) en Microsoft Teams.
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 884055dce490b9db8fd31f6e52042a4315633e00
ms.sourcegitcommit: f942232d43fc4ad56b34dd400fdb4bca39013f5f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/26/2018
---
# <a name="quality-of-service-qos-in-microsoft-teams"></a>Calidad de servicio (QoS) en Microsoft Teams

Este artículo le ayudará a preparar la red de su organización para calidad de servicio (QoS) en Teams de Microsoft.
QoS es un mecanismo que se utiliza para dar prioridad a determinados tipos de tráfico de red. Priorizar el tráfico para los servicios de comunicaciones en tiempo real, como los equipos es importante para ofrecer una experiencia de usuario de calidad profesional. Para que QoS realmente efectiva, debe configurar una conexión compatibles con QoS de extremo a extremo (PC, conmutadores de red y los enrutadores de la nube), porque cualquier parte de la ruta de acceso que no admitan QoS puede degradar la calidad de la llamada entera.

![La relación entre una organización redes y servicios de Office 365: local red y dispositivos que se conectan con una red de interconexión, que a su vez se conecta con los servicios de conferencias de Audio y voz de nube de Office 365.] (media/Qos-in-Teams-Image1.png "La relación entre una organización redes y servicios de Office 365: local red y dispositivos que se conectan con una red de interconexión, que a su vez se conecta con los servicios de conferencias de Audio y voz de nube de Office 365.")

_La figura 1. La relación entre una organización redes y servicios de Office 365_
 

En la mayoría de los casos, la red de interconexión será una conexión a internet red no administrada. Una opción disponible para QoS end-to-end de direcciones es [ExpressRoute de Azure](https://azure.microsoft.com/documentation/articles/expressroute-introduction/). Recomendamos que implemente QoS en las partes de la red tendrá control sobre, a saber, la red local. Esto aumentará la calidad de las cargas de trabajo de comunicación en tiempo real en toda la implementación y aliviar puntos de restricción en su implementación de. 


## <a name="prioritize-teams-network-traffic-for-qos"></a>Priorizar el tráfico de red de los equipos de QoS 

En este artículo se centra en cómo dar prioridad al tráfico de comunicaciones en tiempo real de los equipos, es decir, voz y vídeo. También puede dar prioridad a otros tipos de tráfico, en función de sus necesidades.

Existen diversos métodos para priorizar el tráfico, pero el más común consiste en usar marcados de punto de código de servicios diferenciados (DSCP). Pueden ser aplicados ("etiquetado") en función de intervalos de puertos y también a través de objetos de directiva de grupo. Trataremos en este artículo. Recomendamos que utilice el etiquetado basado en intervalos de puerto ya que funciona para todos los dispositivos, no sólo los que se une al dominio.

Controlar el marcado de DSCP a través de objetos de directiva de grupo garantiza que los equipos unidos a un dominio reciben la configuración correcta y que sólo un administrador puede administrar este.
 
Es importante comprender que QoS sólo funciona cuando se implementa en todos los vínculos que conectan el llamador al destinatario de la llamada. Si utiliza QoS de la red interna y un usuario inicia sesión desde una ubicación remota, sólo puede dar prioridad dentro de la red interna, administrada. Aunque las ubicaciones remotas pueden recibir una conexión administrada mediante la implementación de una red privada virtual (VPN), se recomienda evitar el uso de tráfico de comunicaciones en tiempo real a través de la VPN.

> [!NOTE]
> Recomendamos que implemente túnel dividido para que usuarios remotos conectados por VPN maximizar la calidad de la experiencia del usuario. Descargue el documento [Deploy-guía-VPN Split túnel](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_9 ) de MyAdvisor para obtener más información.

En una organización global con vínculos administrados que abarcan continentes, QoS recomienda porque el ancho de banda para esos vínculos es limitado en comparación con la LAN.

## <a name="qos-queues"></a>Colas de QoS

Para proporcionar un nivel garantizado de servicio para una aplicación en la red, los dispositivos de red subyacente deben tener una manera de clasificar distintos tipos de tráfico. Si su organización desea dar prioridad de tráfico de voz sobre el resto de tráfico, un enrutador (por ejemplo) debe ser capaz de distinguir entre el tráfico de voz y el tráfico normal de navegación por la web. 

Servicios diferenciados (DiffServ) proporciona un marco en el que el tráfico tiene prioridad diferentes dispositivos de red en función del tipo de campo de servicios (ToS) en el encabezado de un paquete IPv4 o IPv6. Los seis bits más significativos del campo DiffServ son el punto de código de servicios diferenciados o DSCP. Con este marco, tráfico puede ser clasificado como un tipo determinado de tráfico (por ejemplo, voz) y entonces marcado (101110 o 46 en decimal para el tráfico de voz), para que cuando dichas marcas de proceso de los dispositivos de red, el tráfico puede ser priorizadas en consecuencia () Reenvío acelerado, en este ejemplo).

Cuando el tráfico de red entre un enrutador, el tráfico se coloca en una cola, si no hay ningún QoS en lugar, básicamente hay sólo una cola y los datos se tratan como, primero en salir. Esto significa que puede quedar atascado tráfico de voz (que es muy sensible a retrasos) detrás del tráfico de servicios en línea de transmisión. Cuando la implementación de QoS, puede definir varias colas mediante características de prevención de congestión (por ejemplo, ponderada [aleatorio de detección temprana y características de administración de la congestión diferente (como de Cisco colas de prioridad y basados en clases ponderado razonable cola [CBWFQ]) WRED]).

![El ancho de banda disponible total se divide entre varias colas, audio, vídeo y otro tráfico — que se han asignado prioridades diferentes.] (media/Qos-in-Teams-Image2.png "El ancho de banda disponible total se divide entre varias colas, audio, vídeo y otro tráfico — que se han asignado prioridades diferentes.")

_La figura 2. Colas de QoS visualizadas_

Una vez que estas piezas están en su lugar, es posible ofrecer QoS predecible porque la red administrada subyacente ahora entiende cómo clasificar, marcar y dar prioridad al tráfico. Desde la perspectiva de los equipos, el paso de configuración más importante es la clasificación y el marcado de paquetes, pero para que QoS end-to-end tenga éxito también debe alinear cuidadosamente la configuración de la aplicación con la configuración de la red subyacente.

## <a name="teams-qos-scenarios"></a>Escenarios de QoS de equipos

Las instrucciones para la implementación de QoS para equipos se basan en cuatro situaciones:

*  **Escenario 1:** Ha implementado, o va a implementar, los equipos y está planeando la implementación de QoS a través de etiquetado basado en puerto. Etiquetado basado en puerto es el método más confiable, porque funciona universalmente en todas las plataformas y es más fácil de implementar.  

*  **Escenario 2:** Ha implementado, o va a implementar, los equipos y planean implementar QoS mediante etiquetas de objeto de directiva de grupo. Este método se usa en ocasiones en combinación con el escenario 1. Aunque esta situación es totalmente válida, es importante comprender que sólo funciona para los clientes Unidos a un dominio de Windows. Cualquier dispositivo que no es un cliente Windows del dominio no estará activado para DSCP etiquetado.

*  **Escenario 3:** Ha implementado Skype para los negocios en línea, incluyendo QoS etiquetado y ahora están implementando los equipos. Si ese es su caso, Teams respetará la configuración existente y usará los mismos intervalos de puertos y el mismo etiquetado que el cliente de Skype Empresarial. En la mayoría de los casos, no se necesitará ninguna configuración adicional. 
 
    > [!NOTE]
    > Si utiliza aplicación nombre QoS tagging mediante Directiva de grupo, debe agregar Teams.exe como nombre de la aplicación.

*  **Escenario 4:** Ha implementado, o va a implementar, los equipos y desea implementar QoS a través de etiquetado basado en puerto mediante un intervalo de puerto personalizado.

## <a name="recommended-dscp-markings"></a>Marcados de DSCP recomendados

El primer paso es clasificar los flujos de tráfico (como audio y video) asignando valores DSCP a los intervalos de puerto único, no se superponen. El valor DSCP asignado aquí determinará la prioridad del tráfico que pasa a través de la red, basándose en la configuración de red. Cada carga de trabajo obtiene su propio valor DSCP, aunque no necesariamente un valor único, algunos clientes podrían establecer el mismo valor para cargas de trabajo de voz y vídeo, dándoles la misma prioridad en la red.  

El valor DSCP a utilizar depende de cómo desea dar prioridad a la carga de trabajo. Por ejemplo, los requerimientos del negocio pueden dictar que da aplicación compartir la misma prioridad que el vídeo (y, por tanto, se marca con el mismo valor DSCP como vídeo). Otros entornos podrían tener una estrategia de QoS existente en el lugar, que le ayudará a determinar la prioridad de las cargas de trabajo de la red. 

La tabla 1 muestra las marcas DSCP necesarias al utilizar equipos con ExpressRoute. Estos marcadores pueden servir como un buen punto de partida para los clientes que no saben lo que se debe utilizar en sus propios entornos. Para obtener más información, lea [Requisitos de QoS ExpressRoute](https://docs.microsoft.com/azure/expressroute/expressroute-qos).


_La tabla 1. Marcados de DSCP_
    
| Intervalo de puerto de origen de cliente |Protocolo|Categoría del medio|Valor de DSCP|Clase de DSCP|
|---------|---------|---------|---------|---------|
| 50.000 – 50,019|TCP/UDP|Audio|46|Desvío rápido (EF)|
| 50,020: 50,039|TCP/UDP|Vídeo|34|Desvío garantizado (AF41)|
| 50,040: 50,059|TCP/UDP|Aplicación o escritorio compartido|18|(AF21) de reenvío asegurado|

Hay que tener en cuenta algunas cosas cuando se use la información de la tabla 1:
    
-  Si piensa implementar ExpressRoute en el futuro y aún no ha implementado QoS, se recomienda que siga las instrucciones en la tabla 1 para que los valores DSCP son los mismos del remitente al receptor. 

-  Todos los clientes, incluidos los clientes móviles y dispositivos de equipos, utilizarán estos intervalos de puertos y se verá afectados por ninguna directiva DSCP implementar que utiliza estos intervalos de puerto de origen. Los únicos clientes que seguirán usar puertos dinámicos son los clientes basados en explorador (es decir, aquellos clientes que permiten a los participantes unirse a reuniones mediante sus exploradores).

-  Aunque el cliente Mac utilizar los mismos rangos de puerto, el cliente de Mac también utiliza valores codificados (EF) de audio y vídeo (AF41). Estos valores no son configurables.
 
    
## <a name="source-ports-used-by-teams"></a>Puertos de origen que usa Teams

En Teams, QoS se debe configurar en función de los puertos de origen que utilizan las diferentes cargas de trabajo. Ni intervalos de puerto del servidor ni el cliente son actualmente configurables. 

Tenga en cuenta los intervalos de puertos de origen de cliente se enumeran en la tabla 2 y utilizar sus marcas DSCP QoS asociadas.

_La tabla 2. Intervalos de puerto de origen de cliente_

| Intervalo de puerto de origen de cliente |Protocolo|Categoría del medio|Valor de DSCP|Clase de DSCP|
|---------|---------|---------|---------|---------|
| 50.000 – 50,019|TCP/UDP|Audio|46|Desvío rápido (EF)|
| 50,020: 50,039|TCP/UDP|Vídeo|34|Desvío garantizado (AF41)|
| 50,040: 50,059|TCP/UDP|Aplicación o escritorio compartido|18|(AF21) de reenvío asegurado|

El método recomendado para la implementación de estas directivas de QoS es utilizar los puertos de origen del cliente con una dirección IP de origen y de destino de "cualquiera". Esta forma detectará tanto tráfico de medios entrantes y salientes de la red interna. 

> [!NOTE]
> Si ya ha configurado QoS basado en intervalos de puerto de origen para Skype para los negocios en línea, se aplicará la misma configuración a los equipos y no se requerirá ningún cambio adicional. Si ha implementado Skype para Business Server local, debe volver a diseñar las directivas de QoS.

## <a name="setting-dscp-markings"></a>Establecer marcas de DSCP

Hay varios enfoques para establecer las marcas DSCP adecuadas para la clasificación del tráfico:

-  **Marcado de DSCP en el punto final:** Por lo general es la opción preferida, porque el propio extremo proporciona los marcadores adecuados. Actualmente esto puede hacerse mediante un objeto de directiva de grupo, pero sólo puede utilizarse en los clientes Unidos a un dominio de Windows. Los clientes móviles no proporcionan un mecanismo para marcar el tráfico mediante el uso de valores DSCP. Aunque no puede configurar no&ndash;Unidos a un dominio de los clientes de Windows al tráfico de etiqueta, clientes como Mac OS tienen etiquetas codificadas de forma rígida y siempre se etiqueta el tráfico como se describió anteriormente.

-  **DSCP basado en el puerto etiquetado utilizando listas de control de acceso (ACL) en los enrutadores:** Ésta es una opción muy común que se encontró en entornos heterogéneos de Windows y Mac. En este escenario, el equipo de red marca el tráfico en los enrutadores de entrada/salida (normalmente se encuentra en la WAN) según los intervalos de puerto de origen definidos para cada modalidad. Aunque esto funciona en plataformas, sólo lo marca el tráfico en la WAN borde — no totalmente en el equipo cliente y por lo tanto, incurre en overhead de administración.
    
-  **Una combinación de marcado de DSCP en el extremo y ACL basadas en puerto en enrutadores:** Se recomienda esta combinación, si es posible en su entorno. Utilizar un objeto de directiva de grupo para detectar la mayoría de los clientes y también utilizar DSCP basado en el puerto etiquetado para asegurarse de que mobile, Mac y otros clientes seguirán recibiendo tratamiento de QoS (al menos parcialmente).
    
Puede utilizar QoS basada en directivas en directiva de grupo para establecer el valor DSCP para el intervalo de puertos de origen predefinido en el cliente de los equipos. Utilice los intervalos de puerto especificados en la tabla 3 para crear una directiva para cada carga de trabajo.

_La tabla 3. Intervalos de puertos por tipo de tráfico_
| Tipo de tráfico del cliente|Inicio del intervalo de puertos|Fin del intervalo de puertos|Valor de DSCP|
|---------|---------|---------|--------|
| Audio|50000|50019|46|
| Vídeo|50020|50039|34|
| Uso compartido de aplicaciones|50040|50059|18|

> [!NOTE]
> No se puede cambiar los intervalos de puertos establecidos por los equipos. Revise [este artículo de soporte técnico](https://support.microsoft.com/kb/2409256) para obtener la información más reciente. 

Cuando haya identificado los intervalos de puertos, el siguiente paso es configurar la configuración de QoS basada en directivas, dentro de un objeto de directiva de grupo. En [este artículo de TechNet](https://technet.microsoft.com/library/jj205371(v=ocs.15).aspx), encontrará más información sobre estos pasos. 

Las nuevas directivas que ha creado no surtirán efecto hasta que Directiva de grupo se ha actualizado en los equipos cliente. Aunque la directiva de grupo se actualiza periódicamente por su cuenta, puede forzar una actualización inmediata.

### <a name="force-group-policy-refresh"></a>Actualización de la directiva de grupo de fuerza

1. En cada equipo que desea actualizar la directiva de grupo, abra una consola de comandos. Asegúrese de que la consola de comandos está configurada para ejecutarse como administrador.

2. En el símbolo del sistema, escriba
```
    gpudate.exe /force
```

## <a name="verify-dscp-markings-in-the-group-policy-object"></a>Compruebe las marcas DSCP en el objeto de directiva de grupo

Para comprobar que se han establecido los valores desde el objeto de directiva de grupo, realice los pasos siguientes.

1.  Abrir una consola de comandos. Asegúrese de que la consola de comandos está configurada para ejecutarse como administrador.

2.  En el símbolo del sistema, escriba 
    ```
    gpresult /R >gp.txt
    ```

    Esto generará un informe y enviarlo a un archivo de texto denominado gp.txt. Como alternativa, puede escribir el comando siguiente para generar los mismos datos en un informe HTML más legible llamado gp.html:
    ```
    gpresult /H >gp.html
    ```
 
   ![Captura de pantalla de la ventana de consola ejecutando el comando gpresult.] (media/Qos-in-Teams-Image3.png "Captura de pantalla de la ventana de consola ejecutando el comando gpresult.")

3.  En el archivo generado, busque el encabezado **Aplicar objetos de directiva de grupo** y comprobar que los nombres de los objetos de directiva de grupo que creó anteriormente en la lista de directivas aplicadas. 

4.  Abra el Editor del registro y vaya a:

    HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\QoS\

    Compruebe los valores de las entradas del registro que se enumeran en la tabla 3.

    _La tabla 3. Valores de las entradas del registro de Windows para QoS_
    
    | Nombre | Tipo | Datos|
    |---------|---------|---------
    | Nombre de la aplicación|REG_SZ|Teams.exe|
    | Valor de DSCP|REG_SZ|46|
    | IP local|REG_SZ|*|
    | Longitud del prefijo de IP local|REG_SZ|*|
    | Puerto local|REG_SZ|50000-50019|
    | Protocolo|REG_SZ|*|
    | IP remota|REG_SZ|*|
    | Prefijo de la dirección IP remota|REG_SZ|*|
    | Puerto remoto|REG_SZ|*|
    | Velocidad de limitación|REG_SZ|-1|
    
5.  Compruebe que es correcto para el cliente que está usando el valor de la entrada del nombre de la aplicación y compruebe que el valor DSCP y el puerto Local entradas reflejan la configuración en el objeto de directiva de grupo.

## <a name="validate-qos-by-analyzing-teams-traffic-on-the-network"></a>Validar QoS mediante el análisis de tráfico de los equipos de la red

El valor DSCP establecido por el objeto de directiva de grupo deba estar presente del llamador al destinatario en orden para QoS sea efectiva. Mirando el tráfico generado por el cliente de los equipos, puede comprobar que el valor DSCP no está cambiado o se eliminan cuando el tráfico de carga de trabajo de equipos atraviese la red. 

Preferiblemente, capturar el tráfico en el punto de salida de la red. Puede utilizar la duplicación de puertos en un switch o router para ayudar con esto.

### <a name="use-network-monitor-to-verify-dscp-values"></a>Utilice a Monitor de red para comprobar valores DSCP

Network Monitor es una herramienta que se puede [descargar de Microsoft](https://www.microsoft.com/download/4865) para analizar el tráfico de red.

1.  En el equipo que ejecuta el Monitor de red, conecte el puerto al que se ha configurado para la duplicación de puertos y capturar paquetes de inicio. 

2.  Realizar una llamada utilizando el Skype para cliente de empresa. Asegúrese de que los medios se ha establecido antes de colgar la llamada. 

3.  Detener la captura.

4. En el campo de **Filtro de visualización** , utilice la dirección IP de origen del equipo que realizó la llamada y refinar el filtro definiendo el valor DSCP 46 (hex 0xb8) como criterios de búsqueda, como se muestra en el ejemplo siguiente:

    Source == "192.168.137.201" AND IPv4.DifferentiatedServicesField == 0xb8 

    ![Captura de pantalla del cuadro de diálogo Filtro de visualización en el Monitor de red, mostrando los filtros para aplicarlos.] (media/Qos-in-Teams-Image4.png "Captura de pantalla del cuadro de diálogo Filtro de visualización en el Monitor de red, mostrando los filtros para aplicarlos.")

5.  Seleccione **Aplicar** para activar el filtro.

6.  En la ventana **Resumen de marco** , seleccione el primer paquete UDP.

7.  En la ventana de **Detalles de las tramas** , expanda el elemento de lista de IPv4 y anote el valor al final de la línea que comienza con el **DSCP**. 

    ![Captura de pantalla del cuadro de diálogo Detalles de tramas de Monitor de red, resaltando valores DSCP.] (media/Qos-in-Teams-Image5.png "Captura de pantalla del cuadro de diálogo Detalles de tramas de Monitor de red, resaltando valores DSCP.")

En este ejemplo, se establece el valor de DSCP a 46. Esto es correcto, ya que utiliza el puerto de origen es 50019, lo que indica que se trata de una carga de trabajo de voz. 

Repita la verificación para cada carga de trabajo que marque el GPO. 
