---
title: ExpressRoute and QoS in Skype for Business Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 20c654da-30ee-4e4f-a764-8b7d8844431d
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom: Setup
description: 'Aprenda a usar ExpressRoute de Azure para tener una red con requisitos de ancho de banda y capacidad de calidad de servicio para una experiencia de usuario de clase empresarial. '
ms.openlocfilehash: 7073840031013d41013762b190ccdc568840cceb
ms.sourcegitcommit: 61127a5723fe58545b0b19edb2e2d4260965eb4a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/19/2017
---
# <a name="expressroute-and-qos-in-skype-for-business-online"></a>ExpressRoute and QoS in Skype for Business Online

Conectarse a Office 365 a través de una conexión de red dedicada con Azure ExpressRoute para Office 365 y Skype para los negocios en línea. La conexión dedicada para el Skype para aplicaciones de negocios le dará rendimiento predecible y confiable como privacidad fuera de la red pública internet. Ahora puede adquirir una conexión de red mejor a Office 365 y Skype para los negocios en línea que agrega la capacidad de predicción, confiabilidad de clase empresarial y viene con un SLA de tiempo activo.
  
> [!NOTE]
> Hay disponible una nueva versión de la calculadora de ancho de banda: [Skype para el negocio, calculadora de ancho de banda](https://go.microsoft.com/fwlink/?LinkId=715766). Sin embargo, las instrucciones de este documento utilice la Lync 2010 y Calculadora de ancho de banda de 2013. 
  
## <a name="skype-for-business-online-and-expressroute"></a>Skype para el negocio en línea y ExpressRoute

Trabajar con socios de ExpressRoute de la Microsoft, puede conectar una variedad de aplicaciones de Office 365, incluyendo Skype para los negocios en línea en la nube a través de una conexión dedicada. Sin embargo, la voz en tiempo real y capacidades de comunicaciones de vídeo de Skype para empresas requieren servicios de red están configurados específicamente para admitir estas cargas de trabajo en tiempo real de Office 365. Esto incluye una red con ancho de banda suficiente para llevar a cabo el volumen de tráfico necesario y ser capaz de admitir la calidad de servicio (QoS) para ofrecer una experiencia de clase empresarial para los usuarios.
  
Este documento está diseñado para ayudar a usted, administradores y diseñadores de red comprender los desafíos especiales necesarios para admitir las comunicaciones en tiempo real, las herramientas proporcionadas por Microsoft para ayudarle a diseñar una red capaz de admitirlos requisitos y le guiará a través del proceso de diseño mediante un caso práctico. 
  
La primera parte de este documento le guía a través de un estudio de caso para ayudarle con el diseño de red con [Lync 2010 y 2013 Calculadora de ancho de banda](https://go.microsoft.com/fwlink/?LinkId=690282) para estimar los requisitos de red para un Skype grande y en múltiples sitios para la implementación de ExpressRoute de negocios. La segunda parte de este documento le ofrece los conceptos fundamentales de calidad de servicio (QoS), un análisis más profundo sobre los detalles técnicos específicos para la compatibilidad con Skype para comunicaciones en tiempo real de negocio y los tipos específicos de servicios de red que están es necesario.
  
Toda la información que aquí le proporcionará los detalles técnicos y descripción para QoS y ExpressRoute, comprender los desafíos específicos podrá ser frente a y brindarle un conocimiento práctico de las herramientas y técnicas que le permitirá correctamente implementar un ExpressRoute en su Skype para red de negocios. 
  
## <a name="getting-started"></a>Introducción

Cuando está listo para ExpressRoute de Skype para el negocio, es una buena idea mirar los diferentes modelos de conexión de ExpressRoute y la elección de asociados de negocios y ubicaciones diferentes y lea cómo adquirir y hacer provisioning de ExpressRoute dentro de su empresa. A continuación presentamos algunos recursos para ayudarle a comenzar: 
  
- [Azure ExpressRoute]( https://go.microsoft.com/fwlink/?LinkId=690283)
    
- [Precios ExpressRoute](https://go.microsoft.com/fwlink/?LinkId=690284)
    
- [Documentación de ExpressRoute](https://go.microsoft.com/fwlink/?LinkId=690285)
    
## <a name="part-1-case-study---expressroute-for-dewey-law-llc"></a>Parte 1: caso práctico - ExpressRoute para Dewey Law, LLC.

Este caso práctico para Dewey Law, LLC. le mostrará cómo configurar una red, servicios de acceso de red de orden y determinar los requisitos de ancho de banda para admitir ExpressRoute de Skype para los negocios en línea.
  
 **Fondo** Ley mistake LLC. ¿es una empresa grande derecho nacional con 790 abogados y un total de 5.580 empleados distribuida en 78 ubicaciones. La empresa tiene una oficina central en Nueva York, tres oficinas regionales en Chicago, San Francisco y Dallas, junto con el gran tamaño de 24 y 50 pequeñas sucursales repartidos por todo el país. La empresa controla los casos de grandes y complejos con la carga de trabajo normalmente repartido en dos o más de las oficinas. Con este resultado de diseño de red considerable tráfico de red entre las oficinas.
  
Ley mistake LLC. es una empresa relativamente joven y los abogados y otros miembros del personal son muy cómodos con la tecnología y en gran medida dependen de su trabajo diario. 
  
 **Distribución de usuarios por ubicaciones y posiciones**
  
||**Sede central (Nueva York)**|**Oficinas regionales (3)**|**Sucursales de gran tamaño (24)**|**Las sucursales pequeñas (50)**|
|:-----|:-----|:-----|:-----|:-----|
|Ejecutivo  <br/> |20  <br/> |10  <br/> |1  <br/> |1  <br/> |
|Asociados de negocios  <br/> |150  <br/> |50  <br/> |10  <br/> |5  <br/> |
|Associates  <br/> |300  <br/> |100  <br/> |20  <br/> |10  <br/> |
|Asistente legal  <br/> |400  <br/> |125  <br/> |30  <br/> |15  <br/> |
|Administradores ejecutivos  <br/> |100  <br/> |35  <br/> |6  <br/> |3  <br/> |
|IT and general Administrative  <br/> |100  <br/> |25  <br/> |3  <br/> |2  <br/> |
|Total por sitio  <br/> |1.070  <br/> |345  <br/> |70  <br/> |36  <br/> |
|Total por clase de sitio  <br/> |1.070  <br/> |1.035  <br/> |1.680  <br/> |1.800  <br/> |
   
### <a name="setting-up-the-network"></a>Configuración de la red

Para ofrecer servicios en tiempo real de coherente y de alta calidad para Dewey Law LLC., hay un par de requisitos básicos que debe cumplirse:
  
- Desean proporcionar servicios de voz durante el corte de suministro eléctrico, por lo que sus conmutadores de distribución de red y enrutadores deben proporcionar alimentación a través de Ethernet (PoE) IEEE 802.3af o 802.3at.
    
- Los conmutadores y enrutadores de red también deben utilizar fuentes de alimentación ininterrumpida (SAI) para que puedan continuar en funcionamiento durante un corte de alimentación.
    
    Tienen una conexión Wi-Fi a sus oficinas de LAN, por lo que se recomienda usar un certificado Skype para socios de infraestructura empresarial Wi-Fi de [Skype para soluciones empresariales](https://go.microsoft.com/fwlink/?LinkId=690281).
    
    > [!TIP]
    >  se recomienda utilizar puntos de acceso inalámbrico 802. 11n y 802.11ac.
  
- Y lo más importante, todas las redes LAN en todas las oficinas deben configurarse para proporcionar calidad de servicio (QoS). Esto incluye PCs, computadoras portátiles y hardware de red como switches y routers.
    
Ahora que tienes cubierto lo básico, para ofrecer servicios de voz de grado empresarial para Dewey Law LLC., se recomienda usar servicio de Multi-Protocol Label Switching (MPLS) IP desde un socio de servicio de red que se conectará al servicio ExpressRoute de Azure. MPLS proporciona un servicio IP con garantías de retraso, inestabilidad y pérdida de paquetes. Sin embargo, si no está disponible la MPLS, Ethernet conectado a uno de nuestro asociados de negocios de intercambio de datos también pueden utilizarse de ExpressRoute.
  
Proveedores de MPLS ofrecen varias clases de niveles de servicio, pero cada uso de diferentes términos para identificarlas. Tendrá que trabajar estrechamente con su proveedor para asegurarse de que comprenden los datos que han de entrada en [Lync 2010 y 2013 Calculadora de ancho de banda](https://go.microsoft.com/fwlink/?LinkID=690282) y las opciones disponibles y se recomiendan para la carga de trabajo en tiempo real diferentes de Office 365 aplicaciones.
  
Hay dos opciones para cómo se pueden asignar datos de Skype para aplicaciones empresariales a las clases correspondientes de MPLS de servicio:
  
- Extremo marcado de tráfico utilizando el punto de Control de DiffServ (DSCP)
    
- Según la lista de Control de acceso de red (ACL)
    
Para implementar el extremo de marcado, debe configurar todos los equipos de Windows dominio unido para Dewey ley LLC. para marcar cada paquete con la marca de punto de Control de DiffServ (DSCP) adecuada y, a continuación, implementar QoS en todos los enrutadores y conmutadores de red en todos los sitios de office para asegurarse de que la calidad del servicio marcas se mantienen y no se quitan. Marcados de DSCP en paquetes de red indican que el proveedor de servicios cómo se priorizan ese paquete de red. **Hay más información en DSCP en la sección de QoS en la parte 2.**
  
Asignación basada en ACL de la red, las marcas de prioridad DSCP se implementan en un enrutador de nivel superior y se basan en el puerto de origen UDP. Los intervalos de puerto recomendado para cada aplicación se enumeran en la sección 2.6.1.1 de la [Red planificación, supervisión y solución de problemas con Lync Server](https://go.microsoft.com/fwlink/?LinkId=690286). Es importante que coordinar esto con Dewey ley LLC general diseño e implementación de QoS y ser conscientes de las distintas directivas de QoS y la posibilidad de marcar los errores de coincidencia de paquetes.
  
Cada proveedor de servicios de red de ExpressRoute tendrá una clase de servicio (QoS) que sea adecuado para vídeo y voz en tiempo real. Este COS se llama 'Expedited Forwarding' (EF) para voz y 'Reenvío asegurado' (AF) para vídeo. Debe ser muy cuidadoso en la cantidad de ancho de banda que adquirir para voz tráfico EF de tamaño. La razón es que la clase de voz del servicio es muy implacable en caso de que se envíe más tráfico de voz de la clase del servicio está configurada para.
  
> [!TIP]
>  Any traffic that is sent on the voice class of service in excess of the service provider's commitment is immediately discarded which will direct effect voice quality.
  
Cuando se mira el diseño general de Dewey ley LLC. it is extremely important that you accurately determine the amount of network bandwidth that they need to support the voice traffic across their network and be marking each voice packet (and only voice packets) with the DSCP setting for voice (i.e. DSCP EF 46).
  
To implement QoS across their enterprise network, the endpoints or routers must mark each packet with the appropriate Layer 3 priority indicator (i.e., DSCP). Along the entire network path, each switch and router must have the QoS option turned on. Having even only one network switch or router that doesn't have QoS turned on, the QoS markings on voice or video packets passing through that switch or router could be stripped off. This effectively disables QoS in all downstream switches and routers which decreases the value of having ExpressRoute.
  
This also requires that the association of the Layer 3 and Layer 2 QoS priorities be defined at each point. The Layer 2 priority mechanisms are defined in IEEE 802.1p for wired networks and 802.11e/WMM for Wi-Fi networks. More importantly, the network router facing the network service provider's MPLS network must maintain the DSCP settings on all outbound packets so that they will maintain the appropriate MPLS class of service. 
  
> [!TIP]
>  For the specific details regarding QoS set-up, refer to Section 2.6 [Network Planning, Monitoring, and Troubleshooting with Lync Server]( https://go.microsoft.com/fwlink/?LinkId=760669). You can also see [Plan network requirements for Skype for Business 2015](https://go.microsoft.com/fwlink/?LinkId=690287) for more network planning requirements.
  
### <a name="ordering-network-access-services"></a>Ordering Network Access Services

Once you have the QoS network prerequisites and mechanisms in place to support ExpressRoute, the next step is to place an order for the ExpressRoute network access services. When ordering ExpressRoute access services for Dewey Law LLC from the Microsoft network services provider partner, you will need to provide two things:
  
- The total amount of bandwidth required to connect each site to ExpressRoute and Office 365.
    
- The total bandwidth required for each class of service that is required to support Skype for Business apps that are being used at Dewey Law LLC. The class of service bandwidth requirement is driven by the volume of traffic you expect from each of the various Skype for Business applications like voice, video, IM, presence, and screen sharing.
    
### <a name="determining-bandwidth-requirements-for-skype-for-business-applications"></a>Determining Bandwidth Requirements for Skype for Business Applications

For Dewey Law LLC., once you have determined the total bandwidth required you now need to know how that total amount of bandwidth should be divided among the various classes of service. For example, how much bandwidth for each Skype for Business application.
  
To determine those requirements at each of the Dewey Law LLC. sites, you will use the [Lync 2010 and 2013 Bandwidth Calculator](https://go.microsoft.com/fwlink/?LinkID=690282). This calculator is an Excel-based tool that allows you to specify the expected use of the various Skype for Business applications including voice, video, conferencing, and screen sharing. The calculator will automatically generate an estimate of the bandwidth and CoS requirements for each site on their network. When you download the Lync 2010 and 2013 Bandwidth Calculator, a user's guide will also be downloaded which will give you details on using it. 
  
To help you with the spreadsheet, the various cells in the spreadsheet are color-coded:
  
- **Green** These are general data input areas.
    
- **Yellow** These are advanced data input areas. You can change these, but do so carefully.
    
- **Red** These are read-only areas and are locked input values and can't be changed.
    
- **Gray** These are display-only areas. They are the results or data that is from the general input areas.
    
The design process for Dewey Law LLC. begins by characterizing their users into different 'Personas.' For each persona you define, you can specify their expected use of the various Skype for Business applications ('None', 'Low', 'Medium', 'High', or one of three defined 'Custom' settings). Those selections are found in the 'Persona' worksheet. The specific usage for each choice ('Low', 'Medium', or 'High') is provided, but the defaults for each choice can be changed. By identifying the number of users for each persona that is located at each site, the calculator can compute the total bandwidth required for each location.
  
You can also specify the audio and video codecs that are used, whether forward error correction is used and also other system parameters that will affect the bandwidth requirements. You can use the default settings in the Lync 2010 and 2013 Bandwidth Calculator or select different codecs and other system parameters. For Dewey Law LLC's site design, the default settings can be used. However, to change from any of the default settings there is a pull-down menu with all of the available choices. The bandwidths that are used for each choice are included in the 'Codecs' worksheet. When you change any setting, the change in bandwidth and class of service (CoS) mix at each site is updated. Having this capability allows you to test different potential configurations for them and see the impact the changes will have on bandwidth requirements for them.
  
We have defined three personas for Dewey Law LLC., 'Executive/Partner', 'Associate/Paralegal' and 'IT admins'. The table below shows how we have set the usage profiles for the various Skype for Business apps for each persona.
  
 **Personas and usage profiles ('Persona' Worksheet- Columns A through P)**
  
|**Persona**|**IM/Presence**|**P2P audio**|**P2P video**|**Conferencing audio**|**Conferencing video**|**Compartir escritorio**|**Audioconferencia**|**RTV_Type de Lync 2010**|**Usuarios remotos**|**Lync 2013 stereo audio**|**Lync 2013 video quality**|**Lync 2013 users behavior for P2P video window**|**Lync 2013 Multi-view usage**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Executive/ Partner  <br/> |Alta  <br/> |Mediana  <br/> |Bajo  <br/> |Mediana  <br/> |Mediana  <br/> |Ninguno  <br/> |Mediana  <br/> |CIF  <br/> |0%  <br/> |0%  <br/> |Mejor  <br/> |Típica  <br/> |Típica  <br/> |
|Asociar / Paralegal  <br/> |Alta  <br/> |Mediana  <br/> |Bajo  <br/> |Mediana  <br/> |Alta  <br/> |Alta  <br/> |Mediana  <br/> |CIF  <br/> |0%  <br/> |0%  <br/> |Mediana  <br/> |Typical  <br/> |Typical  <br/> |
|Administradores de TI  <br/> |Alta  <br/> |Mediana  <br/> |Ninguno  <br/> |Bajo  <br/> |Ninguno   <br/> |Ninguno  <br/> |Mediana  <br/> |CIF  <br/> |0%  <br/> |0%  <br/> |Mediana  <br/> |Typical  <br/> |Typical  <br/> |
   
You will need to enter the information in the **Distribution of users by locations and positions** table above in the 'Sites' worksheet of the Lync 2010 and 2013 Bandwidth Calculator. As the number of users in the regional offices is identical, they are defined for one 'Site' and specified that there were three instances of it. The same was done for the large and small branches where there were 24 and 50 users in sites respectively.
  
After specifying the settings for each persona, you need to enter the number of users in each persona at each site in the 'Sites' worksheet. The total users for all sites is updated automatically. Since there aren't users at the Office 365 location, they should all be entered in the 'Branches' rows of the worksheet. The Lync 2010 and 2013 Bandwidth Calculator then populates the 'Best Effort Class', 'Data Traffic Class' and 'Real-time traffic class' columns in the 'WAN BW per QoS traffic class' table. This is shown in the data in the table below.
  
> [!TIP]
>  The full spreadsheet also includes the maximum number of simultaneous sessions for each application, but we deleted those columns to save space.
  
 **Personas by site - ('Sites' Worksheet- Columns A, D, I and AI through AX)**
  
|**Nombre del sitio**|**Número total de usuarios en el sitio**|**Total Sites Like This**|**User Profile 1**|**User's of Profile 1**|**User Profile 2**|**User's of Profile 2**|**User Profile 3**|**User's of Profile 3**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Headquarters  <br/> |1070  <br/> |1  <br/> |Executive/Partner  <br/> |170  <br/> |Asociar/Asistente legal  <br/> |700  <br/> |Administradores de TI  <br/> |200  <br/> |
|Oficinas regionales  <br/> |345  <br/> |3  <br/> |Ejecutivo o pareja  <br/> |60  <br/> |Asociar/Asistente legal  <br/> |225  <br/> |Administración de TI  <br/> |60  <br/> |
|Las sucursales grandes  <br/> |70  <br/> |24  <br/> |Ejecutivo o pareja  <br/> |11  <br/> |Asociar/Asistente legal  <br/> |50  <br/> |Administración de TI  <br/> |9  <br/> |
|Las sucursales pequeñas  <br/> |36  <br/> |50  <br/> |Ejecutivo o pareja  <br/> |6  <br/> |Asociar/Asistente legal  <br/> |25  <br/> |Administración de TI  <br/> |1  <br/> |
   
 **Ancho de banda requerido por cada aplicación por sitio en Kbps ('Sitios hoja'-las columnas A y BQ a través de LF)**
  
|**Sitio**|**Pico de SIP / ancho de banda IM**|**Máximo ancho de banda entre sitios del mismo nivel Audio**|**Máximo ancho de banda entre sitios del mismo nivel vídeo**|**Máximo ancho de banda de conferencia de Audio**|**Máximo ancho de banda de videoconferencia**|**Ancho de banda de WAN compartir máximo**|**Ancho de banda WAN máximo para las llamadas PSTN**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Sede central  <br/> |1070  <br/> |525.30  <br/> |560.00  <br/> |739.50  <br/> |2640.00  <br/> |4224.00  <br/> |2688.30  <br/> |
|Oficinas regionales  <br/> |345  <br/> |185.40  <br/> |560.00  <br/> |255.00  <br/> |1320.00  <br/> |1536.00  <br/> |896.10  <br/> |
|Sucursales de gran tamaño  <br/> |70  <br/> |92,70  <br/> |560.00  <br/> |102,00  <br/> |600,00  <br/> |384.00  <br/> |216.30  <br/> |
|Sucursales pequeñas  <br/> |36  <br/> |119.40  <br/> |560.00  <br/> |76.50  <br/> |600,00  <br/> |384.00  <br/> |123.60  <br/> |
   
Probablemente las columnas en la hoja de cálculo más importantes son los que describen el ancho de banda WAN por clase de QoS. Esto se muestra en la tabla siguiente. Estos datos resumen la información que debe proporcionar al proveedor de servicios de red para solicitar la conexión de acceso a cada uno de los sitios. Al calcular el ancho de banda total, no olvide multiplicar el ancho de banda para cada tipo de sucursales por el número de sitios del mismo tipo. Para conectar con su socio de servicios de red de ExpressRoute, puede ver [ExpressRoute de Azure]( https://go.microsoft.com/fwlink/?LinkId=690283).
  
Es muy importante que no superan el ancho de banda en la voz o 'Expedited Forwarding' (EF) de la clase de servicio. Un conjunto aleatorio de paquetes se descartarán tan en lugar de reducir la calidad de una llamada única o un conjunto de llamadas, todas las llamadas en curso pueden verse afectados. También es importante que sólo voz marcarse con el valor DSCP para EF (es decir, DSCP = 46) o la cola de voz podría causar un desbordamiento cuando el tráfico de voz no se agrega.
  
> [!TIP]
>  De nuevo, mientras que la clase EF de servicio ofrece la mejor garantía de ejecución, si supera el ancho de banda definido, inmediatamente se descartarán todos los paquetes.
  
 **Ancho de banda agregado por sitio por clase de tráfico QoS - ('Sitios' hoja de cálculo de las columnas A y ML mediante MR)**
  
|**Nombre del sitio**|**Clase de mejor esfuerzo (DSCP 0)**|**Clase de tráfico de datos (DSCP personalizado)**|**Clase de tráfico en tiempo real (DSCP 34, AF41)**|**Clase de prioridad del tráfico (DSCP 46, EF)**|
|:-----|:-----|:-----|:-----|:-----|
|Sede central  <br/> |0,00  <br/> |5764.80  <br/> |3200.00  <br/> |3953.10  <br/> |
|Oficinas regionales  <br/> |0,00  <br/> |2033.60  <br/> |1880.00  <br/> |1336.50  <br/> |
|Sucursales de gran tamaño  <br/> |0,00  <br/> |486.40  <br/> |1160.00  <br/> |411.00  <br/> |
|Sucursales pequeñas  <br/> |0,00  <br/> |438.40  <br/> |1160.00  <br/> |319.50  <br/> |
   
### <a name="putting-your-plan-into-action"></a>Poniendo su plan en acción

Podemos calcular el ancho de banda total que se atraviesan la WAN y la cantidad de ancho de banda que pasarán por el ExpressRoute, utilizando el ancho de banda estimaciones de la tabla **por aplicación y por el sitio** anterior. La parte del tráfico que atraviesa ExpressRoute excluye el ancho de banda entre sitios del mismo nivel.

 
|**Sitio**|**Pico de SIP / ancho de banda IM**|**Máximo ancho de banda de conferencia de Audio**|**Máximo ancho de banda de videoconferencia**|**Ancho de banda de WAN compartir máximo**|**Ancho de banda WAN máximo para las llamadas PSTN**|**Total ExpressRoute<br/>tráfico por clase de sitio<br/>(es decir, total<br/>tiempo Nº de sitios)**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|**Sede central** <br/> |1.070  <br/> |739.50  <br/> |2640.00  <br/> |4224.00  <br/> |2688.30  <br/> |11361.80  <br/> |
|**Oficinas regionales** <br/> |345  <br/> |255.00  <br/> |1320.00  <br/> |1536.00  <br/> |896.10  <br/> |8704.20  <br/> |
|**Sucursales de gran tamaño** <br/> |70  <br/> |102,00  <br/> |600,00  <br/> |384.00  <br/> |216.30  <br/> |32935.20  <br/> |
|**Sucursales pequeñas** <br/> |36  <br/> |76.50  <br/> |600,00  <br/> |384.00  <br/> |123.60  <br/> |61005.00  <br/> |
   
Esto significa que Skype para el tráfico de negocios en línea que se recorra la ruta express será aproximadamente 114 Mbps, Dewey va a necesitar por lo menos la suscripción de 200 Mbps para ExpressRoute. Varios circuitos ExpressRoute se pueden comprar en diferentes ubicaciones de interconexión de ExpressRoute. Esto se recomienda si sitios de Dewey se encuentran en distintas regiones geográficas, o para proporcionar resistencia en caso de que se produce un error en la conexión con el circuito de ExpressRoute. Si compra circuitos ExpressRoute en varias regiones de Azure, el complemento de la prima de ExpressRoute deben recibir la conectividad global a través de ExpressRoute.
  
Ahora que ya tiene la cantidad total de ancho de banda requerido y la clase de servicio (CoS) de servicio proveedores números de ancho de banda puede colocar sus pedidos con la red seleccionada. No olvide incluir estimaciones de tráfico para otras aplicaciones y servicios. Le ofrecemos orientación para otros servicios de Office 365, incluyendo calculadoras de ancho de banda para Exchange y OneDrive de planificación de red. Suscripción de ancho de banda para el proveedor de servicios de red será mayor porque se debe agregarse en el tráfico dentro del sitio. Calculadora de ancho de banda de 2013 y el Lync 2010 ofrece sólo una estimación del tráfico esperado, por lo tanto, se recomienda confirmar la capacidad de la red para admitir ese volumen de tráfico de llevar a cabo una prueba de esfuerzo. 
  
> [!TIP]
> Es muy recomendable probar la red cuando se realiza una evaluación previa de la red. 
  
Una prueba de esfuerzo implica la creación y configuración de la infraestructura y ejecutarlo con el volumen de tráfico simulado esperado al supervisar el rendimiento. Las estimaciones de tráfico pueden ser inexactas en algunas áreas, pero al menos puede estar seguro puede admitir el volumen de tráfico el Lync 2010 y predecir la calculadora de ancho de banda de 2013. Se recomienda que ejecute la prueba de estrés durante un mínimo de unos días, pero ejecutarla durante períodos más prolongados de tiempo le permiten ajustar los números. Sin embargo, extender el período de prueba de carga debe valorarse contra el costo de los servicios de red que vas a pagar que no llevar el tráfico de red de usuario real. Microsoft ha certificado varios proveedores como parte de su programa de IT Pro Tools para proporcionar herramientas de administración y operaciones de red incluyendo herramientas de estrés de evaluación previa de la red. Skype para empresas también proporciona un sistema integradores (SI) que puede tomar el certificado IT Pro Tools y que puede hacer la evaluación de la red para usted. Puede ver más información en [Skype para Business Solutions: IT Pro Tools](https://go.microsoft.com/fwlink/?LinkID=690307).
  
Las pruebas de estrés proporciona cierta tranquilidad que la red puede admitir el volumen de tráfico que se necesitan, pero en realidad la Lync 2010 y 2013 datos Calculadora de ancho de banda pueden estar desactivada por cualquier número de razones. También debe considerar seguir supervisando las redes de sitios haciendo una evaluación continua de red una vez que se implementa para garantizar el ancho de banda es suficiente y que los mecanismos de QoS funcionan correctamente. Es importante seguir supervisando el rendimiento de la red, como usuarios más reales se pusieran en línea.
  
## <a name="part-2-expressroute-skype-for-business-qos"></a>Parte 2: ExpressRoute Skype para QoS de negocio

Servicio de ExpressRoute de Microsoft proporciona una conexión dedicada a la nube de Azure, pero los servicios de comunicación de Office 365 en tiempo Real las cargas de trabajo requieren servicios de red con ancho de banda suficiente para llevar a cabo el volumen de tráfico y son capaces de soportar Experiencia de calidad de servicio (QoS) para ofrecer a un usuario a nivel empresarial. Una conexión debe ser de QoS configurado end-to-end (PC, conmutadores de red y los enrutadores de la nube) como cualquier parte de la ruta de acceso que no admitan QoS podría degradar la calidad de la llamada toda.
  
El propósito de esta sección es ayudarle a comprender los desafíos al soporte de tráfico en tiempo real en una red IP y configuración y soporte técnico de una correcta distribución de ExpressRoute de Office 365 en tiempo Real las cargas de trabajo usando una de Microsoft ExpressRoute Exchange Asociado de negocios proveedor o proveedor de servicios de red.
  
QoS se acepta de sus redes exclusivamente a través de circuitos de red ExpressRoute y se utiliza para el tráfico del negocio dentro de la red de Microsoft de Skype. En la actualidad, partes de algunas conexiones salientes desde Microsoft les faltan valores DSCP de Skype para el negocio. Hasta que el tráfico saliente se marca completamente con valores DSCP, se aconseja seguir las instrucciones para agregar marcadores de QoS al tráfico en los límites de la red como se describe en la sección **Implementación de QoS mediante la lista de Control de acceso (ACL) de red** de este artículo.
  
### <a name="the-real-time-problem"></a>El problema en tiempo Real

Prestación de servicios de voz y vídeo de calidad empresarial coloca las exigencias especiales en una red IP. El tráfico en tiempo real utiliza el protocolo de transporte en tiempo real (RTP) que se realiza mediante el protocolo de datagramas de usuario (UDP). A diferencia de transmisión Control protocolo (TCP) que los números y comprueba cada mensaje para errores e incluye otros mecanismos para detectar y retransmitir los mensajes perdidos o cerrados, UDP no proporciona confiabilidad de este tipo. Si los mensajes están dañados por errores o se pierden debido a los desbordamientos de búfer, se pierden. UDP se eligió para su uso con RTP debido a la naturaleza del tráfico en tiempo real es que aunque se volvieron a enviar los mensajes perdidos, ¿llegan demasiado tarde para que cualquier impacto positivo en el flujo de mensajes de voz.
  
Conocer el impacto de paquetes de voz perdidos, diseñadores propuso dos enfoques para mejorar el rendimiento de vídeo y voz sobre IP:
  
- Hacer la voz de codificación y descodificación más resistente cuando se pierden paquetes. Esto puede hacerse por cualquiera con corrección de errores de reenvío (FEC) para corregir un porcentaje de los errores encontrados, que es una capacidad que se encuentra de transporte en tiempo Real de Office 365, o mediante la voz de diseñar sistemas que intentan enmascarar el efecto de la pérdida de paquetes de descodificación que es una característica de códecs de Microsoft. 
    
- Utilizar los servicios de transporte que utilice calidad de mecanismos de servicios para garantizar el rendimiento de la red con respecto a la demora, pérdida de paquetes y vibración y la variación de retardo entre paquetes.
    
Sólo codificación de voz flexible soluciona el problema de pérdida de paquetes, por lo que es importante que una red que se utiliza para transportar voz en tiempo real y vídeo tienen mecanismos que minimizan la variación y el retraso. Incluso con codificación resistente, si demasiados paquetes se pierden, la estación receptora no tiene información suficiente para reconstruir una versión reconocible de la señal de voz. El porcentaje de paquetes perdidos que daría como resultado una disminución significativa en la calidad de la voz que varía en función de la voz codificación técnica que se utiliza. En todos los casos, sin embargo, perder las cadenas de envíos sucesivos de paquetes es muy problemática.
  
Minimizar el retraso es importante porque retraso excesivo puede afectar el flujo de la conversación y crear una molestia para los altavoces. Mejores prácticas nos dicen que demora end-to-end para voz (lo que conocemos como retraso de boca a oreja) debe mantenerse por debajo de 150 milisegundos (ms). unidireccional, retraso no 'round trip'. Por supuesto, el retardo aumentará en más vínculos de transmisión como los que atraviesan los océanos, dados el retardo en la propagación o el tiempo que tarda la señal en recorrer físicamente el cable.
  
Cuando el retardo va mayor que 150 milisegundos. unidireccional, tiene un efecto extraño en el altavoz. Psicológicamente, un reloj desaparece en el cerebro del orador que les hace pensar que el destinatario no ha oído hablar a ellos y que repita lo último que dijeron. Esto entra en conflicto con la respuesta retardada procedentes de la sede. Si alguna vez ha hablado sobre un canal de satélite reconocerá este efecto. A través de un canal de satélite el retardo unidireccional es aproximadamente 250 ms., que es mucho más allá de la demora permisible.
  
 **Parámetros de red recomendada para la voz de grado empresarial**
  
|**Parámetro**|**Valor recomendado**|
|:-----|:-----|
|Entre la vibración de la llegada de paquetes (promedio)  <br/> |≤ 5 MS  <br/> |
|Entre la vibración de la llegada de paquetes (máximo)  <br/> |INFERIOR O IGUAL A 40MS  <br/> |
|Velocidad de pérdida de paquetes (promedio)  <br/> |0% alcanzando  <br/> |
|Una forma de latencia de la red  <br/> |≤ 100 ms (debe incluir el control del retraso frente a distancia geográfica)  <br/> |
   
### <a name="expressroute-as-part-of-a-business-grade-voice-network"></a>ExpressRoute como parte de una red de voz de grado empresarial

ExpressRoute ofrece una conexión dedicada a través de un proveedor de servicio de red (NSP) o un proveedor de Exchange (EXP) en uno de los 3 opciones de conexión: 
  
- Ubicación cooperativa de intercambio de nube
    
- Conexión Ethernet de punto a punto
    
- Para cualquier conexión (IPVPN)
    
Esto proporciona ventajas de alta disponibilidad (99,9% de tiempo activo SLA) y enrutamiento confiable es decir proteger (sin tránsito de internet), afectados por las variaciones en el tráfico de Internet y aspectos marcas de calidad de servicio para dar prioridad al tráfico (QoS se explica a continuación) . ExpressRoute, junto con una WAN bien planeada puede proporcionar una red de voz de grado empresarial.
  
Puede utilizar ExpressRoute para el tránsito de datos de oficinas o centros de datos (si topología híbrido) que están conectados con el circuito. Datos de los usuarios fuera del sitio (por ejemplo, desde oficinas en casa, o viajando, etc.) no aprovechan el circuito de ExpressRoute, a menos que los usuarios están conectado de VPN y no necesitan incluirse en las estimaciones de ancho de banda para el circuito de ExpressRoute de tamaño. Si usted es un cliente multinacional, puede adquirir circuitos ExpressRoute en cada región y utilizar etiquetas de la Comunidad BGP para informar a las reglas de enrutamiento para que el tráfico se dirige al circuito de ExpressRoute preferido (normalmente el más cercano uno por cada sitio), mientras que el otro circuitos ofrecen redundancia en caso de una interrupción que afecta a un solo circuito. 
  
### <a name="if-expressroute-isnt-an-option"></a>Si ExpressRoute no es una opción

Puede no ser factible para conectar todos los sitios a ExpressRoute, ya sea debido a los costos, incapacidad para cumplir los requisitos previos de ExpressRoute o limitaciones de su actual NSP. Si es que no pueden utilizar ExpressRoute se sigue recomienda que sigan los consejos a continuación para marcar QoS dentro de su red y planificar los contratos con los NSP para asegurar suficiente ancho de banda y soporte para la asignación de prioridades de tráfico basado en QoS.
  
Además, si dispone de oficinas en varias regiones, pero no tienen circuitos ExpressRoute en todas las regiones deben utilizar las etiquetas de región BGP Comunidad al configurar el enrutamiento para el tráfico hacia y desde las oficinas satélite de manera que puede evitar el tránsito innecesario largo alcance. Por ejemplo, imagine una empresa que tenga un Skype para la organización de los negocios en línea alojado en Estados Unidos, pero con sucursales en Europa, y la empresa sólo tiene un solo circuito de ExpressRoute en Silicon Valley. La mayoría de lo Skype para tráfico de negocios en línea se enrutarán a un centro de datos donde se aloja la organización (por ejemplo, llamadas de conferencia con otros usuarios de la compañía), puede ser preferible para la mayor parte del tráfico usando el circuito de ExpressRoute. Sin embargo, si un usuario en Europa para unirse a una conferencia alojada por otra empresa cuya organización está ubicada en Europa, el destino de los medios de comunicación en esa llamada sería el centro de datos Europeo donde se encuentra la segunda empresa. Enruta el tráfico a través del circuito de ExpressRoute en Silicon Valley sería una ruta menos directa que sería posible a través de Internet. En tal caso, es aconsejable configurar los enrutadores de la red (por ejemplo, en las oficinas europeas) para inspeccionar las etiquetas de la Comunidad al realizar el enrutamiento reglas y enrutamiento a través de Internet en lugar de Silicon Valley ExpressRoute circuito para el tráfico que tiene Etiquetas de la región de Europa.
  
### <a name="basic-concepts-of-quality-of-service-qosclass-of-service-cos"></a>Conceptos básicos de calidad de servicio (QoS) y clase de servicio (CoS)

En IP, calidad de servicio (QoS) describe cualquier mecanismo que se utiliza para proporcionar control de prioridad para algunos paquetes en detrimento de otros. Según la definición de la Unión internacional de telecomunicaciones (UIT), QoS abarca todos los aspectos de calidad de una conexión como retraso, pérdida, relación señal / ruido, interferencia, eco, interrupciones, respuesta en frecuencia, los niveles de volumen y así sucesivamente. Lo que conocemos como QoS en redes de paquetes es más correctamente denominan clase de servicio (CoS) que se centra en mejorar el rendimiento de retraso, inestabilidad y pérdida de paquetes, pero continuaremos usando el término de QoS cuando se utiliza más comúnmente.
  
Proporcionar QoS en una dirección IP de red llama de dos componentes principales:
  
- La reserva de una cantidad definida de ancho de banda en cada vínculo para el tráfico en tiempo real; Si dicho ancho de banda no es necesario para el tráfico en tiempo real en cualquier momento, puede usarlo para otro tráfico. La regla general es que no supere el 30% de la capacidad de cualquier vínculo debe asignarse para el tráfico de voz.
    
- Marcar los paquetes con un indicador de prioridad en el encabezado que indica a los conmutadores y enrutadores en la ruta de la prioridad del paquete que se debe asignar.
    
Cuando se recibe un paquete en un switch o router, se mueve a una cola de salida para el siguiente tramo o salto. Hay colas de salida diferente para los diferentes niveles de prioridad. Un conmutador o un enrutador utiliza un algoritmo de servicios con más frecuencia que las colas de prioridad más baja de la cola de prioridad alta.
  
El desafío es que hay diferentes técnicas de QoS que se implementan en el nivel 2 (es decir, la capa Ethernet o Wi-Fi) y Layer 3 (es decir, la capa IP). Las diferentes implementaciones de QoS pueden deben configurarse en cada conmutador y enrutador en la red, así como la interfaz entre la red y la red del proveedor de servicio de red.
  
Hay dos opciones para cómo se pueden asignar datos desde los distintos Skype para aplicaciones empresariales a las clases correspondientes de servicio:
  
- Marcador de punto final del tráfico mediante servicios diferenciados Control punto (DSCP) 
    
- Lista de Control de acceso (ACL) de red-base
    
### <a name="end-point-traffic-marking--differentiated-services-control-point-dscp"></a>Punto final tráfico marcado diferenciados por punto de Control de servicios (DSCP)

Servicios diferenciados (DiffServ) se conoce como un mecanismo de "grano grueso" para clasificar y administrar el tráfico de red y proporcionar QoS en redes IP. Enrutadores y otros dispositivos que implementan las funciones de capa 3 utilizan el punto de Control de DiffServ (DSCP) para definir la prioridad del paquete. QoS se implementa mediante la inserción de un valor DSCP de 6 bits en el campo de servicios diferenciados (anteriormente el campo "Tipo de servicio") en el encabezado IP; 6 bits permite 64 niveles de prioridad diferente. Los niveles de prioridad se definen normalmente como se muestra aquí.
  
 **Configuración recomendada de DSCP**
  
|**Clase de tráfico**|**Tratamiento (marcado de DSCP)**|**Skype para cargas de trabajo empresariales**|
|:-----|:-----|:-----|
|**Voz** <br/> |EF (46)  <br/> |Skype para voz empresarial y Lync  <br/> |
|**Interactivo** <br/> |AF41 (34)  <br/> |Vídeo  <br/> |
||AF21 (18)  <br/> |Uso compartido de aplicaciones  <br/> |
|**Predeterminado** <br/> |AF11 (10)  <br/> |Transferencia de archivos  <br/> |
||EL SISTEMA CS0 (0)  <br/> |Algo más  <br/> |
   
 **Encabezado de IP versión 4**
  
![Encabezado de IPv4](../images/c8a6a714-2784-4328-8297-2e62706f302d.png)
  
### <a name="layer-2-qos-ieee-8021pwi-fi-multi-media-ieee-80211e"></a>QoS de capa 2: IEEE 802.1p y Wi-Fi multimedia (IEEE 802. 11e)

Aunque DSCP es el mecanismo estándar para la implementación de QoS en el nivel 3, existen diferentes mecanismos de QoS de capa 2 para cableada (por ejemplo, Ethernet) e inalámbricas (es decir, las redes Wi-Fi). El mecanismo de QoS para las redes cableadas se define en el estándar IEEE 802.1p; el mecanismo de QoS de WLAN se define en IEEE 802. 11e, lo que la Wi-Fi Alliance se identifica como "Certificación Wi-Fi multimedia" (certificado de WMM).
  
El IEEE 802.1p utiliza un punto de código de prioridad de 3 bits (PCP) para identificar la prioridad del mensaje; el PCP forma parte de un campo de 32 bits en el encabezado de Ethernet que también lleva el identificador VLAN. Las definiciones de los valores de PCP se incluyen a continuación.
  
 **Valores de PCP IEEE 802.1p**
  
|**Valor de PCP**|**Prioridad**|**Acrónimo**|**Tipos de tráfico**|
|:-----|:-----|:-----|:-----|
|7  <br/> |7  <br/> |NC  <br/> |Control de la red  <br/> |
|6  <br/> |6  <br/> |IC  <br/> |Control de interconexión de redes  <br/> |
|5  <br/> |5  <br/> |VO  <br/> |Voz  <br/> |
|4  <br/> |4  <br/> |VI  <br/> |Vídeo  <br/> |
|3  <br/> |3  <br/> |ENTIDAD EMISORA DE CERTIFICADOS  <br/> |Aplicaciones críticas  <br/> |
|2  <br/> |2  <br/> |EE  <br/> |Excelente  <br/> |
|0  <br/> |1  <br/> |SER  <br/> |Mejor esfuerzo  <br/> |
|1  <br/> |0  <br/> |BK  <br/> |Información general  <br/> |
   
Donde se implementa IEEE 802.1p en forma similar a como DSCP con tráfico ordenados en colas de prioridad diferente para cada nivel de prioridad, pero la naturaleza de medios compartidos de llamadas de las WLAN para un enfoque diferente. Mientras que el punto de acceso y el cliente mantendrá las colas de salida distintas para los diferentes niveles de prioridad, también existen diferencias en cómo se envían los marcos en el canal de radio.
  
En una red Wi-Fi, todos los clientes asociados a un punto de acceso comparten un único canal dúplex medio (es decir, el punto de acceso o estación de un único cliente puede enviar a la vez). Para minimizar el potencial de colisiones en el canal de radio, antes de enviar una trama que la estación espera a que el canal esté inactivo durante un período definido de tiempo llamado un "espaciado entre tramas," si el canal está ocupado cuando una estación se va a enviar, retrocede un peri de tiempo aleatorio od. Una vez que la trama se envía si el remitente no recibe un mensaje de confirmación del destinatario, se supone una colisión o se ha producido otro error y pasos atrás en un intervalo aleatorio antes de intentar acceder al canal de radio para enviar. El intervalo de interrupción es aleatorio para reducir la probabilidad de que las mismas dos estaciones colisionarán otra vez.
  
Priorizar el acceso a la radio del canal, IEEE 802. 11e / WMM define diferentes intervalos de espera de transmisión previo llamados "Arbitrated entre tramas espaciados" (AFIS) y diferentes rangos de interrupción las diferentes clases de tráfico; se definen cuatro niveles de prioridad llamados 'Categorías de acceso'.
  
Se da prioridad asignando valores AFIS más corto a los marcos de prioridad superior. Así que si una estación está esperando para enviar una trama de voz y el otro está esperando para enviar una trama de datos, el marco de voz siempre se enviará primero. Técnicamente, voz y vídeo marcos se asignan el mismo valor AFIS, pero el intervalo de interrupción intervalos de fotogramas de vídeo es superior. Así que mientras una voz y un fotograma de vídeo pueden entrar en conflicto en el primer intento, el marco de voz siempre se retransmitirá antes. La correlación entre IEEE 802.1p y IEEE 802. 11e se muestra a continuación:
  
 **IEEE 802. 11e / asignación multimedia Wi-Fi (WMM) para 802.1p**
  
|**Categoría de acceso WMM**|**Descripción de WMM**|**Valor de PCP 802.1p**|**Designación de 802.1p**|
|:-----|:-----|:-----|:-----|
|1 (AC_VO)  <br/> |Voz  <br/> |7 (111)  <br/> |NC  <br/> |
|6 (110)  <br/> |VO  <br/> |
|2 (AC_VI)  <br/> |Vídeo  <br/> |5 (101)  <br/> |VI  <br/> |
|4 (100)  <br/> |CL  <br/> |
|3 (AC_BE)  <br/> |Datos de mejor esfuerzo  <br/> |3 (011)  <br/> |EE  <br/> |
|0 (000)  <br/> |SER  <br/> |
|4 (AC_BK)  <br/> |Datos de fondo  <br/> |1 (001)  <br/> |BK  <br/> |
|2 (010)  <br/> |---  <br/> |
   
La asociación recomendada de capa 3 a las prioridades de nivel 2 es el siguiente:
  
 **Recomienda Layer 3 asociaciones de prioridad de capa 2**
  
||**Marcadores de capa 3**|**Nivel 2 (valor de PCP)**|**Wi-Fi (categoría de acceso)**|
|:-----|:-----|:-----|:-----|
|Control de la red  <br/> |Por comportamiento de salto (PHB) - Selector de clase (CS) 6  <br/> |6  <br/> |1 (AC_VO)  <br/> |
|Valor DSCP -48  <br/> |
|Voz  <br/> |Por comportamiento de salto (PHB)-Expedited Forwarding (EF)  <br/> |5  <br/> |1 (AC_VO)  <br/> |
|Valor DSCP - 46  <br/> |
|Sistemas de videoconferencia  <br/> |Por comportamiento de salto (PHB) - asegurado (AF) 41 de reenvío  <br/> |4  <br/> |2 (AC_VI)  <br/> |
|Valor DSCP - 34  <br/> |
|Llame a la señalización  <br/> |Por comportamiento de salto (PHB) - Selector de clase 3 (CS)  <br/> |3  <br/> |2 (AC_VI)  <br/> |
|Valor DSCP - 24  <br/> |
|Datos de latencia baja  <br/> |Por comportamiento de salto (PHB)-asegurado (AF) 21 de reenvío  <br/> |2  <br/> |3 (AC_BE)  <br/> |
|Valor DSCP -18  <br/> |
|Datos de alto rendimiento  <br/> |Por comportamiento de salto (PHB) - asegurado (AF) 11 de reenvío  <br/> |1  <br/> |3 (AC_BE)  <br/> |
|Valor DSCP - 10  <br/> |
|Mejor esfuerzo  <br/> |Por comportamiento de salto (PHB) - 0  <br/> |0  <br/> |4 (AC_BK)  <br/> |
|Valor DSCP - 0  <br/> |
   
Es importante tener en cuenta que hay una incoherencia en los códigos de prioridad de IEEE 802.1p y WMM. El valor del PCP para voz de 802.1p es 5, sin embargo, en la asignación estándar de equivalencia de WMM, PCP 5 se convierte en categoría 2 de Access, la categoría de acceso WMM para vídeo (AC_VI). Si es posible debe reemplazar la asignación para que el PCP 5 se traduce en 1 de la categoría de acceso, o simplemente evitar utilizar voz y vídeo en la misma red Wi-Fi hasta que la Wi-Fi Alliance soluciona este problema. Para obtener información adicional sobre Wi-Fi, consulte [Los artículos de catálogo de Wi-Fi]( https://go.microsoft.com/fwlink/?LinkId=690322).
  
### <a name="implementing-qos-using-network-access-control-list-acl"></a>La implementación de QoS mediante la lista de Control de acceso (ACL) de red

El método alternativo de la implementación de QoS en una configuración de ExpressRoute es utilizar la lista de Control de acceso (ACL) de red. En que el enfoque, en lugar de tener los puntos finales inserta el marcado de DSCP correspondiente en el encabezado de cada paquete, el marcado puede realizarse mediante un enrutador de nivel superior, basado en el puerto de origen UDP. Todos los conmutadores y enrutadores aún deben configurarse para admitir QoS para asegurar que se mantienen los valores DSCP. Más importante aún, el enrutador conectado a la red del proveedor de servicios debe mantener en el encabezado de cada paquete, DSCP como ese valor DSCP es esencialmente la instrucción al proveedor de servicios de red de cómo se debería tratar ese paquete.
  
Los intervalos de puerto recomendado para cada Skype para aplicación empresarial se enumeran en la sección 2.6.1.1 de la Guía de [Planificación de redes, supervisión y solución de problemas con Lync Server](https://go.microsoft.com/fwlink/?LinkId=690286) . Es importante que esto se coordinan con el enfoque global de la organización de QoS y debe a la caza de diferentes políticas de QoS y posibles discrepancias de nomenclaturas de paquetes.
  
Mientras que es la razón principal se utilizan servicios de red QoS y MPLS garantizar una buena experiencia de usuario de voz en tiempo real y el vídeo, esas mismas funciones pueden aplicarse también a las aplicaciones de datos. En lugar de tratar igualmente a todas las aplicaciones, redes MPLS pueden permiten a las organizaciones a dar prioridad a algunas aplicaciones de datos sobre otros. Con MPLS, aplicaciones en tiempo real como transacciones de tarjeta de crédito o compartir la pantalla pueden tener prioridad sobre menos tráfico confidencial de tiempo como el correo electrónico.
  
### <a name="understanding-the-types-of-ip-network-services--basic-ip-and-mpls"></a>Descripción de los tipos de IP red servicios básicos IP y MPLS

El reenvío de paquetes IP original funciona sobre el principio de "mejor esfuerzo". Eso significaba que los enrutadores reenvíen los paquetes IP haría su mejor para entregarlos a sus destinos, pero no había absolutamente ninguna garantía con respecto a cuando o si llegan a sus destinos. Que es la forma básicos servicios de Internet, incluyendo la conexión a Internet doméstica, trabajo hoy. La idea era que si confiabilidad era necesaria para una aplicación determinada, se podría proporcionar en un nivel superior de la pila de protocolos. El mecanismo de entrega confiable es el protocolo de Control de transmisión (TCP). El protocolo de datagrama de usuario (UDP), que se utiliza para vídeo y voz en tiempo real, es la entrega no confiable (es decir, "mejor esfuerzo") mecanismo. 
  
Multi-Protocol Label Switching (MPLS) se desarrolló como un medio para proveedores de servicios de red para la oferta de una dirección IP de servicio con rendimiento garantiza retardo, vibración y pérdida de paquetes. Para ofrecer las garantías de buen fin, MPLS toma algunas de las inesperadas de IP tradicional. En primer lugar, en lugar de tener cada paquete encontrar el camino al enrutador a su destino (cuyo resultado podría ser que cada paquete tiene una ruta diferente desde el origen al destino), MPLS enruta todos los paquetes en una conexión "circuito virtual" con un ruta fija llama un Label Switched Path (LSP). Si se produce un error en uno de los vínculos de esa ruta, todos los proveedores de servicios lingüísticos con ese vínculo rápidamente se redistribuirá.
  
Cuando se envía un paquete a la red MPLS enrutador de borde del proveedor de servicios de red anexa un encabezado adicional al paquete que incluye una etiqueta que se utiliza para reenviarlo sobre el LSP apropiado. La etiqueta se separa por el enrutador de borde en el otro extremo de la red MPLS.
  
Al lado de simplificar el proceso de reenvío, MPLS ofrece otra ventaja es que el sistema de administración de red sabrá qué conexiones se están realizando en todos los vínculos de la red. Al controlar la forma en que el tráfico se enruta a través de la red, el operador puede garantizar la QoS proporcionará cada ruta. Así que a diferencia el mejor rendimiento de esfuerzo de IP tradicional o básica, operadores MPLS pueden proporcionar un servicio IP con un performance predecible. Que LSP hace también MPLS inherentemente más seguro que los servicios de Internet tradicionales. Por lo que con el servicio IP básico podemos esperar que la red llevará a cabo bien suficiente para proporcionar la voz de buena calidad y utilizar técnicas como FEC y más resistente la voz para mejorar las probabilidades de codificación, pero utilizando MPLS, podemos estar seguros de.
  
Proveedores de MPLS ofrecen varias clase de degradados de servicio que Desafortunadamente utiliza términos diferentes para identificarlas. Tendrá que trabajar estrechamente con su proveedor para asegurarse de que comprenden las salidas de [Lync 2010 y 2013 Calculadora de ancho de banda](https://go.microsoft.com/fwlink/?LinkID=690282) y las opciones recomendadas para diferentes aplicaciones de cargas de trabajo de Office 365 en tiempo Real.
  
## <a name="conclusion"></a>Conclusión

Skype para empresas mejora la forma en que se llevan a cabo las comunicaciones empresariales. En lugar de tener un teléfono conectado a un sistema PBX, un sistema de videoconferencia independiente, una plataforma independiente para correo electrónico, un servicio externo para conferencias de audio y algunos vehículo para mensajería instantánea y presencia, Skype para empresas puede reunir todas estas capacidades en una única interfaz de usuario.
  
Proporcionando servicios de vídeo y voz en tiempo real de grado empresarial requiere una infraestructura de red end-to-end que es capaz de proporcionar QoS. Que incluiría los servicios WAN y LAN. Microsoft proporciona herramientas como la [Calculadora de ancho de banda de 2013 y Lync 2010](https://go.microsoft.com/fwlink/?LinkID=690282) para estimar la capacidad de red que necesarios para los distintos servicios. Además, hay socios en el programa IT Pro Tools [Skype para Business Solutions: IT Pro Tools](https://go.microsoft.com/fwlink/?LinkID=690307) que ofrecen herramientas para evaluar previamente la infraestructura de red y soporte de monitoreo, reporting y solución de problemas. Sin una infraestructura de red de tamaño y configurado correctamente, se corre el riesgo de tener un Skype ExpressRoute de implementación de negocios que no satisfaga las expectativas del usuario para la calidad y la coherencia.
  
Herramientas empresariales eficaces deben realizar de forma fiable, coherente y ofrecer una experiencia de usuario que fomente la adopción del usuario. Desde una perspectiva de red significa tener una infraestructura de red, área local y extensa, fija y móvil, que puede permitir que esto suceda. Planear, diseñar, implementar y mantener que la infraestructura no es siempre una tarea fácil. Hardware, herramientas y servicios de red para lograr están disponibles hoy en día, pero es responsabilidad del profesional de TI para ver que son diseñados, implementados y mantiene de una manera que garantiza a que los usuarios obtendrán un conjunto de servicios de colaboración y comunicaciones que les permiten trabajar de forma eficiente y eficaz y que la organización puede aprovechar todas las ventajas de esta tecnología de qué tiene que ofrecer. 
  
## <a name="related-topics"></a>Temas relacionados

[Documentación de ExpressRoute](https://go.microsoft.com/fwlink/?LinkId=690285)

