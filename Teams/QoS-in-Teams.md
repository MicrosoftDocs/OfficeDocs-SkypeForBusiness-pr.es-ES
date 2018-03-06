---
title: Calidad de servicio (QoS) en Microsoft Teams
author: rmw2890
ms.author: MyAdvisor
manager: Serdars
ms.date: 02/16/2018
ms.topic: article
ms.service: msteams
description: "Prepare la red de su organización para la calidad de servicio (QoS) en Microsoft Teams."
MS.collection: Strat_MT_TeamsAdmin
ms.openlocfilehash: 61bebd64c7d1478c16e114631b696dee2bf59625
ms.sourcegitcommit: 85105cb4e42ae8eb6e7e76eaf6d4dd5b9568cf41
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2018
---
<a name="quality-of-service-qos-in-microsoft-teams"></a>Calidad de servicio (QoS) en Microsoft Teams
==========================================
Esta guía le ayudará a preparar la red de su organización para la calidad de servicio (QoS) en Teams.


La calidad de servicio (QoS) es un mecanismo que le permite priorizar determinados tipos de tráfico de red. Es importante priorizar el tráfico para servicios de comunicaciones en tiempo real, como Teams, para poder ofrecer una experiencia de usuario de tipo empresarial. Para que QoS sea realmente efectiva, se debe configurar una conexión de un extremo a otro que sea capaz de implementar la calidad de servicio (PC, conmutadores de red y enrutadores a la nube), puesto que, si alguna de las partes del recorrido falla al respaldar la QoS, la calidad de toda la llamada se podría ver afectada.


![Captura de pantalla de un diagrama donde se ilustra la relación entre las redes de una organización y los servicios de Office 365.](media/Qos-in-Teams-Image1.png)

 

En la mayoría de los casos, la red de interconexión será una red sin administrar, una conexión de Internet. Una opción disponible para abordar la QoS de un extremo a otro es [ExpressRoute](https://azure.microsoft.com/documentation/articles/expressroute-introduction/). Nuestra recomendación sigue siendo implementar QoS en las partes de la red que usted controle, concretamente en su red local. De este modo se incrementa la calidad de las cargas de trabajo de comunicación en tiempo real a través de la implementación y se mitigan los puntos de contención de su implementación actual. 

## <a name="objectives"></a>Objetivos 

Esta guía se centra en cómo se prioriza el tráfico de comunicaciones en tiempo real de Teams, principalmente voz y vídeo. También se pueden priorizar otros tipos de tráfico en función de sus necesidades.

Existen diversos métodos para priorizar el tráfico, pero el más común consiste en usar marcados de punto de código de servicios diferenciados (DSCP). Se pueden aplicar en función de los intervalos de puertos, pero también a través de objetos de directiva de grupo. Se cubrirán ambos métodos en este documento.

Al controlar el marcado de DSCP a través de los objetos de directiva grupo (GPO) se garantiza que los equipos unidos a un dominio reciban la configuración correcta y que esos ajustes solo los pueda gestionar un administrador. 

Es importante saber que QoS solo funciona cuando se implementa en todos los vínculos que conectan a la persona que llama con el destinatario. Si usamos QoS en la red interna y un usuario inicia sesión desde una ubicación remota, solo se podrá priorizar dentro de nuestra red interna y administrada. Si bien las ubicaciones remotas podrían recibir una conexión administrada al implementar una VPN, no se recomienda ejecutar tráfico de comunicaciones en tiempo real a través de la VPN.

> [!NOTE]
> Nuestra recomendación es implementar la tunelización dividida para usuarios remotos conectados por VPN para lograr la mejor experiencia posible del usuario. Consulte el documento [Implementar-Guía-Túnel dividido de VPN](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_9 ) para obtener más información.

En una organización global con vínculos administrados que abarcan continentes, se recomienda encarecidamente utilizar QoS, puesto que el ancho de banda es limitado en comparación con la red local (LAN).

## <a name="quality-of-service"></a>Calidad de servicio

Para poder proporcionar un nivel de servicio garantizado para una aplicación de la red, los dispositivos de red subyacentes deben tener una forma de poder clasificar los diferentes tipos de tráfico. Un enrutador, por ejemplo, debe poder distinguir entre tráfico de voz y tráfico de navegador web normal, si se espera que la voz reciba un mejor tratamiento. 

Los servicios diferenciados (DiffServ) proporcionan un marco en el que los dispositivos de red manejan el tráfico con prioridades que se basan en el campo del tipo de servicios (ToS) del encabezado de un paquete IPv4/IPv6. Los seis bits más significativos del campo DiffServ se conocen como el punto de código de servicios diferenciados o DSCP. Con este marco, el tráfico se puede clasificar como un tipo particular de tráfico (voz) y después marcarse (101110 o 46 en decimal), de manera que cuando los dispositivos de red procesan estos marcados, el tráfico se puede priorizar en consecuencia (desvío rápido, en este ejemplo).

Cuando el tráfico de red pasa por un enrutador, el tráfico se sitúa en una cola. En caso de no haber QoS implementado, básicamente existe solo una cola y los datos se tratan con el principio de que el primero en entrar es el primero en salir. Eso significa que el tráfico de voz (donde es probable que se produzcan retrasos) podría quedarse detenido detrás del tráfico de los servicios de transmisión en línea. Cuando se implementa QoS, se pueden definir varias colas con distintas características para administrar la congestión (como la cola de prioridades de Cisco ["Priority Queuing", PQ] y la cola de espera equitativa y ponderada basada en clases ["Class Based Weighted Fair Queue", CBWFQ]) y características para evitar la congestión (como la detección anticipada aleatoria ponderada ["Weighted Random Early Detection", WRED]).

![Captura de pantalla de un diagrama donde se ilustran las colas de QoS en Teams.](media/Qos-in-Teams-Image2.png)

Figura 1: Colas de QoS visualizadas

Una vez que todas estas piezas están colocadas en su sitio, se puede ofrecer un nivel de calidad de servicio predecible, ya que la red administrada subyacente sabe cómo hay que clasificar, marcar y priorizar el tráfico. Desde la perspectiva de Teams, el elemento más importante de la configuración es la clasificación y el marcado de los paquetes, si bien también hay que realizar una cuidadosa planificación para poder alinear la configuración de la aplicación con la configuración de red subyacente y que el QoS de un extremo a otro se realice correctamente.

## <a name="qos-scenarios"></a>Escenarios de QoS

A la hora de implementar QoS para Teams, hemos basado nuestras instrucciones en cuatro escenarios de partida:

1.  Ha implementado o está implementando Teams y tiene pensado implementar QoS a través del etiquetado basado en puertos. El etiquetado basado en puertos es el método más fiable, puesto que funciona de manera universal en todas las plataformas y es el más fácil de implementar. 

2.  Ha implementado o está implementando Teams y tiene pensado implementar QoS a través del etiquetado de objetos de directiva de grupo. Este método se usa en ocasiones en combinación con el escenario 1. Si bien este escenario es completamente válido y se describe más adelante, es importante saber que solo funcionará para clientes Windows unidos a un dominio. Cualquier otro dispositivo que no sea un cliente Windows unido a un dominio no se habilitará para el etiquetado QoS/DSCP. 

3.  Ha implementado Skype Empresarial Online con el etiquetado QoS y ahora está implementando Teams. Si ese es su caso, Teams respetará la configuración existente y usará los mismos intervalos de puertos y el mismo etiquetado que el cliente de Skype Empresarial. No será necesario utilizar ninguna otra configuración adicional. 
    > [!NOTE]
    > Si está usando el etiquetado QoS de nombre de aplicación a través de la directiva de grupo, debería agregar “Teams.exe” como el nombre de la aplicación.
4.  Ha implementado Teams o lo está implementando y quiere implementar QoS a través del etiquetado basado en puertos con un intervalo de puertos personalizado.

## <a name="recommended-differentiated-services-code-point-dscp-markings"></a>Marcados de punto de código de servicios diferenciados (DSCP) recomendados

El primer paso consiste en clasificar los flujos de tráfico (como el audio y el vídeo) evaluando los intervalos de puertos únicos no superpuestos con un valor de DSCP. El valor de DSCP que se asigne aquí determinará la prioridad del tráfico que pasará por la red (en función de la configuración de red). Cada carga de trabajo obtiene su propio valor de DSCP, aunque algunos clientes podrían establecer el mismo valor para la voz y el vídeo, otorgándoles de este modo la misma prioridad en la red. 

El valor de DSCP que se use dependerá de la prioridad que se dé a cada carga de trabajo. Por ejemplo, los requisitos empresariales podrían dictar que el uso compartido de aplicaciones se trate con el mismo nivel de prioridad que el vídeo (y, por lo tanto, se marque con el mismo valor de DSCP que el del vídeo). Otros entornos podrían ya contar con una estrategia de QoS. 

En la tabla 1 siguiente se muestran los marcados de DSCP que se requieren cuando se utiliza Teams con ExpressRoute. Podría servir como un buen punto de partida para clientes que no tienen claro qué deben usar en su propio entorno. Para obtener más información, lea [Requisitos de QoS ExpressRoute](https://docs.microsoft.com/azure/expressroute/expressroute-qos).


| Puerto origen del cliente|Protocolo|Categoría del medio|Valor de DSCP común|Clase de DSCP|
|---------|---------|---------|---------|---------|
| 50 000 – 50 019|TCP/UDP|Audio|46|Desvío rápido (EF)|
| 50 020 – 50 039|TCP/UDP|Vídeo|34|Desvío garantizado (AF41)|
| 50 040 – 50 059|TCP/UDP|Compartir aplicaciones/escritorio y transferencia de archivos|18|Selector de clases (CS3)|

Tabla 1: Marcados de DSCP

Hay que tener en cuenta algunas cosas cuando se use la información de la tabla 1:

- El uso compartido de archivos y el uso compartido de aplicaciones emplean el mismo intervalo de puertos de origen y, por lo tanto, usarían los mismos marcados de DSCP cuando se utilice el etiquetado basado en puertos. Por este motivo, se debería determinar qué prioridad habría que aplicar mayormente a *ambas* modalidades (interactiva o predeterminada).
    
- Si hay un plan para implementar ExpressRoute en el futuro y QoS no se ha implementado todavía, lo más recomendable es seguir las indicaciones anteriores para que los valores de DSCP sean los mismos del remitente para el receptor. 
    
## <a name="source-ports-used-by-teams"></a>Puertos de origen que usa Teams

En Teams, QoS se debe configurar en función de los puertos de origen que utilizan las diferentes cargas de trabajo. Los intervalos de puertos del servidor y los del cliente no son configurables en este punto. 

Para implementar QoS, use los intervalos de puertos de origen del cliente que se enumeran en la tabla 2, con los marcados de DSCP del QoS asociados.

| Puerto origen del cliente|Protocolo|Categoría del medio|Valor de DSCP común|Clase de DSCP|
|---------|---------|---------|---------|---------|
| 50 000 – 50 019|TCP/UDP|Audio|46|Desvío rápido (EF)|
| 50 020 – 50 039|TCP/UDP|Vídeo|34|Desvío garantizado (AF41)|
| 50 040 – 50 059|TCP/UDP|Compartir aplicaciones/escritorio y transferencia de archivos|18|Selector de clases (CS3)|

Tabla 2: Intervalos de puertos de origen del cliente

> [!NOTE]
> Si ya ha configurado QoS en función de los intervalos de puertos de origen para Skype Empresarial Online, se aplicará la misma configuración en Teams sin que haga falta ningún otro cambio. Si ya ha implementado Skype Empresarial Server (en local), tendrá que volver a diseñar sus directivas de QoS.

## <a name="setting-differentiated-services-code-point-dscp-markings"></a>Configuración de marcados de punto de código de servicios diferenciados (DSCP)

Hay muchas formas de configurar los marcados de DSCP adecuados para llevar a cabo la clasificación del tráfico.

- El marcado de DSCP en el punto de conexión: esta es la opción que se prefiere en general, ya que el mismo punto de conexión proporciona los marcados adecuados. En este momento esto se podría conseguir con un GPO, pero solo es posible en clientes Windows unidos a un dominio. Los clientes móviles o Mac OSX, por ejemplo, no proporcionan un mecanismo que pueda marcar el tráfico con valores de DSCP.

- Basado en puertos con listas ACL en enrutadores: es una opción muy común en entornos heterogéneos de Windows y Mac. En este escenario, el equipo de red marca el tráfico en los enrutadores de entrada/salida (normalmente en la red de área extensa [WAN]) en función de los intervalos de puertos de origen definidos para cada modalidad. Si bien esto funciona en todas las plataformas, solo marca en el extremo WAN (no en todo el trayecto hasta el equipo cliente) e incurre en sobrecarga de administración.
    
- Una combinación de marcados de DSCP en el cliente y listas ACL basadas en puertos en los enrutadores.
    
Si es posible, se recomienda una combinación de ambos y, de ese modo, usar un GPO para filtrar la mayoría de clientes y usar también el etiquetado DSCP basado en puertos para garantizar que los clientes móviles, los Mac y otros clientes seguirán obteniendo una tratamiento de QoS (parcial).

Para configurar el valor de DSCP para el intervalo de puertos de origen predefinido en el cliente de Teams, se puede usar QoS basado en directivas dentro de la directiva de grupo. En la siguiente tabla se usan los intervalos de puertos especificados en la tabla para crear una directiva para cada carga de trabajo.

| Tipo de tráfico del cliente|Inicio del intervalo de puertos|Fin del intervalo de puertos|Valor de DSCP|
|---------|---------|---------|--------|
| Audio|50000|50019|46|
| Vídeo|50020|50039|34|
| Uso compartido de aplicaciones|50040|50059|18|
| Transferencia de archivos|50040|50059|18|

Tabla 3: Intervalos de puertos según el tipo de tráfico

Nota: Los intervalos de puertos que establece Teams no se pueden modificar ni alterar. Revisa esta página para ver la última información al respecto: https://support.microsoft.com/kb/2409256

Una vez que los intervalos de puertos se han determinado, el siguiente paso consiste en configurar las opciones de QoS basado en directivas dentro de un objeto de directiva de grupo (GPO). Los detalles de los pasos siguientes se pueden encontrar en [TechNet](https://technet.microsoft.com/library/jj205371(v=ocs.15).aspx). 

Las nuevas directivas que ha creado no surtirán efecto hasta que la directiva de grupo se haya actualizado en los equipos cliente. Aunque la directiva de grupo se actualiza periódicamente por sí misma, se puede forzar una actualización inmediata si se ejecuta el siguiente comando en cada equipo en el que se tenga que actualizar la directiva de grupo:

        gpudate.exe /force

Este comando se puede ejecutar desde cualquier ventana de comandos que se ejecute con las credenciales del administrador. Para abrir una ventana de comandos con las credenciales del administrador, haga clic en **Inicio**, haga clic con el botón derecho en **Símbolo del sistema** y, a continuación, haga clic en **Ejecutar como administrador**.

## <a name="verifying-the-dscp-markings-in-gpo"></a>Verificación de los marcados de DSCP en GPO

Para verificar que se hayan establecido los valores del GPO, lleve a cabo estos pasos:

1.  Use gpresult para verificar que el PC local haya recibido la configuración del GPO. gpresult /R >gp.txt generará un informe y lo enviará a un archivo de texto, gp.txt.

    ![Captura de pantalla del símbolo del sistema del administrador donde se ejecuta el comando gpresult.](media/Qos-in-Teams-Image3.png)

    Figura 2: Verificación aplicada a los objetos de directiva de grupo
    > [!NOTE]
    > Otra opción consiste en ejecutar gpresult /H gp.html para generar los mismos datos en un informe HTML que el usuario entienda con mayor facilidad. 
2.  En el archivo generado, busque el título: Applied Group Policy Objects (Objetos de directiva de grupo aplicados) y compruebe que los nombres de los GPO creados anteriormente están en la lista de directivas aplicadas. 

3.  Abra el editor de registro y acceda a:

    HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\QoS\

    Compruebe los valores del registro que aparecen en la tabla 3 siguiente.
    
    | Nombre | Tipo | Datos|
    |---------|---------|---------
    | Nombre de la aplicación|REG_SZ|Teams.exe|
    | Valor de DSCP|REG_SZ|46|
    | IP local|REG_SZ|*|
    | Longitud del prefijo de IP local|REG_SZ|*|
    | Puerto local|REG_SZ|50000-50019|
    | Protocolo|REG_SZ|*|
    | IP remota|REG_SZ|*|
    | Prefijo de IP remota|REG_SZ|*|
    | Puerto remoto|REG_SZ|*|
    | Velocidad de limitación|REG_SZ|-1|
    
    Tabla 3: Valores del Registro de Windows para QoS

4.  Compruebe que el nombre de la aplicación sea correcto para el cliente que está usando y compruebe que el valor de DSCP y el del puerto local reflejan la configuración del GPO.

## <a name="validating-qos-analyzing-teams-traffic-on-the-network"></a>Validación de QoS: análisis del tráfico de Teams en la red

El valor de DSCP que establece el GPO tiene que estar presente desde la persona que llama al destinatario para que QoS sea eficaz. Si nos fijamos en el tráfico que genera el cliente de Teams, podemos verificar que el DSCP no ha cambiado ni se ha seccionado al atravesar la red. 

Preferiblemente, capturaríamos el tráfico en el punto de entrada de la red. La creación de reflejos del puerto se puede usar en un conmutador o un enrutador para ayudar a capturar el tráfico en la red. 

### <a name="looking-at-network-traffic-using-network-monitor"></a>Verificación del tráfico de red con Monitor de red

Monitor de red es una herramienta que puede descargarse desde Microsoft para analizar el tráfico de red. Descargue [Monitor de red 3.4](https://www.microsoft.com/download/4865).

Conecte el PC que ejecuta Monitor de red al puerto que se ha configurado para la creación de reflejos de puertos y comience a capturar paquetes. Haga una llamada con el cliente de Skype Empresarial. Asegúrese de que los medios se han establecido antes de colgar la llamada. Al detener la captura, se crea un filtro de visualización que coincide con el IP de origen del PC que hizo la llamada y se restringe el filtro definiendo el valor de DSCP 46 (hex 0xb8) como criterio de búsqueda:

Source == "192.168.137.201" AND IPv4.DifferentiatedServicesField == 0xb8 

![Captura del cuadro de diálogo de visualización del filtro en Monitor de red, donde se muestran los filtros que se van a aplicar.](media/Qos-in-Teams-Image4.png)


Haga clic en **Aplicar** para activar el filtro. En la ventana de **resumen del marco**, seleccione el primer paquete UDP y fíjese en los detalles del marco:

![Captura de pantalla del cuadro de diálogo de detalles del marco en Monitor de red, donde se resalta la configuración de DSCP.](media/Qos-in-Teams-Image5.png)

Amplíe IPv4 y fíjese en el valor que hay al final de la línea de DSCP. En este ejemplo se ve que el valor de DSCP está configurado en 46, lo cual es correcto puesto que el puerto de origen usado es 50019, lo que nos indica que la carga de trabajo es de voz. 

Repita la verificación para cada carga de trabajo que marque el GPO. 

> [!NOTE]
> Compruebe que los marcados atiendan al tráfico punto a punto también. Esto se puede lograr si instala Monitor de red en dos clientes y realiza llamadas entre los dos clientes. Fíjese en el tráfico de medios que fluye entre los clientes como se ha descrito anteriormente.

### <a name="sample-filters-to-use-for-network-monitor-or-wireshark"></a>Ejemplo de filtros que se deben usar para Monitor de red o Wireshark

|Uso  |Ejemplo de filtro  |
|---------|---------|
|Voz (nota: hay que desactivar la multiplexación)     |   udp.port==3479 AND Ipv4.DifferentiatedServicesField.DSCP==46      |
|Vídeo     | udp.port==3480 AND Ipv4.DifferentiatedServicesField.DSCP==34        |
|Pantalla compartida     |  udp.port==3481 AND Ipv4.DifferentiatedServicesField.DSCP==18       |

### <a name="filter-media-traffic-from-microsoft-relays-requires-azure-expressroutehttpsazuremicrosoftcomservicesexpressroute"></a>Filtro: tráfico de medios desde relés de Microsoft (requiere [Azure ExpressRoute](https://azure.microsoft.com/services/expressroute/))

ip.src in {52.114.188.0/22 52.114.220.0/22 52.114.124.0/22 52.114.60.0/22} y (udp.srcport in {3479 3480 3481} o (udp.srcport ge 50000 y udp.srcport lt 60000))

### <a name="filter-media-traffic-to-microsoft-relays"></a>Filtro: tráfico de medios a relés de Microsoft

ip.dst in {52.114.188.0/22 52.114.220.0/22 52.114.124.0/22 52.114.60.0/22} y (udp.dstport en {3479 3480 3481} o (udp.dstport ge 50000 y udp.dstport lt 60000))


Debe consultar el tráfico que se dirige a los relés de Microsoft y que procede de ellos. Puede comprobar los marcados de DSCP en la capa de IP en Wireshark, como se muestra en la próxima sección.

### <a name="expected-dscp-markings"></a>Marcados DSCP esperados

Transmisiones de audio: 46

Transmisiones de vídeo: 34

Transmisiones de datos: 18

### <a name="filter-dscp-condition-to-network"></a>Filtro: condición de DSCP a la red

ip.dsfield.dscp in {46 34 18}



### <a name="looking-at-network-traffic-using-wireshark"></a>Verificación del tráfico de red con Wireshark

Wireshark, https://www.wireshark.org/, es una potente herramienta que nos permite filtrar y registrar los datos de red para poder analizarlos después. Conecte un PC que ejecute Wireshark al puerto que se ha configurado para la creación de reflejos de puertos y comience a capturar paquetes. Haga una llamada con el cliente de Teams. Asegúrese de que los medios se han establecido antes de colgar la llamada.

Detenga el seguimiento del paquete y cree un filtro que solo muestre la IP de origen del PC en el que el cliente de Teams está instalado; por ejemplo, *ip.src_host == 192.168.137.201*, y busque paquetes que usen un puerto de origen del intervalo especificado para la voz: 50 000 – 50 019:

![Captura de pantalla de Wireshark con la configuración del filtro.](media/Qos-in-Teams-Image6.png)
 

Marque el paquete y expanda el encabezado del protocolo de Internet versión 4 (IPV4) en el panel de detalles del paquete:

![Captura de pantalla de Wireshark con la configuración de marcados de punto de código de servicios diferenciados resaltada.](media/Qos-in-Teams-Image7.png)
 

Compruebe que el valor del *punto de código de servicios diferenciados* coincide con el valor de la carga de trabajo especificada que, en este caso, es 46 (101110 binario) para la voz.

Repita la verificación para cada carga de trabajo que marque el GPO.

> [!NOTE]
> Compruebe que los marcados atiendan al tráfico punto a punto. Esto se puede lograr si instala WireShark o Monitor de red en dos clientes y realiza llamadas entre los dos clientes. Fíjese en el tráfico de medios que fluye entre los clientes como se ha descrito anteriormente.

## <a name="summary"></a>Resumen

Calidad de servicio es una pieza fundamental del puzle que se crea cuando se quieren proporcionar experiencias de tipo empresarial con Teams. Sin embargo, también es fundamental recordar que QoS solo es eficaz en redes administradas correctamente. De ese modo, el equipo de implementación debe trabajar mano a mano con los equipos de redes y, así, garantizar que la información adecuada pasa a la capa de red, idealmente administrada de un extremo a otro.

