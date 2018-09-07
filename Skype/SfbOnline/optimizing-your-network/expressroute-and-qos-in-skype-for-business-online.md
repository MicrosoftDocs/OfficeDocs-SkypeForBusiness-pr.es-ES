---
title: ExpressRoute y QoS en Skype Empresarial Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mpottier, dougand
ms.topic: article
ms.assetid: 20c654da-30ee-4e4f-a764-8b7d8844431d
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Optimization
description: 'Learn about using Azure ExpressRoute to have a network with bandwidth requirements and Quality of Service capability for a business class user experience. '
ms.openlocfilehash: 81cc2f0c959bb4c611abc7ff198e6c5befc58c21
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "23865271"
---
# <a name="expressroute-and-qos-in-skype-for-business-online"></a>ExpressRoute y QoS en Skype Empresarial Online

Conéctese a Office 365 a través de una conexión de red dedicada con Azure ExpressRoute para Office 365 y Skype Empresarial Online. Una conexión dedicada para las aplicaciones de Skype Empresarial le proporcionará un rendimiento confiable y predecible, además de la privacidad que no proporciona una conexión de Internet pública. Ahora puede comprar una conexión de red mejor a Office 365 y a Skype Empresarial Online que ofrece predictibilidad y confiabilidad de categoría empresarial, y que incluye un contrato de nivel de servicio de tiempo de actividad.
  
> [!NOTE]
> Hay una nueva versión de la calculadora de ancho de banda que está disponible en [Skype Empresarial, Calculadora de ancho de banda](https://go.microsoft.com/fwlink/?LinkId=715766). Sin embargo, en las instrucciones de este documento se usa la calculadora de ancho de banda de Lync 2010 y 2013. 
  
## <a name="skype-for-business-online-and-expressroute"></a>Skype Empresarial Online y ExpressRoute

Al trabajar con un partner de ExpressRoute de Microsoft, puede conectar una amplia variedad de aplicaciones de Office 365, como Skype Empresarial Online, en la nube a través de una conexión dedicada. Pero las capacidades de comunicaciones de voz y vídeo en tiempo real para Skype Empresarial necesitan servicios de red que se hayan configurado específicamente para admitir estas cargas de trabajo en tiempo real de Office 365. Esto incluye una red que tenga un ancho de banda suficiente para transferir el volumen necesario de tráfico y que sea capaz de admitir una calidad de servicio (QoS), y así poder ofrecer a sus usuarios una experiencia de categoría empresarial.
  
Este documento se ha diseñado para ayudar a los clientes, a los administradores y a los ingenieros de redes a comprender los retos especiales necesarios para admitir las comunicaciones en tiempo real, las herramientas proporcionadas por Microsoft para ayudarle a diseñar una red capaz de admitir estos requisitos y guiarle en los pasos del proceso de diseño con un caso práctico. 
  
En la primera parte de este documento verá un caso práctico que le ayudará a diseñar la red con la [Herramienta de cálculo de ancho de banda de Skype Empresarial](https://go.microsoft.com/fwlink/?LinkId=690282) para calcular los requisitos de red de una implementación de ExpressRoute de Skype Empresarial de gran tamaño y en varios sitios. En la segunda parte de este documento se indican los conceptos fundamentales de Calidad de servicio (QoS), un análisis en profundidad de los detalles técnicos para admitir las comunicaciones en tiempo real de Skype Empresarial, así como los tipos específicos de servicios de red que son necesarios.
  
Aquí encontrará los detalles técnicos e información que le ayudará a comprender QoS, ExpressRoute y los retos específicos a los que se enfrentará, además de conocimientos prácticos de herramientas y técnicas que le permitirán implementar correctamente ExpressRoute en toda su red de Skype Empresarial. 
  
## <a name="getting-started"></a>Introducción

Al prepararse para usar ExpressRoute para Skype Empresarial, es buena idea conocer los diferentes modelos de conexión de ExpressRoute y las diferentes opciones de partners y ubicaciones, además de leer cómo comprar y aprovisionar ExpressRoute en su empresa. Aquí encontrará algunos recursos con los que le resultará más fácil a empezar: 
  
- [Azure ExpressRoute]( https://go.microsoft.com/fwlink/?LinkId=690283)
    
- [Precios de ExpressRoute](https://go.microsoft.com/fwlink/?LinkId=690284)
    
- [Documentación de ExpressRoute](https://go.microsoft.com/fwlink/?LinkId=690285)
    
## <a name="part-1-case-study---expressroute-for-dewey-law-llc"></a>Parte 1: Caso práctico - ExpressRoute paraDewey Law, LLC.

Con este caso práctico de Dewey Law, LLC., aprenderá a configurar una red, solicitar servicios de acceso a la red y determinar los requisitos de ancho de banda para admitir ExpressRoute para Skype Empresarial Online.
  
 **Antecedentes** Dewey Law, LLC. es un bufete de abogados nacional de gran tamaño, con 790 abogados y un total de 5580 empleados repartidos en 78 ubicaciones. El bufete tiene su sede central en Nueva York y tres oficinas regionales en Chicago, San Francisco y Dallas, además de 24 sucursales grandes y 50 sucursales pequeñas repartidas por todo el país. El bufete gestiona casos importantes y complejos, y la carga de trabajo se suele repartir entre dos o más oficinas. Tener este diseño de red genera como resultado una cantidad importante de tráfico de red entre las oficinas.
  
Dewey Law, LLC. es un bufete relativamente nuevo, y los abogados y otros miembros del personal se sienten muy cómodos con la tecnología y dependen en gran medida de ella para su trabajo diario. 
  
 **Distribución de usuarios por ubicaciones y puestos**
  
||**Sede central (NY)**|**Oficinasregionales(3)**|**Sucursalesgrandes(24)**|**Sucursalespequeñas(50)**|
|:-----|:-----|:-----|:-----|:-----|
|Ejecutivos  <br/> |20  <br/> |10  <br/> |1  <br/> |1  <br/> |
|Socios  <br/> |150  <br/> |50  <br/> |10  <br/> |5  <br/> |
|Asociados  <br/> |300  <br/> |100  <br/> |20  <br/> |10  <br/> |
|Asistente jurídico  <br/> |400  <br/> |125  <br/> |30  <br/> |15  <br/> |
|Administradores ejecutivos  <br/> |100  <br/> |35  <br/> |6  <br/> |3  <br/> |
|TI y administrativos generales  <br/> |100  <br/> |25  <br/> |3  <br/> |2  <br/> |
|Total por sitio  <br/> |1.070  <br/> |345  <br/> |70  <br/> |36  <br/> |
|Total por clase de sitio  <br/> |1.070  <br/> |1.035  <br/> |1.680  <br/> |1.800  <br/> |
   
### <a name="setting-up-the-network"></a>Configuración de la red

Para ofrecer servicios en tiempo real coherentes y de alta calidad para Dewey Law, LLC., es necesario que se cumplan dos requisitos básicos:
  
- Quieren prestar servicios de voz durante un error de alimentación, por lo que sus conmutadores y enrutadores de distribución de la red tienen que suministrar alimentación a través de Ethernet (PoE) IEEE 802.3af o 802.3at.
    
- Además, los conmutadores y enrutadores de red también tienen que usar sistemas de alimentación ininterrumpida (SAI) para que puedan continuar funcionando durante un error de alimentación.
    
    Tienen conexiones Wi-Fi en sus oficinas con redes LAN, por lo que es muy recomendable que usen un partner certificado de infraestructura de Wi-Fi de Skype Empresarial de [Soluciones de Skype Empresarial](https://go.microsoft.com/fwlink/?LinkId=690281)
    
    > [!TIP]
    >  Se recomiendan los puntos de acceso inalámbricos 802.11n y 802.11ac.
  
- Además, lo más importante es que se tienen que configurar todas las redes LAN de las oficinas para proporcionar Calidad de servicio (QoS). Esto incluye PC, portátiles y cualquier otro hardware de redes, como conmutadores y enrutadores.
    
Ahora que hemos tratado los conceptos básicos, para ofrecer servicios de voz de categoría empresarial para Dewey Law, LLC. recomendamos usar un servicio IP MPLS (conmutación por etiquetas multiprotocolo) de un partner de servicios de red que se conectará al servicio Azure ExpressRoute. MPLS proporciona un servicio IP con garantías de rendimiento en caso de retraso, vibración y pérdida de paquetes. Pero, si MPLS no está disponible, también se puede usar una conexión Ethernet conectada a uno de nuestros partners de intercambio de datos de ExpressRoute.
  
Los proveedores de MPLS ofrecen varios niveles de clase de servicio, pero cada uno usa diferentes términos para identificarlos. Tendrá que trabajar estrechamente con su proveedor para asegurarse de que comprende los datos que ha especificado en la [Herramienta de cálculo de ancho de banda de Skype Empresarial](https://go.microsoft.com/fwlink/?LinkID=690282) y las opciones disponibles y recomendadas para las diferentes aplicaciones de carga de trabajo en tiempo real de Office 365.
  
Hay dos opciones para asignar los datos de las aplicaciones de Skype Empresarial a las diferentes clases de servicio de MPLS:
  
- Marcado de extremo de tráfico con Punto de código de servicios diferenciados (DSCP)
    
- Basado en lista de control de acceso (ACL) de red
    
Para implementar el marcado de extremo, tiene que configurar todos los equipos Windows que se hayan unido al dominio para Dewey Law, LLC. para marcar cada paquete con el Punto de código de servicios diferenciados (DSCP) y, después, implementar QoS en todos los conmutadores y enrutadores de red de todos los sitios de oficinas para asegurarse de que se mantengan los marcados de QoS y no se eliminen. Los marcados de DSCP en los paquetes de red indican al proveedor de servicios cómo clasificar por orden de prioridad los paquetes de red. **Encontrará más información sobre DSCP en la sección QoS de la parte 2.**
  
Para las asignaciones basadas en ACL de red, los marcados de prioridad de DSCP se implementan en un enrutador de canal de subida y se basan en el puerto UDP de origen. Los intervalos de puertos recomendados para cada aplicación se indican en la sección 2.6.1.1 de [Planificación, supervisión y solución de problemas de red con Skype Empresarial Server](https://go.microsoft.com/fwlink/?LinkId=690286). Es importante que coordine esto con la implementación de QoS general de Dewey Law, LLC. y que diseñe y conozca las diferentes directivas de QoS y los posibles errores de coincidencia de marcado de paquetes.
  
Cada proveedor de servicios de red de ExpressRoute tendrá una clase de servicio (QoS) que sea apropiada para voz y vídeo en tiempo real. Esta COS se llama "desvío rápido" (EF) para voz y "desvío garantizado" (AF) para vídeo. Tenga cuidado al establecer el tamaño de la cantidad de ancho de banda que compre para el tráfico de EF de voz. El motivo es que la clase de servicio de voz puede ocasionar problemas de procesamiento si se envía más tráfico de voz del aprovisionado por la clase de servicio.
  
> [!TIP]
>  Todo el tráfico que se envíe en la clase de servicio de voz que supere el compromiso del proveedor de servicios se descartará inmediatamente, lo que afectará directamente a la calidad de los servicios de voz.
  
Al analizar el diseño general de Dewey Law, LLC., es muy importante que determine de forma precisa la cantidad de ancho de banda de red necesario para admitir el tráfico de voz en toda su red y que marque cada paquete de voz (y solo los paquetes de voz) con la configuración de DSCP para voz (es decir, DSCP EF 46).
  
Para implementar QoS en toda su red empresarial, los extremos o enrutadores tienen que marcar cada paquete con el indicador de prioridad de capa 3 correspondiente (es decir, DSCP). En toda la ruta de red, cada conmutador y enrutador ha de tener activada la opción QoS. Aunque solo haya un conmutador o enrutador de red que no tenga activada QoS, se podrían eliminar las marcas de QoS en los paquetes de voz o vídeo que pasen a través del conmutador o enrutador. De hecho, esto deshabilita QoS en todos los conmutadores y enrutadores de canal de bajada, lo que reduce el valor de tener ExpressRoute.
  
Esto también necesita que la asociación de las prioridades de QoS de las capas 3 y 2 se defina en cada punto. Los mecanismos de prioridad de la capa 2 se definen en IEEE 802.1p para las redes cableadas y en 802.11e/WMM para las redes Wi-Fi. Aún más importante, el enrutador de red al que tenga acceso la red MPLS del proveedor de servicios de red tiene que mantener la configuración DSCP en todos los paquetes de salida para que mantengan la clase de servicio de MPLS adecuada. 
  
> [!TIP]
>  Para conocer los detalles específicos de la configuración de QoS, consulte la sección 2.6 [Planeación de red, seguimiento y solución de problemas con Lync Server]( https://go.microsoft.com/fwlink/?LinkId=760669). También puede ver [Planear los requisitos de red para Skype Empresarial 2015](https://go.microsoft.com/fwlink/?LinkId=690287) para obtener más información sobre los requisitos de planeación de red.
  
### <a name="ordering-network-access-services"></a>Solicitud de servicios de acceso a la red

Cuando tenga preparados los requisitos previos y los mecanismos de red de QoS para admitir ExpressRoute, el paso siguiente es realizar una solicitud de los servicios de acceso a la red de ExpressRoute. Al solicitar los servicios de acceso de ExpressRoute para Dewey Law, LLC. del proveedor de servicios de red que sea partner de Microsoft, tendrá que proporcionar dos cosas:
  
- La cantidad total de ancho de banda necesario para conectar cada sitio a ExpressRoute y Office 365.
    
- El ancho de banda total necesario para cada clase de servicio que sea necesario para admitir las aplicaciones de Skype Empresarial que se usan en Dewey Law, LLC. El requisito de ancho de banda de clase de servicio depende del volumen de tráfico que espere de las diferentes aplicaciones de Skype Empresarial, como voz, vídeo, mensajería instantánea, presencia y pantalla compartida.
    
### <a name="determining-bandwidth-requirements-for-skype-for-business-applications"></a>Determinar los requisitos de ancho de banda para aplicaciones de Skype Empresarial

Para Dewey Law, LLC., después de determinar el ancho de banda total necesario, tendrá que conocer cómo se tiene que dividir dicha cantidad total de ancho de banda entre las diferentes clases de servicio. Por ejemplo, cuánto ancho de banda se tiene que asignar a cada aplicación de Skype Empresarial.
  
Para determinar esos requisitos en cada sitio de Dewey Law LLC., puede usar la [Herramienta de cálculo de ancho de banda de Skype Empresarial](https://go.microsoft.com/fwlink/?LinkID=690282). Esta calculadora es una herramienta basada en Excel que le permite especificar el uso esperado de diferentes aplicaciones de Skype Empresarial, como voz, vídeo, conferencia y pantalla compartida. La calculadora generará automáticamente una estimación de los requisitos de ancho de banda y de CoS para cada sitio de la red. Cuando descargue la Herramienta de cálculo de ancho de banda de Skype Empresarial, también se descargará un manual del usuario, donde encontrará información sobre cómo usarla. 
  
Para ayudarle con la hoja de cálculo, las distintas celdas están codificadas por colores:
  
- **Verde** Son áreas de entrada de datos generales.
    
- **Amarillo** Son áreas de entrada de datos avanzados. Aunque se pueden cambiar, hágalo con precaución.
    
- **Rojo** Son áreas de solo lectura donde los valores de entrada están bloqueados y no se pueden cambiar.
    
- **Gris** Son áreas que solo permiten la visualización. Son los resultados o datos derivados de áreas de entrada generales.
    
El proceso de diseño de Dewey Law, LLC. empieza con la caracterización de sus usuarios en diferentes "roles". Por cada rol que defina, puede especificar el uso esperado de las diferentes aplicaciones de Skype Empresarial ("Ninguno", "Bajo", "Medio", "Alto" o una de las tres opciones definidas de "Personalizado"). Estas selecciones se encuentran en la hoja de cálculo "Rol". Se proporciona el uso específico para cada opción ("Bajo", "Medio", "Alto"), pero los valores predeterminados para cada opción no se pueden cambiar. Al identificar el número de usuarios por cada rol que se encuentra en cada sitio, la calculadora puede calcular el total de ancho de banda necesario para cada ubicación.
  
También puede especificar los códecs de audio y de vídeo que se usarán, si se usa la corrección de errores de transmisión y otros parámetros del sistema que afectarán a los requisitos de ancho de banda. Puede usar la configuración predeterminada de la Herramienta de cálculo de ancho de banda de Skype Empresarial, o bien seleccionar diferentes códecs y otros parámetros del sistema. Para el diseño del sitio de Dewey Law, LLC., se puede usar la configuración predeterminada. Pero, para cambiar cualquier opción de la configuración predeterminada, hay un menú desplegable con todas las opciones disponibles. Los valores de ancho de banda que se usan para cada opción se incluyen en la hoja de cálculo "Códecs". Si cambia un parámetro, se actualizará el cambio en la combinación de ancho de banda y clase de servicio (CoS) en todos los sitios. Esta capacidad le permite probar diferentes configuraciones posibles y ver el impacto que tendrán los cambios en los requisitos de ancho de banda.
  
Hemos definido tres roles para Dewey Law, LLC.: "Ejecutivo/socio", "Asociado/asistente jurídico" y "Administradores de TI". En la tabla siguiente se muestra cómo hemos establecido los perfiles de uso para las distintas aplicaciones de Skype Empresarial para cada rol.
  
 **Roles y perfiles de uso (hoja de cálculo "Rol": columnas de la A a la P)**
  
|**Rol**|**MI/Presencia**|**Audio P2P**|**Vídeo P2P**|**Audioconferencia**|**Videoconferencia**|**Compartir escritorio**|**Audioconferencia de acceso telefónico local**|**Lync 2010Tipo_RTV**|**Usuarios remotos**|**Lync 2013audio estéreo**|**Lync 2013calidad de vídeo**|**Lync 2013comportamiento de los usuarios para la ventana de vídeo P2P**|**Lync 2013Uso para varias vistas**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Ejecutivo/socio  <br/> |Alto  <br/> |Medio  <br/> |Bajo  <br/> |Medio  <br/> |Medio  <br/> |Ninguna  <br/> |Medio  <br/> |CIF  <br/> |0 %  <br/> |0 %  <br/> |Muy buena  <br/> |Típica  <br/> |Típica  <br/> |
|Asociado/Asistente jurídico  <br/> |Alto  <br/> |Medio  <br/> |Bajo  <br/> |Medio  <br/> |Alto  <br/> |Alto  <br/> |Medio  <br/> |CIF  <br/> |0 %  <br/> |0 %  <br/> |Medio  <br/> |Típica  <br/> |Típica  <br/> |
|Administradores de TI  <br/> |Alto  <br/> |Medio  <br/> |Ninguna  <br/> |Bajo  <br/> |Ninguna  <br/> |Ninguna  <br/> |Medio  <br/> |CIF  <br/> |0 %  <br/> |0 %  <br/> |Medio  <br/> |Típica  <br/> |Típica  <br/> |
   
Tendrá que escribir la información en la tabla **Distribución de usuarios por ubicaciones y puestos** anterior, en la hoja de cálculo "Sitios" de la Herramienta de cálculo de ancho de banda de Skype Empresarial. Como el número de usuarios en las oficinas regionales es idéntico, se definen para un "Sitio" y se especifica que hay tres instancias de este. Se realiza lo mismo para las sucursales grandes y pequeñas donde había 24 y 50 usuarios en los sitios, respectivamente.
  
Después de especificar la configuración para cada rol, tendrá que escribir en la hoja de cálculo "Sitios" el número de usuarios de cada rol en todos los sitios. El total de usuarios de todos los sitios se actualiza automáticamente. Como no hay ningún usuario en la ubicación de Office 365, se tienen que especificar todos en las filas "Sucursales" de la hoja de cálculo. A continuación, la Herramienta de cálculo de ancho de banda de Skype Empresarial rellena las columnas "Clase de mejor esfuerzo", "Clase de tráfico de datos" y "Clase de tráfico en tiempo real" en la tabla "Clase de tráfico de WAN BW por QoS". Esto se muestra en los datos de la tabla siguiente.
  
> [!TIP]
>  La hoja de cálculo completa también incluye el número máximo de sesiones simultáneas para cada aplicación, pero hemos eliminado esas columnas para ahorrar espacio.
  
 **Roles por sitio (hoja de cálculo "Sitios": columnas A, D, I y de AI a AX)**
  
|**Nombre del sitio**|**Total de usuarios en el sitio**|**Total de sitios como este**|**Perfil de usuario 1**|**Del usuario del perfil 1**|**Perfil de usuario 2**|**Del usuario del perfil 2**|**Perfil de usuario 3**|**Del usuario del perfil 3**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Sede central  <br/> |1070  <br/> |1  <br/> |Ejecutivo/socio  <br/> |170  <br/> |Asociado/asistente jurídico  <br/> |700  <br/> |Administradores de TI  <br/> |200  <br/> |
|Oficinas regionales  <br/> |345  <br/> |3  <br/> |Ejecutivo/socio  <br/> |60  <br/> |Asociado/asistente jurídico  <br/> |225  <br/> |Administrador de TI  <br/> |60  <br/> |
|Sucursales grandes  <br/> |70  <br/> |24  <br/> |Ejecutivo/socio  <br/> |11  <br/> |Asociado/asistente jurídico  <br/> |50  <br/> |Administrador de TI  <br/> |9  <br/> |
|Sucursales pequeñas  <br/> |36  <br/> |50  <br/> |Ejecutivo/socio  <br/> |6  <br/> |Asociado/asistente jurídico  <br/> |25  <br/> |Administrador de TI  <br/> |1  <br/> |
   
 **Ancho de banda necesario por aplicación y por sitio en Kbps(Hoja de cálculo "Sitios": columnas A y BQ a LF)**
  
|**Sitio**|**Máximo de ancho de banda de SIP/MI**|**Máximo de ancho de banda de audio del mismo nivel entre sitios**|**Máximo de ancho de banda de vídeo del mismo nivel entre sitios**|**Máximo de ancho de banda de audioconferencia**|**Máximo de ancho de banda de videoconferencia**|**Máximo de ancho de banda de uso compartido de WAN**|**Máximo de ancho de banda de WAN para llamadas RTC**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Sede central  <br/> |1070  <br/> |525,30  <br/> |560,00  <br/> |739,50  <br/> |2640,00  <br/> |4224,00  <br/> |2688,30  <br/> |
|Oficinas regionales  <br/> |345  <br/> |185,40  <br/> |560,00  <br/> |255,00  <br/> |1320,00  <br/> |1536,00  <br/> |896,10  <br/> |
|Sucursales grandes  <br/> |70  <br/> |92,70  <br/> |560,00  <br/> |102,00  <br/> |600,00  <br/> |384,00  <br/> |216,30  <br/> |
|Sucursales pequeñas  <br/> |36  <br/> |119,40  <br/> |560,00  <br/> |76,50  <br/> |600,00  <br/> |384,00  <br/> |123,60  <br/> |
   
Probablemente, las columnas más importantes de la hoja de cálculo son las que describen el ancho de banda de WAN por la clase de QoS. Esto se muestra en la tabla siguiente. Estos datos resumen la información que necesitará indicar al proveedor de servicios de red para solicitar la conexión de acceso a cada uno de los sitios. Al calcular el ancho de banda total, recuerde multiplicar el ancho de banda de cada tipo de sucursal por el número de sitios del mismo tipo. Para conectar con su partner de servicios de red de ExpressRoute, puede ver [Azure ExpressRoute]( https://go.microsoft.com/fwlink/?LinkId=690283).
  
Es muy importante que no supere el ancho de banda de voz o la clase de servicio de "Desvío rápido" (EF). Se descartó un conjunto de paquetes aleatorio, por lo que, en lugar de reducir la calidad de una sola llamada o de un grupo de llamadas, esto podría afectar a todas las llamadas en curso. También es importante que solo la voz se marque con DSCP para EF (es decir, DSCP = 46), ya que, en caso contrario, la cola de voz podría desbordarse si se agrega tráfico que no sea de voz.
  
> [!TIP]
>  De nuevo, aunque la clase de servicio de EF ofrece las mejores garantías de rendimiento, si se supera el ancho de banda definido, se descartarán los paquetes adicionales inmediatamente.
  
 **Ancho de banda agregado por sitio por clase de tráfico de QoS (hoja de cálculo "Sitios": columnas A y ML a MR) **
  
|**Nombre del sitio**|**Clase de mejor esfuerzo (DSCP 0)**|**Clase de tráfico de datos (DSCP personalizado)**|**Clase de tráfico en tiempo real(DSCP 34, AF41)**|**Clase de tráfico prioritario(DSCP 46, EF)**|
|:-----|:-----|:-----|:-----|:-----|
|Sede central  <br/> |0,00  <br/> |5764,80  <br/> |3200,00  <br/> |3953,10  <br/> |
|Oficinas regionales  <br/> |0,00  <br/> |2033,60  <br/> |1880,00  <br/> |1336,50  <br/> |
|Sucursales grandes  <br/> |0,00  <br/> |486,40  <br/> |1160,00  <br/> |411,00  <br/> |
|Sucursales pequeñas  <br/> |0,00  <br/> |438,40  <br/> |1160,00  <br/> |319,50  <br/> |
   
### <a name="putting-your-plan-into-action"></a>Poner en marcha el plan

Podemos calcular el ancho de banda total que atravesará la WAN y la cantidad de ancho de banda que atravesará ExpressRoute; para ello usamos la estimación del ancho de banda de la tabla **Por aplicación por sitio** anterior. La parte de tráfico que atraviesa ExpressRoute excluye el ancho de banda entre sitios del mismo nivel.

 
|**Sitio**|**Máximo de ancho de banda de SIP/MI**|**Máximo de ancho de banda de audioconferencia**|**Máximo de ancho de banda de videoconferencia**|**Máximo de ancho de banda de uso compartido de WAN**|**Máximo de ancho de banda de WAN para llamadas RTC**|**Total de ExpressRoute<br/>el tráfico por clase de sitio<br/>(es decir, total<br/>tiempo Nº de sitios)**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|**Sede central** <br/> |1.070  <br/> |739,50  <br/> |2640,00  <br/> |4224,00  <br/> |2688,30  <br/> |11361,80  <br/> |
|**Oficinas regionales** <br/> |345  <br/> |255,00  <br/> |1320,00  <br/> |1536,00  <br/> |896,10  <br/> |8704,20  <br/> |
|**Sucursales grandes** <br/> |70  <br/> |102,00  <br/> |600,00  <br/> |384,00  <br/> |216,30  <br/> |32935,20  <br/> |
|**Sucursales pequeñas** <br/> |36  <br/> |76,50  <br/> |600,00  <br/> |384,00  <br/> |123,60  <br/> |61005,00  <br/> |
   
Esto significa que el tráfico de Skype Empresarial Online que atravesará Express Route será aproximadamente de 114 Mbps, por lo que Dewey necesitará al menos una suscripción de 200 Mbps para ExpressRoute. Pueden adquirirse varios circuitos de ExpressRoute en diferentes ubicaciones de intercambio de tráfico de ExpressRoute. Esto podría ser recomendable si los sitios de Dewey se encuentran en regiones geográficas diferentes, o para proporcionar resistencia en el caso de que la conexión al circuito de ExpressRoute falle. Si adquiere circuitos de ExpressRoute en varias regiones de Azure, el complemento premium de ExpressRoute será necesario para recibir una conectividad global en ExpressRoute.
  
Ahora que tiene la cantidad total de ancho de banda necesario y los números de ancho de banda de clase de servicio (CoS), puede realizar los pedidos con los proveedores de servicios de red seleccionados. No olvide incluir las estimaciones del tráfico de otras aplicaciones y servicios. Ofrecemos orientación para la planeación de red de otros servicios de Office 365, incluidas calculadoras de ancho de banda para Exchange y OneDrive. La suscripción de ancho de banda para el proveedor de servicios de red será superior porque el tráfico entre sitios necesitará agregarse de nuevo. La calculadora de ancho de banda de Lync 2010 y 2013 proporciona solo una estimación del tráfico esperado, por lo que es recomendable confirmar la capacidad de la red para soportar el volumen de tráfico mediante una prueba de esfuerzo. 
  
> [!TIP]
> Es muy recomendable realizar una prueba de esfuerzo de la red al realizar una evaluación previa de la red. 
  
Para llevar a cabo una prueba de esfuerzo, es necesario crear y configurar la infraestructura y, después, ejecutarla con el volumen esperado de tráfico simulado al supervisar el rendimiento. Es posible que las estimaciones de tráfico no sean precisas en algunas áreas, pero al menos se asegura de que puede admitir el volumen de tráfico estimado por la Herramienta de cálculo de ancho de banda de Skype Empresarial. Se recomienda ejecutar la prueba de esfuerzo como mínimo varios días, pero ejecutarla durante períodos más prolongados de tiempo puede ayudarle a refinar los números. Pero extender el período de la prueba de esfuerzo se tiene que comparar con el coste de los servicios de red que esté pagando y que no transportan un tráfico de red real de usuarios. Microsoft ha certificado a varios proveedores como parte de su programa IT Pro Tools para proporcionar herramientas de administración y operaciones de red (por ejemplo, herramientas de esfuerzo de evaluación previa de red). Skype Empresarial también proporciona integradores de sistemas (SI) que pueden usar IT Pro Tools para completar la evaluación de la red. Para más información, vea [Soluciones de Skype Empresarial: IT Pro Tools](https://go.microsoft.com/fwlink/?LinkID=690307).
  
La prueba de esfuerzo proporciona algunas garantías de que la red puede admitir el volumen de tráfico que sea necesario, pero, en realidad, los datos de la Herramienta de cálculo de ancho de banda de Skype Empresarial pueden ser incorrectos por varias razones. También puede continuar supervisando las redes de sus sitios si realiza una evaluación de red continua después de su implementación, para garantizar que el ancho de banda sea suficiente y que los mecanismos de QoS funcionen correctamente. Es importante continuar supervisando el rendimiento de la red a medida que más usuarios reales empiezan a estar en línea.
  
## <a name="part-2-expressroute-skype-for-business-qos"></a>Parte 2:QoS de ExpressRoute para Skype Empresarial

El servicio ExpressRoute de Microsoft proporciona una conexión dedicada a la nube de Azure, pero los servicios de comunicación de las cargas de trabajo en tiempo real de Office 365 necesitarán servicios de red con un ancho de banda suficiente para transferir el volumen de tráfico necesario y que sea capaz de admitir una calidad de servicio (QoS) para ofrecer una experiencia del servicio de categoría empresarial a sus usuarios. Es necesario configurar una conexión compatible con QoS de un extremo a otro (PC, conmutadores y enrutadores de red a la nube), ya que cualquier parte de la ruta que no sea compatible con QoS puede afectar a la calidad de toda la llamada.
  
El objetivo de esta sección es hacer que le resulte más fácil comprender los retos al admitir el tráfico en tiempo real en una red IP, y configurar y admitir una implementación de ExpressRoute correcta de cargas de trabajo en tiempo real de Office 365 con un proveedor de Exchange de ExpressRoute o un proveedor de servicios de red que sean partners de Microsoft.
  
Solo se acepta QoS en sus redes sobre los circuitos de la red de ExpressRoute y se usa en la red de Microsoft para el tráfico de Skype Empresarial. Hoy en día, hay partes de algunas conexiones salientes de Microsoft a las que les faltan valores de DSCP para Skype Empresarial. Hasta que el tráfico saliente esté totalmente marcado con valores de DSCP, se le anima a que siga las directrices para agregar el marcado de QoS al tráfico en su límite de red, tal como se describe en la sección **Implementación de QoS con lista de control de acceso (ACL) de red** de este artículo.
  
### <a name="the-real-time-problem"></a>El problema del tiempo real

Para prestar servicios de voz y vídeo de calidad empresarial es necesario cumplir con demandas especiales de una red IP. El tráfico en tiempo real usa el protocolo de transporte en tiempo real (RTP), que se transfiere con el Protocolo de datagramas de usuario (UDP). Al contrario que el protocolo de control de transmisión (TCP), que asigna números y prueba todos los mensajes para asegurarse de que no contengan errores (además de incluir otros mecanismos para detectar y retransmitir mensajes perdidos o con errores), UDP no proporciona este tipo de fiabilidad. Si hay mensajes dañados debido a errores o mensajes perdidos debido a desbordamientos de búfer, estos se perderán. UDP se eligió para usarse con RTP porque la naturaleza del tráfico en tiempo real permite que, incluso aunque se volvieron a enviar los mensajes perdidos, llegarían demasiado tarde para que tuvieran un impacto positivo en el flujo de mensajes de voz.
  
Al conocer el impacto de los paquetes de voz perdidos, los diseñadores idearon dos enfoques para mejorar el rendimiento de la voz y vídeo sobre IP:
  
- Hacer que la codificación y descodificación de voz sea más resistente cuando se pierdan paquetes. Esto se puede conseguir con la corrección de errores de transmisión (FEC) para corregir un porcentaje de los errores detectados (una capacidad que se encuentra en el Protocolo de transporte en tiempo real de Office 365), o bien si se diseñan sistemas de descodificación de voz que intenten enmascarar el efecto de los paquetes perdidos, que es una característica de los códecs de Microsoft. 
    
- Usar servicios de transporte que usen mecanismos de calidad de servicio para garantizar el rendimiento de la red en relación con retrasos, pérdida de paquetes y vibración, y la variación en el retraso entre paquetes.
    
Una codificación de voz resistente solo sirve para solucionar el problema de la pérdida de paquetes, por lo que es importante que una red usada para transportar voz y vídeo en tiempo real tenga mecanismos para minimizar el retraso y la vibración. Incluso con una codificación resistente, si se pierden demasiados paquetes, la estación receptora no tendrá información suficiente para reconstruir una versión reconocible de la señal de voz. El porcentaje de paquetes perdidos daría como resultado una degradación apreciable de la calidad de la voz, que varía según la técnica de codificación de voz que se use. Pero, en cualquier caso, la pérdida de cadenas de paquetes sucesivos es muy problemática.
  
Minimizar el retraso es importante, ya que un retraso excesivo puede afectar al flujo de la conversación y crear una molestia para los interlocutores. En los procedimientos recomendados se indica que el retraso de un extremo a otro de la voz (lo que se conoce como retraso de boca a oído) tiene que ser inferior a 150 milisegundos (ms) unidireccional, no un retraso de recorrido de ida y vuelta. Por supuesto, el retraso aumentará en vínculos de transmisión más largos, como los que atraviesan océanos, debido al retraso de propagación o al tiempo que tarda la señal en viajar físicamente a través del cable.
  
Cuando el retraso es superior a 150 ms unidireccional, tiene un efecto extraño en el hablante. Psicológicamente, se desactiva un reloj en el cerebro del hablante que le hace pensar que el destinatario no le ha escuchado y repite lo último que ha dicho. Esto entra en conflicto con la respuesta retrasada que proviene del extremo lejano. Si alguna vez ha hablado a través de un canal por satélite, reconocerá este efecto. A través de un canal por satélite, el retraso unidireccional es de aproximadamente 250 ms, lo que es muy superior al retraso permitido.
  
 **Parámetros de red recomendados para voz de categoría empresarial**
  
|**Parámetro**|**Valor recomendado**|
|:-----|:-----|
|Entre vibración de paquetes de llegada (promedio)  <br/> |≤ 5ms  <br/> |
|Entre vibración de paquetes de llegada (máximo)  <br/> |≤ 40ms  <br/> |
|Índice de pérdida de paquetes (promedio)  <br/> |0 % al aproximarse  <br/> |
|Latencia de red unidireccional  <br/> |≤ 100 ms (tienen que incluirse comprobaciones en el retraso frente a la distancia geográfica)  <br/> |
   
### <a name="expressroute-as-part-of-a-business-grade-voice-network"></a>ExpressRoute como parte de una red de voz de categoría empresarial

ExpressRoute ofrece una conexión dedicada a través de un Proveedor de servicios de red (NSP) o de un proveedor de Exchange (EXP) en una de las tres opciones de conexión: 
  
- Ubicación de Exchange en la nube
    
- Conexión punto a punto en Ethernet
    
- Conexión cualquiera a cualquiera (IPVPN)
    
Esto proporciona ventajas de alta disponibilidad (99,9 % SLA en tiempo activo) y un enrutamiento fiable que es seguro (sin tránsito de Internet), sin verse afectado por las variaciones en el tráfico de Internet y que respeta el marcado de Calidad del servicio para priorizar el tráfico (QoS se explica a continuación). ExpressRoute, junto con una WAN bien planeada, puede proporcionarle una red de voz de categoría empresarial.
  
Puede usar ExpressRoute para el tránsito de datos de oficinas o centros de datos (si es topología híbrida) que están conectados al circuito. Los datos de los usuarios de fuera del sitio (por ejemplo, de oficinas domésticas o de viajes, etc.) no aprovecharán el circuito de ExpressRoute a menos que los usuarios estén conectados a una VPN y no necesitan incluirse en estimaciones de ancho de banda para dimensionar el circuito de ExpressRoute. Si es un cliente multinacional, puede adquirir circuitos de ExpressRoute en cada región y usar etiquetas de comunidad BGP para informar de las reglas de enrutamiento por las que el tráfico se dirige al circuito de ExpressRoute preferido (normalmente el más cercano a cada sitio), mientras los otros circuitos ofrecen redundancia en caso de una interrupción que afecte al circuito individual. 
  
### <a name="if-expressroute-isnt-an-option"></a>Si ExpressRoute no es una opción

Puede que no sea viable conectar todos los sitios a ExpressRoute debido a los costes, a la incapacidad de cumplir los requisitos previos de ExpressRoute o a las limitaciones de su proveedor de servicios de red actual. Si no puede usar ExpressRoute se le recomienda seguir las siguientes instrucciones para marcar QoS dentro de su red y para planificar los contratos con su proveedor de servicios de red para asegurar un ancho de banda suficiente y admitir la priorización del tráfico de acuerdo con QoS.
  
Además, si tiene oficinas en varias regiones, pero no tiene circuitos de ExpressRoute en todas las regiones, debería usar las etiquetas de la comunidad BGP de la región al configurar el enrutamiento del tráfico hacia las oficinas satélite y desde ellas y así evitar el tránsito innecesario de largo recorrido. Por ejemplo, suponga que una empresa tiene una organización de Skype Empresarial Online hospedada en Estados Unidos, pero con sucursales en Europa, y la empresa solo tiene un único circuito de ExpressRoute en Silicon Valley. La mayoría del tráfico de Skype Empresarial Online se redirigirá a un centro de datos donde se hospede la organización (por ejemplo, llamadas de conferencias con otros usuarios de la empresa), y para la mayor parte del tráfico se preferirá usar el circuito de ExpressRoute. Sin embargo, si un usuario en Europa tuviera que unirse a una llamada de conferencia hospedada por otra empresa cuya organización se encuentra en Europa, el destino para los medios de esa llamada sería el centro de datos europeo donde se ubica la segunda empresa. Redirigir el tráfico a través del circuito de ExpressRoute en Silicon Valley sería una ruta menos directa de lo que sería posible a través de Internet. En ese caso, sería recomendable configurar enrutadores en su red (por ejemplo, en las oficinas europeas) para inspeccionar las etiquetas de la comunidad al realizar reglas de enrutamiento, y redirigir mediante Internet, en vez de por el circuito ExpressRoute de Silicon Valley, para el tráfico que tenga etiquetas regionales de Europa.
  
### <a name="basic-concepts-of-quality-of-service-qosclass-of-service-cos"></a>Conceptos básicos de Calidad de servicio (QoS)/Clase de servicio (CoS)

En IP, Calidad de servicio (QoS) describe cualquier mecanismo que se usa para proporcionar una administración de prioridades para algunos paquetes frente a otros. Según la definición de la Unión de Telecomunicaciones Internacional (ITU), QoS está compuesto por todos los aspectos de calidad de una conexión, incluido el retraso, la pérdida, la relación de señal a ruido, interferencias, eco, interrupciones, respuesta de frecuencias, niveles de volumen, etc. Lo que conocemos como QoS en redes de paquetes se denomina más correctamente Clase de servicio (CoS), que se centra en mejorar el rendimiento de retraso, vibración y pérdida de paquetes, pero continuaremos usando el término QoS, ya que es más común.
  
Al proporcionar QoS en una red IP se usan dos componentes principales:
  
- La reserva de una cantidad definida de ancho de banda en cada vínculo para el tráfico en tiempo real (si ese ancho de banda no se necesita para el tráfico en tiempo real en cualquier momento, se puede usar para otro tipo de tráfico). La recomendación general es que no se asigne más del 30 % de la capacidad de cualquier vínculo para el tráfico de voz.
    
- Marca los paquetes con un indicador de prioridad en el encabezado que indica a los conmutadores y enrutadores de la ruta la prioridad que se tiene que asignar al paquete.
    
Cuando se recibe un paquete en un conmutador o un enrutador, se mueve a una cola de salida para la siguiente sección o salto. Hay diferentes colas de salida para los diferentes niveles de prioridad. Un conmutador o enrutador usa un algoritmo que da servicio a la cola de prioridad alta con más frecuencia que a las colas de baja prioridad.
  
El reto es que hay dos técnicas de QoS distintas que se implementan en la capa 2 (es decir, la capa de Ethernet o la capa de Wi-Fi) y en la capa 3 (es decir, la capa de IP). Es posible que estas implementaciones distintas de QoS se tengan que configurar en cada conmutador y enrutador de la red, así como la interfaz entre su red y la red del proveedor de servicios de red.
  
Hay dos opciones para asignar los datos de las diferentes aplicaciones de Skype Empresarial a las diferentes clases de servicio:
  
- Marcado de extremo del tráfico con Punto de código de servicios diferenciados (DSCP) 
    
- Basado en lista de control de acceso (ACL) de red
    
### <a name="end-point-traffic-marking--differentiated-services-control-point-dscp"></a>Marcado de extremo del tráfico: Punto de código de servicios diferenciados (DSCP)

Los servicios diferenciados (DiffServ) son un mecanismo "general" para clasificar y administrar el tráfico de red y proporcionar QoS en redes IP. Los enrutadores y otros dispositivos que implementen funciones de capa 3 usan el Punto de código de servicios diferenciados (DSCP) para definir la prioridad del paquete. Para implementar QoS, se inserta un valor de DSCP de 6 bits en el campo Servicios diferenciados (anteriormente, el campo "Tipo de servicio") en el encabezado de IP (6 bits permiten 64 niveles de prioridad distintos). Los niveles de prioridad se suelen definir como se muestra aquí.
  
 **Configuración de DSCP recomendada**
  
|**Clase de tráfico**|**Tratamiento (Marcado DSCP)**|**Cargas de trabajo de Skype Empresarial**|
|:-----|:-----|:-----|
|**Voz** <br/> |EF (46)  <br/> |Voz de Skype Empresarial y Lync  <br/> |
|**Interactivas** <br/> |AF41 (34)  <br/> |Vídeo  <br/> |
||AF21 (18)  <br/> |Uso compartido de aplicaciones  <br/> |
|**Valor predeterminado** <br/> |AF11 (10)  <br/> |Transferencia de archivos  <br/> |
||CS0 (0)  <br/> |Otro valor  <br/> |
   
 ** Versión 4 del encabezado de IP**
  
![Encabezado IPv4](../images/c8a6a714-2784-4328-8297-2e62706f302d.png)
  
### <a name="layer-2-qos-ieee-8021pwi-fi-multi-media-ieee-80211e"></a>QoS de capa 2: IEEE 802.1p/Wi-Fi Multimedia (IEEE 802.11e)

Aunque DSCP es el mecanismo estándar para implementar QoS en la capa 3, hay diferentes mecanismos de QoS de capa 2 para conexiones cableadas (es decir, Ethernet) e inalámbricas (es decir, redes Wi-Fi). El mecanismo de QoS para las redes cableadas se define en el estándar IEEE 802.1p, mientras que el mecanismo de QoS para WLAN se define en IEEE 802.11e, lo que la Alianza Wi-Fi identifica como "Certificación Wi-Fi Multimedia" (certificación WMM).
  
IEEE 802.1p usa un punto de código de prioridad (PCP) de 3 bits para identificar la prioridad del mensaje (la PCP forma parte de un campo de 32 bits en el encabezado de Ethernet que también transporta el identificador de VLAN). A continuación se incluyen las definiciones de los valores de PCP.
  
 ** Valores de PCP de IEEE 802.1p**
  
|**Valor de PCP**|**Prioridad**|**Acrónimo**|**Tipos de tráfico**|
|:-----|:-----|:-----|:-----|
|7  <br/> |7  <br/> |NC  <br/> |Control de red  <br/> |
|6  <br/> |6  <br/> |IC  <br/> |Control de conexión entre redes  <br/> |
|5  <br/> |5  <br/> |VO  <br/> |Voz  <br/> |
|4  <br/> |4  <br/> |VI  <br/> |Vídeo  <br/> |
|3  <br/> |3  <br/> |CA  <br/> |Aplicaciones críticas  <br/> |
|2  <br/> |2  <br/> |EE  <br/> |Esfuerzo excelente  <br/> |
|0  <br/> |1  <br/> |BE  <br/> |Mejor esfuerzo  <br/> |
|1  <br/> |0  <br/> |BK  <br/> |Fondo  <br/> |
   
Aunque IEEE 802.1p se implementa de forma muy similar a DSCP con tráfico clasificado en diferentes colas de prioridad para cada nivel de prioridad, la naturaleza de uso compartido de medios de las redes WLAN necesita un enfoque distinto. Aunque el punto de acceso y el cliente mantengan colas de salida separadas para los distintos niveles de prioridad, hay diferencias en cómo se envían las tramas a través del canal de radio.
  
En una red Wi-Fi, todos los clientes asociados con un punto de acceso comparten un único canal de dúplex medio (es decir, solo una estación cliente o el punto de acceso pueden realizar envíos de forma simultánea). Para minimizar el potencial de colisiones en el canal de radio, antes de enviar una trama, la estación espera hasta que el canal esté inactivo durante un período de tiempo definido, llamado "Espaciado entre tramas" y, si el canal está ocupado cuando una estación va a realizar un envío, se interrumpe durante un período de tiempo aleatorio. Después de enviar la trama, si el remitente no recibe un mensaje de confirmación del destinatario, asume que se ha producido una colisión u otro error, y retrocede un intervalo aleatorio antes de intentar obtener acceso al canal de radio para repetir el envío. El intervalo de interrupción es aleatorio para reducir la probabilidad de que las mismas dos estaciones vuelvan a entrar en conflicto.
  
Para clasificar por orden de prioridad el acceso al canal de radio, IEEE 802.11e/WMM define diferentes intervalos de espera de transmisión previa llamados "Espaciados entre tramas arbitrados" (AFIS) y diferentes intervalos de interrupción para las diferentes clases de tráfico (se definen cuatro niveles de prioridad llamados "Categorías de acceso").
  
La prioridad se establece con la asignación de valores de AFIS más cortos a las tramas de prioridad más elevadas. Por lo tanto, si una estación está esperando para enviar una trama de voz y otra está esperando para enviar una trama de datos, la trama de voz siempre se enviará primero. Desde el punto de vista técnico, se asigna el mismo valor de AFIS a las tramas de voz y de vídeo, pero los intervalos de interrupción para las tramas de vídeo son superiores. Por lo tanto, aunque una trama de voz y una de vídeo pueden entrar en conflicto en el primer intento, la trama de voz siempre se retransmitirá antes. A continuación se muestra la correlación entre IEEE 802.1p e IEEE 802.11e:
  
 ** Asignación de IEEE 802.11e/Wi-Fi Multimedia (WMM) a 802.1P**
  
|**Categoría de acceso de WMM**|**Descripción deWMM**|**Valor de PCP de 802.1P**|**Designación de 802.1P**|
|:-----|:-----|:-----|:-----|
|1(AC_VO)  <br/> |Voz  <br/> |7 (111)  <br/> |NC  <br/> |
|6 (110)  <br/> |VO  <br/> |
|2(AC_VI)  <br/> |Vídeo  <br/> |5 (101)  <br/> |VI  <br/> |
|4 (100)  <br/> |CL  <br/> |
|3(AC_BE)  <br/> |Mejor esfuerzoDatos  <br/> |3 (011)  <br/> |EE  <br/> |
|0 (000)  <br/> |BE  <br/> |
|4(AC_BK)  <br/> |FondoDatos  <br/> |1 (001)  <br/> |BK  <br/> |
|2 (010)  <br/> |---  <br/> |
   
Aquí se muestra la asociación recomendada de las prioridades de la capa 3 con la capa 2:
  
 **Asociaciones recomendadas de prioridad de la capa 3 a la capa 2**
  
||**Marcas de la capa 3**|**Capa 2 (valor de PCP)**|**Wi-Fi (categoría de acceso)**|
|:-----|:-----|:-----|:-----|
|Control de red  <br/> |Comportamiento por salto (PHB): selector de clases (CS) 6  <br/> |6  <br/> |1(AC_VO)  <br/> |
|Valor de DSCP: 48  <br/> |
|Voz  <br/> |Comportamiento por salto (PHB): desvío rápido (EF)  <br/> |5  <br/> |1(AC_VO)  <br/> |
|Valor de DSCP: 46  <br/> |
|Videoconferencia  <br/> |Comportamiento por salto (PHB): desvío garantizado (AF) 41  <br/> |4  <br/> |2(AC_VI)  <br/> |
|Valor de DSCP: 34  <br/> |
|Señalización de llamadas  <br/> |Comportamiento por salto (PHB): selector de clases (CS) 3  <br/> |3  <br/> |2(AC_VI)  <br/> |
|Valor de DSCP: 24  <br/> |
|Datos de baja latencia  <br/> |Comportamiento por salto (PHB): desvío garantizado (AF) 21  <br/> |2  <br/> |3(AC_BE)  <br/> |
|Valor de DSCP: 18  <br/> |
|Datos de alto rendimiento  <br/> |Comportamiento por salto (PHB): desvío garantizado (AF) 11  <br/> |1  <br/> |3(AC_BE)  <br/> |
|Valor de DSCP: 10  <br/> |
|Mejor esfuerzo  <br/> |Comportamiento por salto (PHB): 0  <br/> |0  <br/> |4(AC_BK)  <br/> |
|Valor de DSCP: 0  <br/> |
   
Es importante señalar que hay un error de coincidencia en la codificación de prioridad para IEEE 802.1p y WMM. En 802.1p, el valor de PCP para voz es de 5, mientras que en la asignación de equivalencia estándar a WMM, PCP 5 se traduce como Categoría de acceso 2, la categoría de acceso de WMM para vídeo (AC_VI). Si es posible, se recomienda invalidar la asignación para que PCP 5 se traduzca como la categoría de acceso 1, o simplemente evitar usar voz y vídeo en la misma red Wi-Fi hasta que la Alianza Wi-Fi solucione este problema. Para más información sobre Wi-Fi, vea [Elementos del catálogo Wi-Fi]( https://go.microsoft.com/fwlink/?LinkId=690322)
  
### <a name="implementing-qos-using-network-access-control-list-acl"></a>Implementación de QoS con lista de control de acceso (ACL) de red

El método alternativo para implementar QoS en una configuración de ExpressRoute es usar la lista de control de acceso (ACL) de red. Con este método, en lugar de que los extremos inserten las marcas DSCP apropiadas en el encabezado de cada paquete, el marcado lo puede realizar un enrutador de canal de subida, según el puerto UDP de origen. Es necesario configurar todos los conmutadores y enrutadores para que sean compatibles con QoS, para garantizar que se mantenga la configuración de DSCP. Lo que es más importante, el enrutador conectado a la red del proveedor de servicios tiene que mantener el DSCP en el encabezado de cada paquete, ya que el parámetro de DSCP es básicamente la instrucción para indicar al proveedor de servicios de red cómo tiene que tratar el paquete.
  
Los intervalos de puertos recomendados para cada aplicación de Skype Empresarial se indican en la sección 2.6.1.1 de la guía [Planificación, supervisión y solución de problemas de red con Skype Empresarial Server](https://go.microsoft.com/fwlink/?LinkId=690286). Es importante coordinar esto con el enfoque general de la organización en relación con QoS, y se recomienda que esté informado de diferentes directivas de QoS y de posibles errores de coincidencia de marcado de paquetes.
  
Aunque la principal razón por la que se usa QoS y los servicios de red MPLS es garantizar una experiencia del usuario adecuada para voz y vídeo en tiempo real, estas mismas capacidades también se pueden aplicar en las aplicaciones de datos. En lugar de considerar todas las aplicaciones por igual, las redes MPLS pueden permitir a las organizaciones otorgar prioridad a algunas aplicaciones de datos frente a otras. Con MPLS, se puede asignar prioridad a las aplicaciones en tiempo real, como transacciones con tarjeta de crédito o la pantalla compartida, frente a tráfico que no dependa tanto del tiempo, como el correo electrónico.
  
### <a name="understanding-the-types-of-ip-network-services--basic-ip-and-mpls"></a>Información sobre los tipos de servicios de redes IP: IP básica y MPLS

El reenvío de paquetes IP original funcionaba según el principio de "mejor esfuerzo". Eso significaba que los enrutadores que reenviaban esos paquetes de IP harían lo posible para entregarlos en sus destinos, pero no existía ninguna garantía sobre cuándo o si llegarían a sus destinos. Así es como funcionan hoy en día los servicios de Internet básicos, como su conexión a internet doméstica. La idea era que, si se necesitaba confiabilidad para una aplicación en concreto, se proporcionaría con un mayor nivel en la pila de protocolos. El mecanismo de entrega confiable es el protocolo de control de transmisión (TCP). El Protocolo de datagramas de usuario (UDP), que se usa para voz y vídeo en tiempo real, es el mecanismo de entrega no confiable (es decir, de "mejor esfuerzo"). 
  
La conmutación por etiquetas multiprotocolo (MPLS) se desarrolló como un medio para que los proveedores de servicios de red ofrecieran un servicio IP con garantías de rendimiento para retraso, vibración y pérdida de paquetes. Para ofrecer esas garantías de rendimiento, MPLS reduce parte de la falta de predictibilidad de la IP tradicional. Primero, en lugar de que cada paquete tenga que encontrar su camino de enrutador a enrutador hasta llegar a su destino (que, como resultado, podría ocurrir que cada paquete tomara una ruta distinta desde el origen hasta el destino), MPLS enruta todos los paquetes con una conexión de "circuito virtual" con una ruta fija llamada intercambio de rutas por etiqueta (LSP). Si uno de los vínculos de la ruta produce errores, se cambiará rápidamente la ruta de todos los LSP que usen ese vínculo.
  
Cuando un paquete se envía a la red MPLS, el proveedor de servicios de red del enrutador perimetral anexa un encabezado adicional al paquete, que incluye una etiqueta que se usa para reenviarlo al LSP adecuado. La etiqueta es eliminada por el enrutador perimetral en el otro extremo de la red MPLS.
  
Antes de simplificar el proceso de reenvío, la otra ventaja que proporciona MPLS es que el sistema de administración de redes sabrá que las conexiones se realizan en todos los vínculos de la red. Al controlar la forma en que se enruta el tráfico a través de la red, el operador puede garantizar la QoS que proporcionará cada ruta. Por lo tanto, al contrario que el rendimiento del mejor esfuerzo de la IP tradicional o básica, los operadores de MPLS pueden proporcionar un servicio IP con un rendimiento predecible. LSP también hace que MPLS sea por definición más seguro que los servicios de Internet tradicionales. Por lo tanto, con el servicio IP básico se puede esperar que el rendimiento de la red sea lo suficientemente bueno para proporcionar voz de calidad correcta y use técnicas como FEC, además de una codificación de voz más resistente, para mejorar las probabilidades, lo que puede garantizar el uso de MPLS.
  
Los proveedores de MPLS ofrecen varios niveles de clase de servicio, pero, desafortunadamente, cada uno usa términos distintos para identificarlos. Tendrá que trabajar estrechamente con su proveedor para asegurarse de que comprende los datos de la [Herramienta de cálculo de ancho de banda de Skype Empresarial](https://go.microsoft.com/fwlink/?LinkID=690282) y las opciones recomendadas para las diferentes aplicaciones de cargas de trabajo en tiempo real de Office 365.
  
## <a name="conclusion"></a>Conclusión

Skype Empresarial mejora la forma en que se realizan las comunicaciones empresariales. En lugar de tener un teléfono conectado a un PBX, un sistema de videoconferencia independiente, una plataforma separada para el correo electrónico, un servicio externo para audioconferencia y algún vehículo para MI y presencia, Skype Empresarial puede reunir todas estas capacidades en una misma interfaz de usuario.
  
Para proporcionar servicios de voz y vídeo en tiempo real de categoría empresarial y de manera coherente, se necesita una infraestructura de red de un extremo a otro que sea capaz de proporcionar QoS. Esto incluye tanto a servicios LAN como a servicios WAN. Microsoft proporciona herramientas como la [Herramienta de cálculo de ancho de banda de Skype Empresarial](https://go.microsoft.com/fwlink/?LinkID=690282) para calcular la capacidad de la red que necesitará para los diferentes servicios. Además, también hay partners en el programa IT Pro Tools,[Soluciones de Skype Empresarial: IT Pro Tools](https://go.microsoft.com/fwlink/?LinkID=690307), que ofrecen herramientas para realizar una evaluación previa de la infraestructura de red y dar soporte para la supervisión, generación de informes y solución de problemas. Sin una infraestructura de red con un tamaño y una configuración correctos, existe el riesgo de tener una implementación de Skype Empresarial de ExpressRoute que no cumpla con las expectativas de los usuarios en relación con la calidad y la coherencia.
  
Las herramientas empresariales eficaces tienen que producir resultados confiables y coherentes, y entregar una experiencia del usuario que anime a la adopción de usuarios. Desde un punto de vista de redes, esto equivale a tener una infraestructura de red, tanto local como de área extensa, fija y móvil, que pueda permitir esto. La planificación, el diseño, la implementación y el mantenimiento de esa infraestructura no es siempre una tarea sencilla. El hardware, las herramientas y los servicios de red para alcanzar esto están disponibles hoy en día, pero es responsabilidad de los profesionales de TI comprobar que el diseño, la implementación y el mantenimiento se realiza de forma que garantice a los usuarios un conjunto de servicios de comunicaciones y de colaboración que les permita trabajar de manera eficiente y eficaz, y que la organización pueda aprovechar al máximo todas las ventajas que puede ofrecer esta tecnología. 
  
## <a name="related-topics"></a>See also

[Documentación de ExpressRoute](https://go.microsoft.com/fwlink/?LinkId=690285)

  
 