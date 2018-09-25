---
title: Calidad de servicio en los equipos de Microsoft - equipos de Microsoft
author: rmw2890
ms.author: MyAdvisor
manager: Serdars
ms.date: 04/23/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
description: Prepare la red de su organización para la calidad de servicio (QoS) en Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
MS.collection: Teams_ITAdmin_PracticalGuidance
appliesto:
- Microsoft Teams
ms.openlocfilehash: a219226ca5fa7664cc83539ee4faeb9f57125c00
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/25/2018
ms.locfileid: "25013300"
---
# <a name="quality-of-service-qos-in-microsoft-teams"></a>Calidad de servicio (QoS) en Microsoft Teams

En este artículo le ayudará a preparar la red de su organización para calidad de servicio (QoS) en Microsoft Teams.
QoS es un mecanismo que utilizar para dar prioridad a determinados tipos de tráfico de red. Asignar prioridades a los el tráfico para servicios de comunicaciones en tiempo real, como los equipos es importante para ofrecer una experiencia de usuario a nivel empresarial. Para que QoS ser verdaderamente eficaces, debe configurar una conexión con capacidad de QoS desde final a final (PC, conmutadores de red y los enrutadores a la nube), ya que cualquier parte de la ruta de acceso que se produce un error para admitir QoS puede reducir la calidad de toda la llamada.

![La relación entre una organización redes y servicios de Office 365: local de red y dispositivos que se conectan con una red de interconexión, lo que a su vez se conecta con los servicios de voz de Office 365 en la nube y conferencias de Audio.] (media/Qos-in-Teams-Image1.png "La relación entre una organización redes y servicios de Office 365: local de red y dispositivos que se conectan con una red de interconexión, lo que a su vez se conecta con los servicios de voz de Office 365 en la nube y conferencias de Audio.")

_En la figura 1. La relación entre una organización redes y servicios de Office 365_
 

En la mayoría de los casos, la red de interconexión será una conexión a internet no administrado de red. Una opción disponible para QoS to-end de direcciones es [ExpressRoute de Azure](https://azure.microsoft.com/documentation/articles/expressroute-introduction/). Aun así, es recomendable que implemente QoS en las partes de la red que tenga control sobre, es decir, la red local. Esto aumentará la calidad de las cargas de trabajo de comunicación en tiempo real en toda la implementación y mitigar los puntos de restricción en la implementación existente. 


## <a name="prioritize-teams-network-traffic-for-qos"></a>Establecer prioridades para el tráfico de red de los equipos para QoS 

En este artículo se centra en cómo dar prioridad al tráfico de comunicaciones en tiempo real de los equipos, es decir, voz y vídeo. También puede dar prioridad a otros tipos de tráfico, según sus necesidades.

Existen diversos métodos para priorizar el tráfico, pero el más común consiste en usar marcados de punto de código de servicios diferenciados (DSCP). Se pueden aplicar ("con etiqueta") en función de los intervalos de puertos y también a través de objetos de directiva de grupo. Trataremos ambos tipos en este artículo. Se recomienda que use etiquetas temáticas según los intervalos de puertos debido a que funcionará para todos los dispositivos, no sólo los que se unen al dominio.

Controlar el marcado DSCP a través de objetos de directiva de grupo se asegura de que los equipos unidos a un dominio reciben la configuración correcta y que sólo un administrador puede administrarlos.
 
Es importante comprender que QoS sólo funciona cuando se implementa en todos los vínculos que se conectan el autor de la llamada al destinatario de la llamada. Si utiliza QoS en la red interna y un usuario inicia sesión desde una ubicación remota, sólo puede dar prioridad a dentro de la red interna, administrada. Aunque las ubicaciones remotas pueden recibir una conexión administrada mediante la implementación de una red privada virtual (VPN), se recomienda que evite la ejecución de tráfico de comunicaciones en tiempo real a través de la VPN.

> [!NOTE]
> Se recomienda que implemente túnel dividido para que usuarios remotos conectados a VPN maximizar la calidad de la experiencia del usuario. Descargue el documento [Deploy de orientación-VPN dividido túnel](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_9 ) desde MyAdvisor para obtener más información.

En una organización global con vínculos administradas que abarcan continentes, es absolutamente recomendable QoS debido a que el ancho de banda para esos vínculos es limitado en comparación con la LAN.

## <a name="qos-queues"></a>Colas de QoS

Para proporcionar un nivel de servicio para una aplicación garantizado en la red, los dispositivos de red subyacente deben tener una forma de clasificar distintos tipos de tráfico. Si su organización desea dar prioridad de tráfico de voz a través de otro tipo de tráfico, un enrutador (por ejemplo) debe ser capaz de distinguir entre el tráfico de voz y el tráfico de exploración web normal. 

Servicios diferenciados (DiffServ) proporciona un marco de trabajo en el que se concede diferente prioridad al tráfico los dispositivos de red en función del tipo de campo de servicios (ToS) en el encabezado de un paquete IPv4 o IPv6. Los seis bits más significativos del campo DiffServ son el punto de código de servicios diferenciados o DSCP. Con este marco de trabajo, el tráfico puede se clasifica como un tipo concreto de tráfico (por ejemplo, voz) y, a continuación, marca (101110 o 46 en decimal para el tráfico de voz), para que cuando estas marcas del proceso de dispositivos de red, el tráfico se puedan prioriza según corresponda () Desvío rápido, en este ejemplo).

Cuando el tráfico de red entra en un enrutador, el tráfico se coloca en una cola, si no hay ningún QoS en su lugar, básicamente hay sólo una cola y los datos se tratan como, primero en salir. Esto significa que el tráfico de voz (que es muy sensible a los retrasos) es posible que se bloquee detrás de tráfico de servicios en línea de transmisión por secuencias. Cuando la implementación de QoS, puede definir varias colas mediante el uso de las características de administración de congestión diferentes (por ejemplo, de Cisco colas de prioridad y basada en la clase promedio ponderado razonable cola [CBWFQ]) y las características de prevención de congestión (por ejemplo, promedio ponderado [aleatorio de detección temprana WRED]).

![El ancho de banda disponible total se divide entre varias colas: audio, vídeo y otro tipo de tráfico, que se han asignado prioridades diferentes.] (media/Qos-in-Teams-Image2.png "El ancho de banda disponible total se divide entre varias colas: audio, vídeo y otro tipo de tráfico, que se han asignado prioridades diferentes.")

_La figura 2. Colas de QoS visualizadas_

Después de que estas piezas están en su lugar, es posible entregar predecible QoS debido a que la red administrada subyacente ahora sabe cómo clasificar, marcar y establecer prioridades de tráfico. Desde la perspectiva de los equipos, el paso de configuración más importante es la clasificación y el marcado de paquetes, pero para que QoS to-end a realizarse correctamente también necesita alinear cuidadosamente la configuración de la aplicación con la configuración de red subyacente.

## <a name="teams-qos-scenarios"></a>Escenarios de QoS de equipos

Las instrucciones para la implementación de QoS para equipos se basan en cuatro situaciones:

*  **Escenario 1:** Ha implementado, o va a implementar, los equipos y planea sobre la implementación de QoS a través de etiquetado basado en puerto. Basado en el puerto etiquetado es el método más confiable, ya que funciona en todo el mundo a lo largo de todas las plataformas y es más fácil de implementar.  

*  **Escenario 2:** Ha implementado, o va a implementar, los equipos y planean implementar QoS a través de etiquetado del objeto de directiva de grupo. Este método se usa en ocasiones en combinación con el escenario 1. Aunque este escenario es totalmente válido, es importante comprender que solo funciona para los clientes Unidos a un dominio de Windows. Cualquier dispositivo que no es un cliente de Windows unido a un dominio no estará activado para DSCP etiquetado.

*  **Escenario 3:** Ha implementado Skype para profesionales Online, incluido el etiquetado de QoS y ahora están implementando los equipos. Si ese es su caso, Teams respetará la configuración existente y usará los mismos intervalos de puertos y el mismo etiquetado que el cliente de Skype Empresarial. En la mayoría de los casos, no se necesitarán ninguna configuración adicional. 
 
    > [!NOTE]
    > Si utiliza QoS de nombre de aplicación de etiquetas temáticas a través de directiva de grupo, debe agregar Teams.exe como el nombre de la aplicación.

*  **Escenario 4:** Ha implementado, o va a implementar, los equipos y desea implementar QoS a través de basado en el puerto etiquetado mediante el uso de un intervalo de puertos personalizados.

## <a name="recommended-dscp-markings"></a>Marcas de DSCP recomendados

El primer paso es clasificar los flujos de tráfico (como audio y vídeo) mediante la asignación de valores de DSCP para los intervalos de puertos único, no se superpongan. El valor DSCP asignado aquí determinará la prioridad del tráfico que pasa a través de la red, en función de la configuración de red. Cada carga de trabajo obtiene su propio valor DSCP, aunque no necesariamente un valor único, es posible que algunos clientes establecer el mismo valor para las cargas de trabajo de voz y vídeo, para concederles la misma prioridad en la red.  

El valor de DSCP para usar depende de cómo desea dar prioridad a la carga de trabajo. Por ejemplo, es posible que determinan los requisitos empresariales que dar a aplicación de uso compartido de la misma prioridad que el vídeo (y, por tanto, se marca con el mismo valor DSCP como vídeo). Otros entornos podrían tener una estrategia de QoS existente en su lugar, que le ayudarán a determinar la prioridad de las cargas de trabajo de la red. 

La tabla 1 muestra las marcas DSCP necesarias cuando usa los equipos con ExpressRoute. Estas marcas pueden servir como un buen punto de partida para los clientes que no están seguro de qué se va a utilizar en sus propios entornos. Para obtener más información, lea [Requisitos de QoS ExpressRoute](https://docs.microsoft.com/azure/expressroute/expressroute-qos).


_La tabla 1. Marcados de DSCP_
    
| Intervalo de puertos de origen de cliente |Protocolo|Categoría del medio|Valor de DSCP|Clase de DSCP|
|---------|---------|---------|---------|---------|
| 50.000 – 50,019|TCP/UDP|Audio|46|Desvío rápido (EF)|
| 50,020 – 50,039|TCP/UDP|Vídeo|34|Desvío garantizado (AF41)|
| 50,040 – 50,059|TCP/UDP|Uso compartido de aplicaciones y escritorio|18|Reenvío (AF21) asegurado|

Hay que tener en cuenta algunas cosas cuando se use la información de la tabla 1:
    
-  Si piensa implementar ExpressRoute en el futuro y aún no ha implementado QoS, se recomienda que siga las instrucciones en la tabla 1 para que los valores DSCP son los mismos del remitente al receptor. 

-  Todos los clientes, incluidos los clientes móviles y dispositivos de los equipos, va a usar estos intervalos de puertos y se verán afectados por implementar cualquier directiva DSCP que usa estos intervalos de puerto de origen. Los únicos clientes que seguirán usando puertos dinámicos son los clientes basados en explorador (es decir, los clientes que permiten que los participantes unirse a reuniones mediante sus exploradores).

-  Aunque el cliente de Mac usar los mismos intervalos de puertos, el cliente de Mac también usa valores codificado de forma rígida para (EF) de audio y vídeo (AF41). Estos valores no son configurables.
 
    
## <a name="source-ports-used-by-teams"></a>Puertos de origen que usa Teams

En Teams, QoS se debe configurar en función de los puertos de origen que utilizan las diferentes cargas de trabajo. Ninguno de los dos intervalos de puertos de servidor ni de cliente son configurables actualmente. 

Tenga en cuenta los intervalos de puertos de origen de cliente que aparecen en la tabla 2 y usar sus marcas DSCP QoS asociadas.

_Tabla 2. Intervalos de puertos de origen de cliente_

| Intervalo de puertos de origen de cliente |Protocolo|Categoría del medio|Valor de DSCP|Clase de DSCP|
|---------|---------|---------|---------|---------|
| 50.000 – 50,019|TCP/UDP|Audio|46|Desvío rápido (EF)|
| 50,020 – 50,039|TCP/UDP|Vídeo|34|Desvío garantizado (AF41)|
| 50,040 – 50,059|TCP/UDP|Uso compartido de aplicaciones y escritorio|18|Reenvío (AF21) asegurado|

Es el método recomendado de la implementación de estas directivas de QoS utilizar los puertos de origen del cliente con una dirección IP de origen y de destino de "cualquiera". Esta forma detectará tanto el tráfico de medios entrantes y salientes en la red interna. 

> [!NOTE]
> Si ya ha configurado QoS según los intervalos de puertos de origen para Skype para profesionales en línea, se aplicará la misma configuración a los equipos y no se requerirá ningún cambio adicional. Si ha implementado Skype para Business Server local, debe volver a diseñar las directivas de QoS.

## <a name="setting-dscp-markings"></a>Configuración de marcados de DSCP

Existen varios enfoques para establecer las marcas DSCP adecuadas para la clasificación del tráfico:

-  **El marcado DSCP en el punto final:** Por lo general es la opción preferida, debido a que el propio extremo proporciona los marcadores adecuados. Actualmente esto puede realizarse mediante el uso de un objeto de directiva de grupo, pero sólo puede utilizarse en los clientes Unidos a un dominio de Windows. Los clientes móviles no proporcionan un mecanismo para marcar el tráfico mediante el uso de los valores DSCP. Si bien no se puede configurar que no sean&ndash;unido a un dominio los clientes de Windows para el tráfico de etiqueta, los clientes como Mac OS tienen etiquetas codificado de forma rígida y siempre se etiqueta el tráfico como se describió anteriormente.

-  **DSCP basado en el puerto etiquetado mediante el uso de listas de control de acceso (ACL) en los enrutadores:** Esto es una opción muy comunes encontrada en entornos heterogéneos de Windows y Mac. En este escenario, el equipo de red marca el tráfico en los enrutadores de entrada/salida (normalmente se encuentra en la WAN) en función de los intervalos de puertos de origen definidos para cada modalidad. Aunque esto funciona a través de plataformas, sólo marca el tráfico en el borde WAN: no completamente en el equipo cliente y por lo tanto, incurre en sobrecarga de administración.
    
-  **Una combinación de marcado de DSCP en el extremo y las ACL basadas en puerto en los enrutadores:** Se recomienda esta combinación, si es posible en su entorno. Utilice un objeto de directiva de grupo para detectar la mayoría de los clientes y también usan DSCP basado en el puerto etiquetado para asegurarse de que mobile, Mac y otros clientes seguirán recibiendo tratamiento de QoS (por lo menos parcialmente).
    
Puede usar QoS basada en Directiva dentro de la directiva de grupo para establecer el valor de DSCP para el intervalo de puertos de origen predefinido en el cliente de los equipos. Usar los intervalos de puertos especificados en la tabla 3 para crear una directiva para cada carga de trabajo.

_Tabla 3. Intervalos de puertos por tipo de tráfico_
| Tipo de tráfico del cliente|Inicio del intervalo de puertos|Fin del intervalo de puertos|Valor de DSCP|
|---------|---------|---------|--------|
| Audio|50000|50019|46|
| Vídeo|50020|50039|34|
| Uso compartido de aplicaciones|50040|50059|18|

> [!NOTE]
> Los intervalos de puertos establecidos los equipos que no se puede cambiar. Revise [este artículo del soporte técnico](https://support.microsoft.com/kb/2409256) para obtener la información más reciente. 

Una vez que ha identificado los intervalos de puertos, el siguiente paso es configurar la configuración de QoS basada en Directiva dentro de un objeto de directiva de grupo. Para obtener más información acerca de estos pasos puede encontrarse en [este artículo de TechNet](https://technet.microsoft.com/library/jj205371(v=ocs.15).aspx). 

Las nuevas directivas que se ha creado no surtirán efecto hasta que se ha actualizado la directiva de grupo en los equipos cliente. Aunque la directiva de grupo se actualiza periódicamente en su propio, puede forzar una actualización inmediata.

### <a name="force-group-policy-refresh"></a>Actualización de la directiva de grupo Force

1. En cada equipo para el que desea actualizar la directiva de grupo, abra una consola de comandos. Asegúrese de que la consola de comandos está establecida en Ejecutar como administrador.

2. En el símbolo del sistema, escriba
```
    gpudate.exe /force
```

## <a name="verify-dscp-markings-in-the-group-policy-object"></a>Compruebe los marcados de DSCP en el objeto de directiva de grupo

Para comprobar que se han establecido los valores desde el objeto de directiva de grupo, realice los pasos siguientes.

1.  Abra una consola de comandos. Asegúrese de que la consola de comandos está establecida en Ejecutar como administrador.

2.  En el símbolo del sistema, escriba 
    ```
    gpresult /R >gp.txt
    ```

    Esto generará un informe y enviarlo a un archivo de texto denominado gp.txt. Como alternativa, puede escribir el comando siguiente para generar los mismos datos en un informe HTML más legible llamado gp.html:
    ```
    gpresult /H >gp.html
    ```
 
   ![Captura de pantalla de la ventana de la consola que se ejecuta el comando gpresult.] (media/Qos-in-Teams-Image3.png "Captura de pantalla de la ventana de la consola que se ejecuta el comando gpresult.")

3.  En el archivo generado, busque el encabezado **Aplica objetos de directiva de grupo** y compruebe que los nombres de los objetos de directiva de grupo que creó anteriormente están en la lista de directivas aplicadas. 

4.  Abra el Editor del registro y vaya a:

    HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\QoS\

    Compruebe los valores de las entradas del registro que aparecen en la tabla 3.

    _Tabla 3. Valores de las entradas del registro de Windows para QoS_
    
    | Nombre | Tipo | Datos|
    |---------|---------|---------
    | Nombre de la aplicación|REG_SZ|Teams.exe|
    | Valor de DSCP|REG_SZ|46|
    | IP local|REG_SZ|*|
    | Longitud del prefijo de IP local|REG_SZ|*|
    | Puerto local|REG_SZ|50000-50019|
    | Protocolo|REG_SZ|*|
    | IP remota|REG_SZ|*|
    | Prefijo de dirección IP remota|REG_SZ|*|
    | Puerto remoto|REG_SZ|*|
    | Velocidad de limitación|REG_SZ|-1|
    
5.  Compruebe que es correcto para el cliente que está utilizando el valor de la entrada de nombre de la aplicación y compruebe que el valor de DSCP y el puerto Local entradas reflejan la configuración en el objeto de directiva de grupo.

## <a name="validate-qos-by-analyzing-teams-traffic-on-the-network"></a>Validar QoS mediante el análisis de tráfico de los equipos de la red

El valor DSCP establecido por las necesidades de objeto de directiva de grupo para estar presente de autor de la llamada al destinatario de la llamada en orden para QoS ser eficaces. Mirando el tráfico generado por el cliente de los equipos, puede comprobar que el valor de DSCP no está cambiado o se eliminan cuando el tráfico de carga de trabajo de los equipos atraviesa la red. 

Preferiblemente, capturar el tráfico en el punto de salida de la red. Puede utilizar la duplicación de puertos en un conmutador o enrutador para ayudar con esto.

### <a name="use-network-monitor-to-verify-dscp-values"></a>Utilice el Monitor de red para comprobar los valores DSCP

Monitor de red es una herramienta que se puede [descargar de Microsoft](https://www.microsoft.com/download/4865) para analizar el tráfico de red.

1.  En el PC que ejecuta el Monitor de red, conecte con el puerto en el que se ha configurado para la creación de reflejo de puerto y capturar paquetes de inicio. 

2.  Realizar una llamada mediante el uso de la Skype para clientes empresariales. Asegúrese de que se ha establecido medios antes de colgar la llamada. 

3.  Detenga la captura.

4. En el campo de **Filtro de presentación** , utilice la dirección IP de origen del PC que realizó la llamada y refinar el filtro mediante la definición de valor DSCP 46 (hex 0xb8) como criterios de búsqueda, como se muestra en el ejemplo siguiente:

    Source == "192.168.137.201" AND IPv4.DifferentiatedServicesField == 0xb8 

    ![Captura de pantalla del cuadro de diálogo Filtro de visualización en el Monitor de red, que muestra los filtros que se debe aplicar.] (media/Qos-in-Teams-Image4.png "Captura de pantalla del cuadro de diálogo Filtro de visualización en el Monitor de red, que muestra los filtros que se debe aplicar.")

5.  Seleccione **Aplicar** para activar el filtro.

6.  En la ventana de **Marco de resumen** , seleccione el primer paquete de UDP.

7.  En la ventana de **Marco de detalles** , expanda el elemento de lista IPv4 y tenga en cuenta el valor al final de la línea que comienza con **DSCP**. 

    ![Captura de pantalla del cuadro de diálogo Detalles de las tramas en el Monitor de red, el resaltado de configuración DSCP.] (media/Qos-in-Teams-Image5.png "Captura de pantalla del cuadro de diálogo Detalles de las tramas en el Monitor de red, el resaltado de configuración DSCP.")

En este ejemplo, se establece el valor de DSCP a 46. Esto es correcto, debido a que el puerto de origen usado es 50019, lo que indica que se trata de una carga de trabajo de voz. 

Repita la verificación para cada carga de trabajo que marque el GPO. 
