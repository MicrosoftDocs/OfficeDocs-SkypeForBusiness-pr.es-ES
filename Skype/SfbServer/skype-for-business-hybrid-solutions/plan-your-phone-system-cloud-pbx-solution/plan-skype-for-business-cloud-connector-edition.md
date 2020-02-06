---
title: Plan para Skype Empresarial Cloud Connector Edition
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 6ce0e580-8c4a-45de-a54f-e39e438335d6
description: Obtenga información sobre Skype Empresarial Cloud Connector Edition, un conjunto de máquinas virtuales (VM) empaquetadas que implementa la conectividad RTC local con el Sistema telefónico de Office 365 (PBX en la nube).
ms.openlocfilehash: 20ea88b230fe0fd9a590c489cb6f0017a2c27209
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814468"
---
# <a name="plan-for-skype-for-business-cloud-connector-edition"></a>Plan para Skype Empresarial Cloud Connector Edition

Obtenga información sobre Skype Empresarial Cloud Connector Edition, un conjunto de máquinas virtuales (VM) empaquetadas que implementa la conectividad RTC local con el Sistema telefónico de Office 365 (PBX en la nube).

Cloud Connector Edition puede ser la solución adecuada para su organización si todavía no tiene una implementación de Lync Server o Skype empresarial Server existente. Si todavía está investigando qué sistema telefónico en la solución de Office 365 es adecuado para su empresa, vea [soluciones de telefonía de Microsoft](https://docs.microsoft.com/en-us/SkypeForBusiness/hybrid/msft-telephony-solutions).

Este documento describe los requisitos de Cloud Connector Edition y las topologías compatibles, y le ayuda a planificar la implementación de Cloud Connector Edition. Asegúrese de leer este tema antes de configurar el entorno de conector de la nube. Cuando esté listo para implementar y configurar Cloud Connector Edition, vea [configurar y administrar Cloud Connector de Skype empresarial](configure-skype-for-business-cloud-connector-edition.md).

Cloud Connector Edition 2,1 ya está disponible. Si aún no ha actualizado a la versión 2.1, consulte [Upgrade to a new version of Cloud Connector](upgrade-to-a-new-version-of-cloud-connector.md). Puede encontrar el archivo de instalación en [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller).

> [!NOTE]
> Microsoft admite la versión anterior de Cloud Connector Edition para 60 días después de la publicación de una nueva versión. Microsoft admitirá la versión 2.0.1 durante 60 días después de la publicación de 2.1 para darle tiempo para la actualización. Todas las versiones anteriores a 2.0.1 han dejado de ser compatibles.

Cloud Connector Edition es una oferta híbrida que consta de un conjunto de máquinas virtuales (MV) empaquetadas que implementan conectividad RTC local con el sistema telefónico en Office 365. Al implementar una topología mínima de Skype empresarial Server en un entorno virtualizado, los usuarios de su organización que estén alojados en la nube pueden recibir servicios de PBX de la nube de Microsoft, pero la conectividad RTC se proporciona a través de la voz local existente infraestructura.

![Diagrama de topología que muestra la puerta de enlace de Cloud PBX conectando Cloud PBX a una implementación local de Skype Empresarial.](../../media/bd898e69-6458-4276-aebe-1854f28ed6fa.png)

Dado que Cloud Connector le permite integrar los servicios del Sistema telefónico de Office 365 con su entorno de telefonía existente (por ejemplo, PBX, dispositivos análogos y los centros de llamadas), puede implementar una migración en fases desde su solución de telefonía actual al Sistema telefónico de Office 365.

Por ejemplo, suponga que su empresa tiene un centro de llamadas sofisticado con una funcionalidad específica que el Sistema telefónico de Office 365 no proporciona. Puede elegir dejar a los usuarios del centro de llamadas con la solución existente, pero mover a otros usuarios al Sistema telefónico de Office 365.

Cloud Connector proporcionará enrutamiento entre los usuarios alojados en local y en línea, y puede elegir usar su propio proveedor RTC con el Sistema telefónico de Office 365.

Tenga en cuenta lo siguiente al planear la implementación de Cloud Connector Edition:

- Para usar Cloud Connector para aprovechar las soluciones de voz en la nube, necesitará suscribirse a un inquilino de Office 365 que incluya el sistema telefónico en Office 365. Si todavía no tiene un inquilino de Office 365, puede obtener información sobre cómo suscribirse aquí: [Office 365 para empresas](https://products.office.com/en-us/business/office). Tenga en cuenta que tendrá que suscribirse a un plan que incluya Skype empresarial online.

- Para registrar los equipos de conector de nube con el servicio de Skype empresarial online y para ejecutar varios cmdlets, el conector de nube 2,0 y versiones posteriores requieren una cuenta de Office 365 dedicada con los derechos de administrador de inquilinos de Skype empresarial. Las versiones de Cloud Connector anteriores a 2.0 requieren una cuenta de Office 365 dedicada con los derechos de administrador global de inquilinos.

- El conector de nube no requiere una implementación de Skype empresarial Server completa.

    En la actualidad, el conector de nube no puede coexistir con servidores locales de Lync o Skype empresarial. Si quiere mover los usuarios existentes de Lync o Skype empresarial a Office 365 y mantener la telefonía local a sus usuarios, considere sistema telefónico en Office 365 con conectividad local usando una implementación existente de Skype empresarial Server. Para obtener más información, vea [planear el sistema telefónico en la solución de office 365 (nube PBX)](plan-your-phone-system-cloud-pbx-solution.md) y [planificar el sistema telefónico en Office 365 con conectividad RTC local en Skype empresarial Server](plan-phone-system-with-on-premises-pstn-connectivity.md).

- Si tenía una implementación anterior de Skype empresarial o de Lync Server y ha ampliado el esquema, no es necesario que limpie el esquema para la implementación de Cloud Connector, siempre y cuando haya eliminado todos los componentes de Skype empresarial o Lync Server de su entorno.

- Los usuarios están hospedados en línea.

- Si su organización ha configurado la sincronización de directorios (DirSync), todas las cuentas de los usuarios que se han planificado para la voz híbrida se deben crear primero en su implementación local y, a continuación, sincronizarse con la nube.

- Si es necesario, puede mantener su operador de RTC actual.

- Si desea proporcionar conferencias de acceso telefónico local a los usuarios alojados en el conector de nube, puede comprar una licencia de conferencias RTC o pagar a medida que habla de las conferencias de audio de Microsoft.

- La licencia de conferencia de audio (o la oferta de paga y habla) también es necesaria para el escalamiento de llamadas. Si un usuario de Skype empresarial recibe una llamada de un usuario de la RTC externa y quiere agregar un participante más a esa llamada (escalar la llamada a una conferencia), la extensión se realizará a través del servicio de conferencia de audio de Microsoft.

- Cloud Connector 2.0 y las versiones posteriores son compatibles ahora con la omisión de medios. La omisión de elementos multimedia permite a un cliente enviar archivos directamente al próximo salto de la red telefónica conmutada (RTC), una puerta de enlace o un controlador de borde de sesión (SBC), y eliminar el componente Cloud Connector Edition de la ruta multimedia. Para obtener más información, vea [planear el omisión de medios en Cloud Connector Edition](plan-for-media-bypass-in-cloud-connector-edition.md).

- Cloud Connector 2.1 y versiones posteriores admiten la supervisión de Cloud Connector mediante Operations Management Suite (OMS). Para obtener más información, vea [Monitor Cloud Connector using Operations Management Suite (OMS)](monitor-cloud-connector-using-operations-management-suite-oms.md).

- El conector de nube está disponible en todos los países donde está disponible Office 365 Enterprise E5.

Este tema incluye las secciones siguientes:

- [Componentes de Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md#BKMK_Components)

- [Topologías de edición del conector para la nube](plan-skype-for-business-cloud-connector-edition.md#BKMK_Topologies)

- [Requisitos para la implementación](plan-skype-for-business-cloud-connector-edition.md#BKMK_Requirements)

- [Información que necesita reunir antes de la implementación](plan-skype-for-business-cloud-connector-edition.md#BKMK_PlanDeployment)

- [Consideraciones de plan de marcado](plan-skype-for-business-cloud-connector-edition.md#BKMK_DailPlan)

- [Consideraciones sobre alta disponibilidad](plan-skype-for-business-cloud-connector-edition.md#BKMK_HA)

- [Flujo multimedia de Cloud Connector](plan-skype-for-business-cloud-connector-edition.md#BKMK_MediaFlow)

- [Supervisión y solución de problemas](plan-skype-for-business-cloud-connector-edition.md#BKMK_Monitor)

- [Para más información](plan-skype-for-business-cloud-connector-edition.md#BKMK_MoreInfo)

## <a name="cloud-connector-edition-components"></a>Componentes de Cloud Connector Edition
<a name="BKMK_Components"> </a>

Con Cloud Connector Edition, se implementa un conjunto de máquinas virtuales empaquetadas que contienen una topología de servidor de Skype empresarial mínima, que consta de un componente perimetral, un componente de mediación y un rol de almacén de administración central (CMS). También instalará un controlador de dominio, que es necesario para el funcionamiento interno del conector de nube. Estos servicios están configurados para su entorno híbrido con el inquilino de Office 365 que incluye los servicios de Skype empresarial online.

![Componentes de Cloud Connector Edition](../../media/f2d4b8a7-c2f4-4cfc-8137-f187399c1298.png)

Los componentes de conector de nube proporcionan la siguiente funcionalidad:

- **Componente perimetral** : la comunicación entre la topología local y los servicios en línea pasa por el componente de borde, que incluye los siguientes componentes:

  - **Perimetral de acceso** : proporciona enrutamiento SIP entre la implementación local y Skype empresarial online.

  - **Retransmisión multimedia** : proporciona el enrutamiento de medios entre el componente de mediación y otros puntos de conexión multimedia.

  - **Autenticación de retransmisión de multimedia/MRAS** : genera tokens para el acceso a media Relay.

- **Enrutamiento saliente** : proporciona equilibrio de carga del tráfico de voz entre puertas de enlace o SBCS conectados a un dispositivo de conector de nube. Las llamadas se dividirán uniformemente entre todas las puertas de enlace o los SBC conectados al dispositivo de Cloud Connector.

    Proporciona enrutamiento a las puertas de enlace en función de las directivas. Solo se admiten las directivas globales que están basadas en números RTC de destino (salida).

- **Rol de almacén de administración central (CMS)** : incluye el almacén de configuración para los componentes de topología, incluyendo la transferencia de archivos CMS.

- **Réplica del almacén central de administración (CMS)** : sincroniza la información de configuración de la base de datos global CMS en el servidor de roles de CMS.

- **Controlador de dominio** : los servicios de dominio de Active Directory del conector de nube almacenan todos los valores y la configuración global necesarios para implementar los componentes del conector en la nube. Se creará un bosque para cada equipo de conector de nube. El controlador de dominio no debe tener ninguna conexión con Active Directory de producción. Los servicios de Active Directory incluyen:

  - Servicios de dominio de Active Directory

  - Servicios de certificados de Active Directory para emitir certificados internos

- **Componente de mediación** : implementa el protocolo de asignación de puertas de enlace de medios y SIP entre Skype empresarial y las puertas de enlace RTC. Incluye una réplica de CMS que sincroniza la configuración de la base de datos global de CMS.

## <a name="cloud-connector-edition-topologies"></a>Topologías de edición del conector para la nube
<a name="BKMK_Topologies"> </a>

Para este contenido, haremos referencia a sitios RTC. Un sitio RTC es una combinación de equipos de conexión en la nube, implementada en la misma ubicación y con puertas de enlace RTC comunes conectadas a ellos. Los sitios RTC le permiten lo siguiente:

- Proporcionar conectividad a las puertas de enlace más próximas a sus usuarios.

- Permita la escalabilidad mediante la implementación de varios dispositivos de conector de nube en uno o más sitios de la RTC.

- Permita una alta disponibilidad al implementar varios dispositivos de conector de nube en un único sitio de PSTN.

Este tema explica los sitios RTC. Para obtener más información sobre cómo planificar los sitios RTC, consulte [Plan for Cloud Connector Edition PSTN sites](plan-for-cloud-connector-edition-pstn-sites.md).

Puede implementar las siguientes topologías de conector de nube:

- Un único dispositivo Cloud Connector Edition por sitio RTC. Esta topología se recomienda para propósitos de evaluación solo, porque no proporciona alta disponibilidad.

- Varios dispositivos de la nube Connector Edition por sitio RTC para proporcionar alta disponibilidad.

- Varios sitios RTC con varios dispositivos de la edición de la nube para proporcionar escalabilidad con alta disponibilidad. Puede implementar hasta 200 sitios.

Al planificar su topología, tenga en cuenta lo siguiente:

- Con el conector para la nube 2,0 y versiones posteriores, un sitio PSTN puede tener hasta 16 dispositivos de conexión de nube. Las versiones anteriores admiten hasta 4 dispositivos por sitio.

- Existen dos tipos de configuraciones de hardware probadas con el conector de nube:

  - La versión mayor puede administrar grandes volúmenes de llamadas simultáneas y es compatible con todos los tipos de entornos de producción.

  - La versión menor está pensada para ejecutarse en hardware de menor potencia y puede usarse para propósitos de evaluación o para sitios con un volumen de llamadas reducido. Aunque implemente una versión menor de Cloud Connector, también deberá tener en cuenta los requisitos de hardware de clase de producción (como fuentes de alimentación dobles).

- Si tiene Cloud Connector versión 2,0 o posterior e implementa la configuración máxima de 16 dispositivos (con hardware más grande), su sitio RTC puede atender hasta 8.000 llamadas simultáneas. Si implementa la versión más pequeña, el límite permitido será de 800.

    También tiene que dedicar algunos dispositivos a la alta disponibilidad. La recomendación mínima es que se reserve un dispositivo a la alta disponibilidad.

  - Con la versión 2, si implementa una configuración de 15 + 1, su sitio PSTN puede atender hasta 7.500 llamadas simultáneas.

  - Si tiene una versión anterior e implementa la configuración máxima de 3+1 (con mayor hardware), su sitio RTC puede administrar hasta 1.500 llamadas simultáneas. Si implementa la versión menor, el límite es de 150.

-  Si necesita tener más llamadas por sitio de RTC, puede escalar si implementa sitios de RTC adicionales en la misma ubicación.

> [!NOTE]
> A menos que se indique lo contrario, los diagramas y ejemplos siguientes suponen el uso de la versión más grande del conector en la nube.

### <a name="single-cloud-connector-appliance-within-a-single-pstn-site"></a>Dispositivo único de Cloud Connector en un solo sitio RTC.

En el siguiente diagrama se muestra un solo dispositivo Cloud Connector Edition en un único sitio de PSTN. Tenga en cuenta que Cloud Connector consta de cuatro máquinas virtuales instaladas en una máquina host física que está dentro de una red perimetral por razones de seguridad.

![Una instancia de Cloud Connector con un sitio de RTC](../../media/7ffe6953-8c66-4323-940e-cd2e6c3c2a66.png)

### <a name="multiple-cloud-connector-appliances-within-a-single-pstn-site"></a>Varios dispositivos de Cloud Connector en un solo sitio RTC.

 Por motivos de escalabilidad y alta disponibilidad, puede elegir tener varias ediciones de conector de nube en un único sitio de PSTN, tal y como se muestra en el siguiente diagrama. Tenga en cuenta lo siguiente:

- Las llamadas se distribuyen en orden aleatorio entre instancias de Cloud Connector en un grupo.

- Para fines de planificación de capacidad, tenga en cuenta la capacidad para administrar la carga si una o más instancias de Cloud Connector están sin conexión, según los cálculos siguientes:

  - **N+1 cuadros.** Para la versión más grande del conector en la nube, los cuadros N\*+ 1 son compatibles con 500 N llamadas simultáneas con un 99,8% de disponibilidad.

    Para la versión más pequeña del conector en la nube, los cuadros N\*+ 1 admiten 50 llamadas simultáneas con un 99,8% de disponibilidad.

  - **N+2 cuadros.** Para la versión más grande del conector en la nube, las casillas N + 2 admiten 500\*N llamadas simultáneas con una disponibilidad del 99,9%.

    Para la versión más reducida del conector en la nube, las casillas N + 2 admiten 50\*N llamadas simultáneas con una disponibilidad del 99,9%.

![Dos instancias de Cloud Connector en 1 sitio de RTC](../../media/fc0dc47f-5595-42cb-9432-9c8ff3e134e9.png)

### <a name="multiple-pstn-sites-with-one-or-more-cloud-connectors-per-site"></a>Varios sitios de RTC con una o más instancias de Cloud Connector por sitio

También puede elegir tener varios sitios RTC con una o más instancias de Cloud Connector Edition en cada sitio. Si el sitio RTC alcanza el límite de llamadas simultáneas, puede agregar otro sitio RTC para administrar la carga.

Varios sitios de RTC le permiten proporcionar conectividad a puertas de enlace que están más cerca de sus usuarios. Por ejemplo, imaginemos que tiene puertas de enlace RTC en Seattle y Ámsterdam. Puede implementar dos sitios RTC, uno en Seattle y otro en Ámsterdam, y asignar usuarios para que usen el sitio de RTC que esté más cerca de ellos. De este modo, los usuarios de Seattle se enrutarán al sitio y a las puertas de enlace de la RTC de Seattle y los de Ámsterdam al sitio y a las puertas de enlace de la RTC de Ámsterdam:

![Cloud Connector Edition en 2 sitios de RTC](../../media/16ead6d3-67da-4e71-b4d5-d895b4c9384e.png)

## <a name="requirements-for-deployment"></a>Requisitos para la implementación
<a name="BKMK_Requirements"> </a>

Antes de implementar Cloud Connector Edition, asegúrese de tener lo siguiente para su entorno:

- **Para el equipo host:** Las máquinas virtuales de conector de nube se deben implementar en hardware dedicado que ejecute Windows Server 2012 R2 Datacenter Edition (en inglés) con el rol de Hyper-V habilitado.

    Para la versión 2.0 y posteriores, la tarjeta de red del equipo host que está enlazada al conmutador de la red corporativa de Skype Empresarial debe tener una dirección IP configurada en la misma subred que las máquinas de red corporativas de Cloud Connector. 

- Para las versiones 2,1 y posteriores, el dispositivo de hospedaje debe tener instalado .NET Framework 4.6.1 o una versión posterior.

- **Para las máquinas virtuales:** Una imagen de Windows Server 2012 R2 ISO (. ISO). La ISO se convertirá en VHD para las máquinas virtuales que ejecutarán Skype empresarial Cloud Connector Edition.

- El hardware necesario para admitir la instalación de las cuatro máquinas virtuales para cada edición de conector de nube en su implementación. Se recomienda la siguiente configuración:

  - procesador dual de 64 bits, seis núcleos (12 verdaderos núcleos), 2,50 gigahercios (GHz) o superiores

  - 64 gigabytes (GB) de RAM con ECC 

  - Cuatro discos de 600 GB (o más) de 10 000 RPM SAS con caché de 128 MB y 6 Gbps, con una configuración RAID 5

  - Tres adaptadores de red de alto rendimiento RJ45 de 1 Gbps

- Si elige implementar la versión más pequeña de Cloud Connector Edition que admite hasta 50 llamadas simultáneas, necesitará el siguiente hardware:

  - Intel i7 4790 de cuatro núcleos con gráficos Intel 4600 (no se necesitan gráficos de alto nivel)

  - 32 GB de memoria DDR3-1600 sin ECC

  - 2 unidades de disco duro de 1 TB a 7200 RPM SATA III (6 Gbps) en RAID 0

  - 2 conectores Ethernet de 1 Gpbs (RJ45)

- Si la máquina host requiere un servidor proxy para navegar por Internet, tendrá que hacer los siguientes cambios en la configuración:

  - Para omitir el proxy, especifique la configuración del proxy WinHTTP con su servidor proxy y una lista de omisión, incluyendo la "192.168.213. \*"red usada por los servicios de administración del conector en la nube y la subred de red corporativa de Skype empresarial según se define en el archivo CloudConnector. ini. De lo contrario, se generará un error en la conectividad de administración y no será posible implementar y recuperar automáticamente Cloud Connector. A continuación se muestra un comando de configuración WinHTTP de Netsh: set proxy de Netsh WinHTTP "10.10.10.175:8080" bypass\*-List = ". local; 1. \*; 172,20. \*; 192.168.218. \*"\<local\>".

  - Especifique la configuración del proxy por máquina en lugar de hacerlo por usuario. De lo contrario, se producirá un error de descarga de conector de nube Puede especificar la configuración del proxy por máquina cambiando el registro o configurando la directiva de grupo como sigue:

  - **Registro:** HKEY_LOCAL_MACHINE configuración de \SOFTWARE\Policies\Microsoft\Windows\CurrentVersion\Internet] ProxySettingsPerUser DWORD: 00000000

  - **Directiva de Grupo:** Plantillas\>\>administrativas de equipos de\> Windows Internet Explorer: establecer la configuración de proxy por máquina (en lugar de por usuario)

- PBX/tronco cualificado o SBC/puerta de enlace cualificada (se recomienda un mínimo de dos puertas de enlace).

    Cloud Connector admite los mismos controladores de borde de sesión (SBC) que los certificados para Skype Empresarial. Para obtener más información, vea [infraestructura de telefonía para Skype empresarial](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways).

- Una cuenta de administrador de servidor local con permisos para instalar y configurar Hyper-V en los servidores host. La cuenta debe tener permisos de administrador en el servidor local donde está instalado y configurado Hyper-V.

- Durante la implementación, se le solicitará que cree una cuenta de administrador de dominios con permisos para crear y publicar la topología en el dominio de Cloud Connector. 

- Los registros DNS externos, que se definen en el archivo CloudConnector.ini incluido en el paquete de instalación:

  - Registro DNS externo para el servicio Edge de Access del componente Edge; por ejemplo, nombre\<\>de dominio AP. Necesita un registro por sitio RTC. Este registro debe contener las direcciones IP de todos los perímetros del sitio.

- Un inquilino de Office 365 con todos los registros DNS y SRV necesarios creados.

    > [!IMPORTANT]
    > Al integrar su inquilino con Cloud Connector Edition, no se admite el uso del sufijo de dominio predeterminado,. onmicrosoft.com, como dominio SIP para su organización. > no puede usar SIP. \<Nombre\> de dominio como el nombre de la interfaz del proxy de acceso perimetral del conector de nube porque este registro DNS se usa en Office 365.

- Un certificado del servidor perimetral externo obtenido de una entidad de certificación (CA) pública.

- Se han completado las reglas de firewall para permitir el tráfico a través de los puertos necesarios.

- Una conexión a Internet para las máquinas virtuales y la máquina host. El conector para la nube descarga software de Internet; por lo tanto, debe proporcionar información de la puerta de enlace y el servidor DNS para que el equipo host del conector de nube y las máquinas virtuales puedan conectarse a Internet y descargar el software necesario.

- Un módulo de PowerShell remoto del inquilino instalado en la máquina host.

- Las credenciales de administrador de Office 365 para Skype Empresarial para ejecutar PowerShell remoto.

    > [!IMPORTANT]
    > La cuenta de administrador NO DEBE tener habilitada la autenticación multifactor.

> [!NOTE]
> La implementación de conector de nube solo se admite en la plataforma virtualizada de Microsoft Hyper-V. Otras plataformas, como VMware y Amazon Web Services no son compatibles.

> [!NOTE]
> La guía de hardware mínima para ejecutar el conector de nube se basa en la capacidad básica de hardware (núcleos, MHz, gigabytes, etc.) con un búfer para acomodar las dificultades intangibles de rendimiento escondidos en la arquitectura de cualquier equipo. Microsoft ha llevado a cabo pruebas de situaciones adversas en hardware comercialmente disponible que cumplía los requisitos mínimos. Se comprobaron la calidad media y el rendimiento de los sistemas. Los socios oficiales del dispositivo de conector de nube de Microsoft tienen implementaciones específicas de hardware del conector de nube en las que han probado el rendimiento de forma independiente y tienen la correspondiente idoneidad de su hardware para cumplir con los requisitos de carga y calidad.

> [!NOTE]
> Los dispositivos producidos por AudioCodes y Sonus tienen código modificado y se ejecutan en servidores Windows Server Standard Edition. Estos dispositivos son compatibles.

## <a name="information-you-need-to-gather-before-deployment"></a>Información que necesita reunir antes de la implementación
<a name="BKMK_PlanDeployment"> </a>

Antes de iniciar la implementación, necesita determinar el tamaño de la implementación y los dominios SIP que se proporcionarán, así como información sobre la configuración de cada sitio de RTC que tiene previsto implementar. Para empezar, necesitará:

- Identifique todos los dominios SIP que esta implementación atenderá en función de los URI de SIP que se usan en su empresa.

- Determinar el número de sitios de RTC que necesita implementar.

- Asegúrese de que tiene el hardware necesario para admitir las cuatro máquinas virtuales que va a instalar para cada edición de Cloud Connector.

Para cada sitio de la RTC que planee implementar, debe hacer lo siguiente:

- Cree nombres para todos los componentes de cada dispositivo del conector de nube (consulte [determinar parámetros de implementación](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams)).

- Definir intervalos de puertos (vea [Puertos y protocolos](plan-skype-for-business-cloud-connector-edition.md#BKMB_Ports)).  

- Crear registros de DNS para el componente perimetral (vea [Requisitos para la implementación](plan-skype-for-business-cloud-connector-edition.md#BKMK_Requirements)).

- Determinar sus requisitos de certificados para el componente perimetral (vea [Requisitos de certificados](plan-skype-for-business-cloud-connector-edition.md#BKMK_Certs)).

### <a name="ports-and-protocols"></a>Puertos y protocolos
<a name="BKMB_Ports"> </a>

Al definir intervalos de puertos para multimedia, tenga en cuenta lo siguiente:

- Los clientes siempre usan el intervalo de puertos 50000 a 50019 para el tráfico de medios: este intervalo está predefinido en Skype empresarial online y no se puede cambiar.

- De forma predeterminada, el componente de mediación usará el intervalo de puertos del 49 152 al 57 500 para el tráfico de contenido multimedia. Sin embargo, la conexión se establece a través del firewall interno y, por razones de seguridad, puede limitar este intervalo de puertos en su topología. Necesitará hasta 4 puertos por llamada. Si desea limitar el número de puertos entre el componente de mediación y la puerta de enlace de RTC, también necesitará configurar el intervalo de puestos correspondiente de la puerta de enlace.

- Debe implementar Cloud Connector en una red perimetral. Esto significa que tendrá dos firewall:

  - El primer firewall es externo entre Internet y la red perimetral.

  - El segundo Firewall es interno entre la red perimetral y la red interna.

    Sus clientes pueden estar en Internet o en la red interna: 

  - Los clientes en Internet se conectarán a su RTC mediante el firewall externo a través del componente perimetral.

  - Los clientes de la red interna se conectarán a través del firewall interno al componente de mediación de la red perimetral, que conectará el tráfico a la puerta de enlace de SBC o RTC.

    Esto quiere decir que necesita abrir los puertos en los dos firewalls. 

En las tablas siguientes se describen los puertos y los intervalos de puertos para los firewalls externo e interno.

En esta tabla se muestran los puertos y los intervalos de puertos para habilitar la comunicación entre los clientes de la red interna y el componente de mediación:

**Firewall interno**



|**IP de origen**|**IP de destino**|**Puerto de origen**|**Puerto de destino**|
|:-----|:-----|:-----|:-----|
|Componente de mediación de conector de nube  <br/> |Puerta de enlace RTC/SBC  <br/> |Cualquiera  <br/> |TCP 5060\*\*  <br/> |
|Puerta de enlace RTC/SBC  <br/> |Componente de mediación de conector de nube  <br/> |Cualquiera  <br/> |TCP 5068/TLS 5067  <br/> |
|Componente de mediación de conector de nube  <br/> |Puerta de enlace RTC/SBC  <br/> |UDP 49 152-57 500  <br/> |Que\*\*\*  <br/> |
|Puerta de enlace RTC/SBC  <br/> |Componente de mediación de conector de nube  <br/> |Que\*\*\*  <br/> |UDP 49 152-57 500  <br/> |
|Componente de mediación de conector de nube  <br/> |Clientes internos  <br/> |TCP 49 152-57 500\*  <br/> |TCP 50.000-50.019  <br/> (Opcional)  <br/> |
|Componente de mediación de conector de nube  <br/> |Clientes internos  <br/> |UDP 49 152-57 500\*  <br/> |UDP 50.000-50.019  <br/> |
|Clientes internos  <br/> |Componente de mediación de conector de nube  <br/> |TCP 50.000-50.019  <br/> |TCP 49 152-57 500\*  <br/> |
|Clientes internos  <br/> |Componente de mediación de conector de nube  <br/> |UDP 50.000-50.019  <br/> |UDP 49 152-57 500\*  <br/> |

\*Este es el intervalo de puertos predeterminado en el componente de mediación. Para un flujo de llamadas óptimo, se recomienda usar cuatro puertos por llamada.

\*\*Este puerto debe estar configurado en la puerta de enlace de SBC/RTC; 5060 es un ejemplo. Puede configurar otros puertos en su puerta de enlace RTC/SBC.

\*\*\*Tenga en cuenta que también puede limitar el intervalo de puertos en el SBC o la puerta de enlace si el fabricante de SBC/puerta de enlace lo permite.

Por motivos de seguridad, puede limitar el intervalo de puertos para el componente de mediación con el cmdlet [set-CsMediationServer](https://docs.microsoft.com/powershell/module/skype/set-csmediationserver?view=skype-ps) .

Por ejemplo, el siguiente comando limita el número de puertos que el componente de mediación usará para el tráfico multimedia a 50 000-51 000 para el audio (entrante y saliente). El componente de mediación podrá administrar 250 llamadas simultáneas con esta configuración. Tenga en cuenta que también puede limitar este intervalo en la puerta de enlace RTC/SBC:

```powershell
Set-CSMediationServer -Identity MediationServer:mspool.contoso.com -AudioPortStart 50000 - AudioPortCount 1000
```

Para recuperar el nombre del componente de mediación y ver los puertos predeterminados, puede usar el cmdlet [Get-CsService](https://docs.microsoft.com/powershell/module/skype/get-csservice?view=skype-ps) de la siguiente manera:

```powershell
Get-CsService -MediationServer | Select-Object Identity, AudioPortStart, AudioPortCount
```

En la tabla siguiente se muestran puertos y intervalos de puertos para habilitar la comunicación entre el componente perimetral del conector de nube y el firewall externo. Esta tabla muestra una recomendación mínima.

En este caso, todo el tráfico multimedia a Internet fluirá a través del perímetro en línea de la siguiente manera: punto de\>fin del usuario-\>-conexión perimetral--perimetral del conector de nube:

**Firewall externo: configuración mínima**



|**IP de origen**|**IP de destino**|**Puerto de origen**|**Puerto de destino**|
|:-----|:-----|:-----|:-----|
|Cualquiera  <br/> |Interfaz externa perimetral del conector para la nube  <br/> |Cualquiera  <br/> |TCP(MTLS) 5061  <br/> |
|Interfaz externa perimetral del conector para la nube  <br/> |Cualquiera   <br/> |Cualquiera  <br/> |TCP(MTLS) 5061  <br/> |
|Interfaz externa perimetral del conector para la nube  <br/> |Cualquiera   <br/> |Cualquiera  <br/> |TCP 80  <br/> |
|Interfaz externa perimetral del conector para la nube  <br/> |Cualquiera   <br/> |Cualquiera  <br/> |UDP 53  <br/> |
|Interfaz externa perimetral del conector para la nube  <br/> |Cualquiera   <br/> |Cualquiera  <br/> |TCP 53  <br/> |
|Interfaz externa perimetral del conector para la nube  <br/> |Cualquiera  <br/> |UDP 3478  <br/> |UDP 3478  <br/> |
|Cualquiera  <br/> |Interfaz externa perimetral del conector para la nube  <br/> |TCP 50.000-59.999  <br/> |TCP 443  <br/> |
|Cualquiera  <br/> |Interfaz externa perimetral del conector para la nube  <br/> |UDP 3478  <br/> |UDP 3478  <br/> |
|Interfaz externa perimetral del conector para la nube  <br/> |Cualquiera  <br/> |TCP 50.000-59.999  <br/> |TCP 443  <br/> |

En la siguiente tabla se muestran puertos y intervalos de puertos para habilitar la comunicación entre el componente perimetral del conector de nube y el firewall externo. Esta tabla muestra la solución recomendada.

En este caso, todo el tráfico multimedia para el extremo de Internet puede fluir directamente al componente perimetral del conector de la nube. La ruta multimedia será el punto final del usuario\> : conector de la nube.

> [!NOTE]
> Esta solución no funcionará si el extremo del usuario está detrás de un NAT simétrico.

**Firewall externo: configuración recomendada**


|**IP de origen**|**IP de destino**|**Puerto de origen**|**Puerto de destino**|
|:-----|:-----|:-----|:-----|
|Cualquiera  <br/> |Interfaz externa perimetral del conector para la nube  <br/> |Cualquiera  <br/> |TCP(MTLS) 5061  <br/> |
|Interfaz externa perimetral del conector para la nube  <br/> |Cualquiera   <br/> |Cualquiera  <br/> |TCP(MTLS) 5061  <br/> |
|Interfaz externa perimetral del conector para la nube  <br/> |Cualquiera   <br/> |Cualquiera  <br/> |TCP 80  <br/> |
|Interfaz externa perimetral del conector para la nube  <br/> |Cualquiera   <br/> |Cualquiera  <br/> |UDP 53  <br/> |
|Interfaz externa perimetral del conector para la nube  <br/> |Cualquiera   <br/> |Cualquiera  <br/> |TCP 53  <br/> |
|Interfaz externa perimetral del conector para la nube  <br/> |Cualquiera  <br/> |TCP 50.000-59.999  <br/> |Cualquiera  <br/> |
|Interfaz externa perimetral del conector para la nube  <br/> |Cualquiera  <br/> |UDP 3478; UDP 50000-59999  <br/> |Cualquiera   <br/> |
|Cualquiera  <br/> |Interfaz externa perimetral del conector para la nube  <br/> |Cualquiera  <br/> |TCP 443; TCP 50000-59999  <br/> |
|Cualquiera  <br/> |Interfaz externa perimetral del conector para la nube  <br/> |Cualquiera  <br/> |UDP 3478; UDP 50000-59999  <br/> |

### <a name="host-internet-connectivity-requirements"></a>Requisitos de conectividad a Internet del host
<a name="BKMB_Ports"> </a>

El equipo host debe poder comunicarse con los recursos externos para instalar, actualizar y administrar Cloud Connector correctamente. En la siguiente tabla se muestran los destinos y los puertos que se necesitan entre el equipo host y el recurso externo.

|Dirección  <br/> |IP de origen  <br/> |IP de destino  <br/> |Puerto de origen  <br/> |Puerto de destino  <br/> |Protocolo  <br/> |Finalidad  <br/> |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Saliente  <br/> |IPs de host del conector de nube  <br/> |Cualquiera  <br/> |Cualquiera  <br/> |53  <br/> |TCP/UDP  <br/> |DNS  <br/> |
|Saliente  <br/> |IPs de host del conector de nube  <br/> |Cualquiera  <br/> |Cualquiera  <br/> |80, 443  <br/> |TCP  <br/> |Lista de revocación de certificados (CRL)  <br/> |
|Saliente  <br/> |IPs de host del conector de nube  <br/> |Cualquiera  <br/> |Cualquiera  <br/> |80, 443  <br/> |TCP  <br/> |Actualización del conector para la nube  <br/> Skype Empresarial Online  <br/> PowerShell de administración  <br/> Windows Update  <br/> |

Si se requieren reglas más restrictivas, consulte las siguientes direcciones URL incluidas en la lista blanca:

- [Direcciones URL de la lista de revocación de certificados](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2) en [Office 365 URL e intervalos de direcciones IP](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US)

- Windows Update: [Cómo configurar un firewall para actualizaciones de software](https://technet.microsoft.com/en-us/library/bb693717.aspx)

- PowerShell de administración de Skype empresarial online \*:. online.Lync.com

    Si necesita excluir un proxy para este destino, tendrá que agregarlo a la lista de omisiones de WinHTTP.

- Actualización del conector para la nube: [https://go.microsoft.com](https://go.microsoft.com)centro de [descarga](https://aka.ms/CloudConnectorInstaller), y[https://download.microsoft.com](https://download.microsoft.com)

### <a name="dns-name-resolution-for-the-edge-component"></a>Resolución de nombres DNS para el componente perimetral
<a name="BKMB_Ports"> </a>

El componente Edge necesita resolver los nombres externos de los servicios 365 de Office y los nombres internos de otros componentes de conector de nube.

Cada componente perimetral es un equipo de hosts múltiples con interfaces internas y externas. El conector de nube implementa servidores DNS en el componente controlador de dominio dentro de la red perimetral. Puede señalar el servidor perimetral en el servidor DNS dentro del perímetro para todas las resoluciones de nombres, pero necesita habilitar el servidor DNS del conector en la nube para resolver nombres externos al configurar una zona DNS que contenga uno o más registros A de DNS para consultas externas que hagan referencia al nombre búsquedas en otros servidores DNS públicos.

En el archivo .ini, si configuró el nombre FQDN para puertas de enlace desde el mismo espacio de dominios que su dominio de SIP, la zona autoritativa para el dominio de SIP se creará en el servidor DNS dentro del perímetro. Si el servidor perimetral apunta a este servidor DNS para resolver nombres, Edge nunca resolverá el _sipfederationtls. \<sudominio\> DNS registro, que es necesario para el flujo de llamadas. En este caso, Microsoft recomienda proporcionar un servidor DNS en la interfaz externa perimetral para resolver las búsquedas de nombres de Internet, y cada componente perimetral debe usar un archivo HOST para resolver otros nombres de componentes de conector de nube en direcciones IP.

> [!NOTE]
> Por razones de seguridad, le recomendamos que no dirija el servidor DNS del conector de nube a los servidores internos en el dominio de producción para la resolución de nombres.

### <a name="determine-deployment-parameters"></a>Determinar los parámetros de implementación
<a name="BKMK_SiteParams"> </a>

En primer lugar, es necesario definir los siguientes parámetros comunes de implementación:


|**Elemento**|**Descripción**|**Notas**|
|:-----|:-----|:-----|
|Dominios SIP  <br/> |URI de SIP que usan los usuarios de la empresa. Proporciona todos los dominios SIP proporcionados por esta implementación. Es posible tener más de un dominio SIP.  <br/> ||
|Número de sitios de RTC  <br/> |El número de sitios de RTC que implementará.  <br/> ||

Para cada sitio de RTC que vaya a implementar, necesitará reunir la siguiente información antes de comenzar. Tendrá que proporcionar esta información cuando actualice el archivo CloudConnector.ini.

Al configurar la información de puerta de enlace, recuerde lo siguiente:

- Si solo tiene una puerta de enlace, elimine la sección en el archivo .ini para la segunda puerta de enlace. Si hay más de dos puertas de enlace, siga el formato existente para agregar nuevas.

- Asegúrese de que la dirección IP y los puertos de las puertas de enlace son correctos.

- Para admitir HA en nivel de puerta de enlace de RTC, mantenga la puerta de enlace secundaria o agregue puertas de enlace adicionales.

(Opcional) Para restringir los números de llamadas salientes, actualice el valor LocalRoute.



|**Parámetros del sitio**|**Descripción**|**Notas**|
|:-----|:-----|:-----|
|Nombre de dominio de máquina virtual  <br/> |Nombre de dominio para los componentes internos del conector en la nube. Este dominio tiene que ser distinto del dominio de producción. El nombre tiene que ser el mismo en todos los dispositivos de Cloud Connector.  <br/> Nombre en el archivo. ini: "VirtualMachineDomain"  <br/> |Se prefiere el dominio .local.   <br/> |
|Nombre del controlador de dominio del conector de nube  <br/> |Nombre del controlador de dominio.   <br/> Nombre del archivo. ini: "nombreservidor"  <br/> |Debe tener 15 caracteres o menos de longitud. Escriba solo el nombre de Netbios.  <br/> |
|IP/subred del controlador de dominio del conector de nube  <br/> |Dirección IP del controlador de dominio.    <br/> Nombre en el archivo. ini: "IP"  <br/> ||
|FQDN de servicios de O365 Online  <br/> |Debe ser el valor predeterminado en la mayoría de los casos para la instancia de O365 internacional.  <br/> Nombre en el archivo. ini: "OnlineSipFederationFqdn"  <br/> ||
|SiteName  <br/> |Nombre del sitio de Skype empresarial; por ejemplo, Seattle.  <br/> Nombre del archivo. ini: "Nombresitio"  <br/> En la versión 1.4.1 y posteriores, el nombre del sitio debe ser distinto para cada sitio y debe coincidir con el sitio RTC definido en Office 365. Tenga en cuenta que los sitios RTC se crearán automáticamente al registrar el primer dispositivo en un sitio.  <br/> ||
|HardwareType  <br/> Versión 1.4.1 y posteriores  <br/> |Tipo de hardware. El valor predeterminado es Normal. También puede configurarlo en Mínimo.  <br/> ||
|Código de país o región  <br/> |Código de país o región para llamadas.  <br/> Nombre del archivo. ini: "CountryCode"  <br/> ||
|Ciudad  <br/> |Ciudad (opcional).  <br/> Nombre en el archivo. ini: "ciudad"  <br/> ||
|Estado  <br/> |Estado (opcional).  <br/> Nombre en el archivo. ini: "estado"  <br/> ||
|Dirección IP de la VM base  <br/> |La dirección IP de la VM base temporal que se usará para crear el VHDX para todas las máquinas virtuales del conector en la nube. Esta IP debe estar en la misma subred de red corporativa perimetral definida en el siguiente paso y requiere acceso a Internet. Asegúrese de definir la puerta de enlace predeterminada corporativa y el DNS enrutable a Internet.  <br/> Nombre en el archivo. ini: "BaseVMIP"  <br/> ||
|WSUSServer  <br/> WSUSStatusServer  <br/> Versión 1.4.1 y posteriores  <br/> |La dirección de los Windows Server Update Services (WSUS), un servidor de intranet para alojar actualizaciones de Microsoft Update.  <br/> Puede dejarla en blanco si no se necesitan los WSUS.    <br/> ||
|Máscara de subred para red interna  <br/> |Conector de nube configura una red IP para la comunicación interna entre los componentes del conector de la nube. El componente perimetral también debe estar conectado a otra subred que permita la conectividad a Internet.  <br/> Nombre del archivo. ini: "CorpnetIPPrefixLength" en "parámetros para un grupo de redes de VM"  <br/> ||
|Máscara de subred para red externa   <br/> |Para la red externa del componente perimetral.  <br/> Nombre del archivo. ini: "InternetIPPrefix" en "parámetros para un grupo de redes de VM"  <br/> ||
|Nombre de conmutador para red interna  <br/> |Nombre del conmutador que se usará para la red del conector de nube interno.  <br/> En la mayoría de los casos, se puede usar el valor sugerido predeterminado.  <br/> Nombre del archivo. ini: "CorpnetSwitchName" en "parámetros para un grupo de redes de VM  <br/> ||
|Nombre de conmutador para red externa  <br/> |Nombre del conmutador que se usará para la red de conector de nube externa.  <br/> En la mayoría de los casos, se puede usar el valor sugerido predeterminado.  <br/> Nombre del archivo. ini: "InternetSwitchName" en "parámetros para un grupo de redes de VM  <br/> ||
|Puerta de enlace predeterminada para red interna  <br/> |Esta puerta de enlace debe proporcionar acceso a Internet (Internet también requiere configurar el servidor DNS) y se configurará en las interfaces internas de los componentes del conector en la nube.  <br/> Nombre del archivo. ini: "CorpnetDefaultGateway" en "parámetros para un grupo de redes de VM  <br/> ||
|Puerta de enlace predeterminada para la interfaz externa del componente perimetral  <br/> |Se configurará en la interfaz externa del componente perimetral.  <br/> Nombre del archivo. ini: "InternetDefaultGateway" en "parámetros para un grupo de redes de VM  <br/> ||
|Servidor DNS para red interna  <br/> |Se configurará en la interfaz interna de la VM temporal. Debe proporcionar la resolución de nombres para nombres de Internet. Sin proporcionar un servidor DNS, no se podrá conectar a Internet y no se podrá finalizar la implementación.  <br/> Nombre del archivo. ini: "CorpnetDNSIPAddress" en "parámetros para un grupo de redes de VM  <br/> ||
|Servidor DNS para la interfaz externa del componente perimetral  <br/> |Se configurará en la interfaz externa del componente perimetral.  <br/> Nombre del archivo. ini: "InternetDNSIPAddress" en "parámetros para un grupo de redes de VM  <br/> ||
|Nombre del conmutador de administración  <br/> |El conmutador de administración es un modificador temporal que se creará automáticamente y que se usará para la configuración del conector de nube durante la implementación. Se desconectará automáticamente después de la implementación. Debe ser una subred diferente de cualquier otra red usada en Cloud Connector.  <br/> En la mayoría de los casos, se puede usar el valor sugerido predeterminado.  <br/> Nombre del archivo. ini: "ManagementSwitchName" en "parámetros para un grupo de redes de VM  <br/> ||
|Dirección de subred/máscara de subred de administración  <br/> |La subred de administración es una subred temporal que se creará automáticamente y que se usará para la configuración del conector de nube durante la implementación. Se eliminará automáticamente después de la implementación. Debe ser una subred diferente de cualquier otra red usada en Cloud Connector.  <br/> Nombres en el archivo. ini: "ManagementIPPrefix" y "ManagementIPPrefixLength" en "parámetros para un grupo de redes de VM  <br/> ||
|Equipo de almacenamiento de administración central (CMS)  <br/> |FQDN único que se usa para el Almacén de administración central (CMS). El nombre de dominio de AD se usará para generar el FQDN.  <br/> Nombre del archivo. ini: "nombreservidor" en "parámetros para el servicio principal de administración central  <br/> |Debe tener 15 caracteres o menos de longitud. Escriba solo el nombre de Netbios.  <br/> (Nombre del grupo de servidores de CMS = nombre del servidor)  <br/> |
|Dirección IP del equipo de CMS  <br/> |Dirección IP del servidor CMS (interna en la red perimetral).  <br/> Nombre del archivo INI: "IP" en "parámetros para el servicio de administración central principal  <br/> ||
|Nombre de recurso compartido de archivos    <br/> |Nombre del recurso compartido de archivos que se creará en el servidor CMS para los datos de replicación de Skype empresarial (por ejemplo, CmsFileStore).  <br/> En la mayoría de los casos, se puede usar el valor sugerido predeterminado.  <br/> Nombre en el archivo. ini: "CmsFileStore" en "parámetros para el servicio principal de administración central  <br/> ||
|Nombre del grupo de componentes de mediación  <br/> |Nombre de grupo del componente de mediación. Escriba solo el nombre de Netbios. El nombre de dominio de AD se usará para generar el FQDN.  <br/> Nombre del archivo. ini: "Nombredegrupo" en "parámetros para un grupo de servidores de mediación"  <br/> |Debe tener 15 caracteres o menos de longitud. Escriba solo el nombre de Netbios.  <br/> |
|Nombre del componente de mediación  <br/> |Nombre de componente del componente de mediación 1. Escriba solo el nombre de Netbios. El nombre de dominio de AD se usará para generar el FQDN.  <br/> Nombre del archivo. ini: "nombreservidor" en "parámetros para un grupo de servidores de mediación"  <br/> |Debe tener 15 caracteres o menos de longitud. Escriba solo el nombre de Netbios.  <br/> |
|Dirección IP de equipo de componente de mediación  <br/> |IP de CorpNet interna para componente mediación (interna en la red perimetral).  <br/> Nombre del archivo. ini: "IP" en "parámetros para un grupo de servidores de mediación"  <br/> ||
|Nombre interno del grupo de servidores perimetrales  <br/> |Nombre de grupo del componente perimetral. Escriba solo el nombre de Netbios. El nombre de dominio de AD se usará para generar el FQDN.  <br/> Nombre del archivo. ini: "InternalPoolName" en "parámetros para un grupo de servidores perimetrales"  <br/> |Debe tener 15 caracteres o menos de longitud. Escriba solo el nombre de Netbios.  <br/> |
|Nombre interno del servidor perimetral  <br/> |Nombre de componente del componente perimetral. Escriba únicamente el nombre NETBIOS. El nombre de dominio de AD se usará para generar el FQDN.   <br/> Nombre del archivo. ini: "InternalServerName" en "parámetros para un grupo de servidores perimetrales"  <br/> |Debe tener 15 caracteres o menos de longitud. Escriba solo el nombre de Netbios.  <br/> |
|IP interna del servidor perimetral   <br/> |IP de la red perimetral interna del componente Edge para comunicarse con otros componentes del conector en la nube.  <br/> Nombre del archivo. ini: "InternalServerIPs" en "parámetros para un grupo de servidores perimetrales"  <br/> ||
|Nombre externo de grupo de servidores de acceso  <br/> |El nombre del componente perimetral de acceso (por ejemplo, AP). Este nombre tiene que coincidir con el nombre proporcionado para el certificado SSL. Escriba únicamente el nombre NETBIOS. El nombre de dominio SIP se usará para generar el FQDN. Se usará un nombre de grupo externo para todos los componentes de borde del grupo. Se necesita un grupo de acceso perimetral por sitio RTC.  <br/> Nombre del archivo. ini: "ExternalSIPPoolName" en "parámetros para un grupo de servidores perimetrales"  <br/> |Debe tener 15 caracteres o menos de longitud. Escriba solo el nombre de Netbios.  <br/> "SIP" está reservado y, por lo tanto, no se puede usar como nombre.  <br/> El nombre de FQDN generado debe coincidir con el nombre que proporciona el certificado SSL.    <br/> |
|IP externa del perímetro de acceso  <br/> |IP externa del componente de la periferia: dirección IP pública si no hay ninguna NAT disponible o IP traducida (especifique ambas direcciones si se asignan).  <br/> Nombre del archivo. ini: "ExternalSIPIPs" en "parámetros para un grupo de servidores perimetrales"  <br/> ||
|Nombre de relé multimedia  <br/> |El nombre del servidor perimetral de relé multimedia de audio/vídeo (por ejemplo, MR). Se usará un nombre de grupo externo para todos los componentes perimetrales de un grupo. Se necesita un grupo de retransmisión de medios perimetrales por sitio RTC.  <br/> Nombre del archivo. ini: "ExternalMRFQDNPoolName" en "parámetros para un grupo de servidores perimetrales"  <br/> |Debe tener 15 caracteres o menos de longitud. Escriba solo el nombre de Netbios.  <br/> |
|IP externa del perímetro de retransmisión multimedia  <br/> |Actualmente solo se admite una IP, por lo que será la misma IP que la del componente perimetral de acceso, tanto si es una IP asignada como si es pública (especifique ambas direcciones si es asignada). Puede ser la misma dirección que la IP externa del componente perimetral del componente perimetral de acceso. Tenga en cuenta que, si el componente perimetral está tras una NAT, también tendrá que especificar el valor del siguiente parámetro.  <br/> Nombre del archivo. ini: "ExternalMRIPs" en "parámetros para un grupo de servidores perimetrales"  <br/> ||
|IP externa del perímetro de retransmisión multimedia (si el borde está detrás de NAT)  <br/> |Si su componente perimetral está tras una NAT, también necesitará especificar la dirección pública del dispositivo NAT.  <br/> Nombre del archivo. ini: "ExternalMRPublicIPs" en "parámetros para un grupo de servidores perimetrales"  <br/> ||
|Marca y modelo de puerta de enlace de voz  <br/> |Especifique la marca y el modelo de la puerta de enlace de SBC/voz. Ten en cuenta que puedes conectar un dispositivo o un tronco de SIP desde la lista de [https://technet.Microsoft.com/UCOIP](https://technet.Microsoft.com/UCOIP)dispositivos probados en.  <br/> ||
|Marca y modelo de puerta de enlace de voz (copia esta fila si tienes más de 2 puertas de enlace)  <br/> |Especifique la marca y el modelo de la puerta de enlace de voz. Tenga en cuenta que puede conectar un dispositivo de la lista de dispositivos probados en [https://technet.Microsoft.com/UCOIP](https://technet.Microsoft.com/UCOIP).  <br/> ||
|Nombre de puerta de enlace de voz 1  <br/> |Se usa para generar el FQDN de la máquina con dominio de AD. Es necesario si se va a usar TLS entre el componente de mediación y la puerta de enlace de voz. Si no tiene previsto usar FQDN, por ejemplo, no se requiere TLS o la puerta de enlace de voz no admite la conexión usando FQDN (solo IP); especifique.  <br/> ||
|Nombre de la puerta de enlace de voz 2 (Copie esta fila si tiene más de 2 puertas de enlace)  <br/> |Se usa para generar el FQDN de la máquina con dominio de AD. Es necesario si se va a usar TLS entre el componente de mediación y la puerta de enlace de voz. Si no tiene previsto usar FQDN, por ejemplo, no se requiere TLS o la puerta de enlace de voz no admite la conexión usando FQDN (solo IP); especifique.  <br/> ||
|Dirección IP de puerta de enlace de voz 1  <br/> |Dirección IP de puerta de enlace de voz.  <br/> ||
|Dirección IP de puerta de enlace de voz 2 (copiar esta fila si tiene más de 2 puertas de enlace)  <br/> |Dirección IP de puerta de enlace de voz.  <br/> ||
|Puerta de enlace de voz 1 puerto # (copiar esta fila si tiene más de 2 puertas de enlace)  <br/> |Puerto donde escuchará el tronco SIP de puerta de enlace de voz (por ejemplo, 5060).  <br/> ||
|Puerto de puerta de enlace de voz 2 #  <br/> |Puerto donde escuchará el tronco SIP de puerta de enlace de voz (por ejemplo, 5060).  <br/> ||
|Protocolo de puerta de enlace de voz 1 para tráfico SIP  <br/> |TCP o TLS.  <br/> ||
|Protocolo de puerta de enlace de voz 2 para tráfico SIP (copiar esta fila si tiene más de 2 puertas de enlace)  <br/> |TCP o TLS.  <br/> ||
|Intervalo de puertos multimedia externos para tráfico desde y hacia el componente perimetral  <br/> |El intervalo de puertos TCP/UDP para el tráfico multimedia desde y hacia la interfaz externa del perímetro. Siempre tiene que empezar con 50000. Para obtener más información, consulte "puertos y protocolos".  <br/> |50000 - 59 999  <br/> |
|Intervalo de puertos de medios para comunicarse desde el componente de mediación a través del firewall interno  <br/> |Intervalo de puertos UDP que el componente de mediación usará para comunicarse con los clientes y las puertas de enlace (Recomendación 4 puertos por llamada).  <br/> ||
|Intervalo de puertos de medios para comunicarse desde el cliente de Skype empresarial a través del firewall interno  <br/> |Por motivos de planificación, esto no se puede cambiar. Es necesario abrir los puertos en el firewall interno para comunicarse entre los clientes de Skype empresarial dentro de la red interna y con el componente de mediación.  <br/> |50.000- 50.019  <br/> |
|Contraseña de certificado público  <br/> |Es necesario proporcionarla en el script.  <br/> ||
|Contraseña de administrador de modo seguro  <br/> Solo la versión 1.4.2  <br/> |La contraseña de administrador de modo seguro para el dominio de CC interno.  <br/> ||
|Contraseña de administrador de dominio de conector de nube  <br/> Solo la versión 1.4.2  <br/> |Contraseña del administrador de dominio del conector de nube (diferente de su dominio de producción). El nombre de usuario es Administrator. No puede cambiar el nombre de usuario.  <br/> ||
|Contraseña de administrador de máquinas virtuales  <br/> Solo la versión 1.4.2  <br/> |Se usa para configurar la red de administración durante la implementación.  <br/> El nombre de usuario es Administrator. No puede cambiar el nombre de usuario.   <br/> ||
|CABackupFile  <br/> Versión 2.0 y posteriores  <br/> |Se usa para guardar el servicio de entidad de certificación del servidor de Active Directory en un archivo al implementar varios dispositivos en un sitio de conector de nube. Asegúrese de usar la misma contraseña en todos los dispositivos de un sitio de Cloud Connector para poder importar correctamente el archivo de copia de seguridad de la entidad de certificación en los nuevos dispositivos que se agreguen.  <br/> ||
|CCEService  <br/> Versión 2.0 y posteriores  <br/> |Se usa para el servicio de administración de Cloud Connector; necesita acceder al directorio del sitio de Cloud Connector. Asegúrese de usar la misma contraseña en todos los dispositivos de un sitio de Cloud Connector.   <br/> ||
|Administrador de inquilinos de Office 365  <br/> |  Cloud Connector usa la cuenta para actualizar y administrar la configuración de los inquilinos para Cloud Connector: <br/>  Versión 2,0 y posteriores: credenciales de una cuenta de Office 365 dedicada con derechos de administrador de Skype empresarial. <br/>  Versiones anteriores a la versión 2.0: las credenciales de una cuenta de Office 365 dedicada con derechos globales de administrador de inquilinos. <br/> ||
|Habilitar la compatibilidad con referencias  <br/> |Esto definirá si la compatibilidad con SIP REFER está habilitada o deshabilitada en la configuración de tronco de su IP/PBX. El valor predeterminado es True. Si su puerta de enlace IP/PBX es compatible con REFER, déjelo como True. Si no es así, tiene que cambiar este valor a False. Si no está seguro de si su puerta de enlace admite referencia, consulte [IP-PBX y puertas de enlace](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways).   <br/> ||
|EnableFastFailoverTimer  <br/> Versión 2.0 y posteriores  <br/> |Con el valor predeterminado "true", si la puerta de enlace no responde a las llamadas salientes en un plazo de 10 segundos, se dirigirá a la siguiente puerta de enlace disponible; Si no hay otros troncos, la llamada se eliminará automáticamente.  <br/> Sin embargo, en una organización donde las respuestas de las puertas de enlace y las redes son lentas, o cuando el proceso de establecimiento de las llamadas tarda más de 10 segundos, las llamadas se interrumpirían innecesariamente.  <br/> Cuando se realizan llamadas a determinados países o regiones, como los Emiratos Árabes Unidos o Afganistán, el establecimiento de llamada puede tardar más de 10 segundos. En estos casos o en otros problemas parecidos, tendrá que cambiar el valor a False. No olvide cambiar la configuración correspondiente en el SBC o la puerta de enlace conectados.  <br/> El valor puede ser True o False. El valor predeterminado es True.  <br/> ||
|ForwardCallHistory  <br/> Versión 2.0 y posteriores  <br/> | Con este parámetro se activan los encabezados SIP que se utilizan para comunicar el autor inicial de la llamada en los escenarios de llamadas simultáneas, desvío de llamadas y transferencia de llamadas. Si el parámetro se establece en True, se activarán dos encabezados SIP:<br/>  History-Info <br/>  Referred-By <br/>  El encabezado información del historial se usa para redestinar solicitudes SIP y "proporciona (s) un mecanismo estándar para capturar la información del historial de solicitudes para habilitar una amplia variedad de servicios para redes y usuarios finales" ([RFC 4244-sección 1,1](http://www.ietf.org/rfc/rfc4244.txt)). En el caso de interfaces de troncos de Cloud Connector, se usa en situaciones de llamadas simultáneas y desvío de llamadas.  <br/>  El valor puede ser True o False. El valor predeterminado es False.<br/> ||
|Reenvío de PAI  <br/> Versión 2.0 y posteriores  <br/> |PAI es una extensión privada de SIP que permite que los servidores SIP confirmen la identidad de los usuarios autenticados. El proveedor de tronco SIP puede usar PAI con fines de facturación en el caso de que los encabezados History-Info y Referred-By no estén presentes. Cuando la identidad declarada de Forward se habilita en la configuración, el servidor de mediación reenviará los encabezados &amp; de PAI con URI de Tel URI del conector de nube en el tronco del SIP. El servidor de mediación reenviará los encabezados de PAI &amp; con los URI de Tel E. 164 números que solo se recibieron en el protocolo troncal de SIP para Cloud. El servidor de mediación también desviará los encabezados de privacidad que se reciban en cualquier dirección. Si la solicitud SIP enviada por el servidor de mediación incluye un encabezado de privacidad en el formulario "privacidad: ID" junto con el encabezado PAI, la identidad confirmada se debe mantener fuera del dominio de confianza de la red.  <br/> El valor puede ser True o False. El valor predeterminado es False.  <br/> ||

### <a name="certificate-requirements"></a>Requisitos de certificados
<a name="BKMK_Certs"> </a>

Cada componente perimetral necesita un certificado de una entidad de certificación pública. Los certificados necesitan una clave privada que se pueda exportar para poder copiar entre componentes perimetrales. Para cumplir con los requisitos de certificados, necesita decidir entre las opciones siguientes para proporcionar el nombre de firmante (SN) y el nombre alternativo del firmante (SAN) para el certificado.

 **Si tiene un único dominio SIP:**

- **Opción 1.** El nombre del asunto tiene que contener el nombre de grupo que asignó a los componentes perimetrales. Tenga en cuenta que el nombre del asunto no puede ser sip.sipdomain.com porque este nombre está reservado para el componente perimetral de Skype empresarial en línea. El SAN tiene que contener sip.sipdomain.com y el nombre de grupo perimetral de acceso:

  ```
  SN = accessedgepoolnameforsite1.sipdomain.com, SAN = sip.sipdomain.com,
  acessedgepoolnameforsite1.sipdomain.com
  ```

- **Opción 2.** Si desea usar un único certificado comodín en todos los servidores de grupo perimetral que implementa, puede usar una entrada SAN comodín de \*. sipdomain.com en lugar del nombre del grupo de bordes en el certificado. El nombre del firmante puede ser el nombre de grupo perimetral de acceso de cualquiera de los grupos de servidores perimetrales que ya haya implementado:

  ```
  SN = accessedgepoolnameforsite1.sipdomain.com, SAN = sip.sipdomain.com, SAN = *.sipdomain.com
  ```

> [!NOTE]
> No debe crear una entrada DNS externa para SIP. \<sipdomain\>. com porque este nombre pertenece a la implementación de Office 365.

> [!NOTE]
> Si desea usar un certificado único para todos los grupos perimetrales implementados en su organización y no puede usar un certificado de comodín como se describe en la opción 2, entonces deberá incluir el FQDN para todos los grupos perimetrales implementados en el nombre SAN en el certificado. 

 **Si tiene varios dominios SIP:**

Necesitará agregar sip.sipdomain.com para todos los dominios SIP y el nombre de los grupos de servidor perimetral de acceso por dominio (puede ser un grupo físico, pero con nombres distintos). A continuación se muestra un ejemplo de entradas SN y SAN en un escenario de varios dominios SIP:

- **Opción 1.** El nombre del asunto debe contener el nombre de la sección que asignó a los componentes de Edge. Tenga en cuenta que el nombre del asunto no puede ser sip.sipdomain.com porque este nombre está reservado para el componente perimetral de Skype empresarial en línea. El SAN tiene que contener sip.sipdomain.com y el nombre de grupo perimetral de acceso:

  ```
  SN = accessedgepoolnameforsite1.sipdomain1.com, SAN = sip.sipdomain1.com, sip.sipdomain2.com,
  acessedgepoolnameforsite1.sipdomain1.com
  ```

- <strong>Opción 2.</strong> Si desea usar un único certificado comodín en todos los servidores de grupo perimetral que implementa, puede usar una entrada SAN comodín de \*. sipdomain.com en lugar del nombre del grupo de bordes en el certificado. El nombre del firmante puede ser el nombre de grupo perimetral de acceso de cualquiera de los grupos de servidores perimetrales que ya haya implementado:

  ```
  SN = accessedgepoolnameforsite1.sipdomain.com, SAN = sip.sipdomain1.com, sip.sipdomain2.com,
  SAN = *.sipdomain1.com
  ```

> [!NOTE]
> No debe crear una entrada DNS externa para SIP. \<sipdomain\>. com porque este nombre pertenece a la implementación de Office 365.

Para fines de implementación, puede usar la tabla siguiente:

|**Opción**|**Descripción**|**Notas**|
|:-----|:-----|:-----|
|¿Qué opción usará para su implementación?  <br/> |Opción 1 o 2  <br/> ||
|SN  <br/> |Proporciona el SN del certificado  <br/> ||
|SAN  <br/> |Proporciona el SAN del certificado  <br/> ||

Si va a utilizar TLS entre la puerta de enlace y el servidor de mediación, deberá obtener un certificado raíz o una cadena de certificados completa para el certificado asignado a la puerta de enlace.

## <a name="dial-plan-considerations"></a>Consideraciones de plan de marcado
<a name="BKMK_DailPlan"> </a>

Cloud Connector requiere que se use un plan de marcado en línea. Para obtener más información sobre cómo configurar un plan de marcado en línea, vea [¿Qué son los planes de marcado?](/microsoftteams/what-are-dial-plans) 
  
## <a name="high-availability-considerations"></a>Consideraciones sobre alta disponibilidad
<a name="BKMK_HA"> </a>

Al implementar Cloud Connector Edition para una alta disponibilidad, se implementan al menos dos dispositivos que actúan como copias de seguridad para cada uno. Cada dispositivo consta de cuatro componentes: Edge, media, almacén de administración central (CMS) y controlador de dominio.

En general, si un componente de un equipo deja de funcionar, la edición de Cloud Connector Edition puede seguir controlando las llamadas, pero debe tener en cuenta lo siguiente:

- **Consideraciones sobre los componentes de controlador de dominios, CMS y de mediación**

    Suponga que se producen problemas en el componente de controlador de dominio o CMS de un dispositivo. El dispositivo todavía puede administrar las llamadas salientes y entrantes, pero si reinicia el componente de mediación mientras el controlador de dominios o de CMS no está disponible, la mediación no funcionará. Esto se aplica de igual manera al reinicio del componente de CMS cuando el controlador de dominios no está accesible.

    **Recomendación:** Antes de reiniciar los componentes, verifique la disponibilidad de los demás componentes del dispositivo.

- **Consideraciones relacionadas con el componente perimetral**

    Si el componente perimetral de un dispositivo no está disponible, el comportamiento de las llamadas entrantes y salientes puede variar de la siguiente manera:

  - **Llamada saliente**: una llamada de su usuario en Internet a una red RTC.

    El mecanismo de distribución de llamadas en la nube identificará que un componente perimetral no está accesible y redirigirá todas las llamadas a otro dispositivo, de modo que la llamada saliente se realiza correctamente.

  - **Llamada entrante**: una llamada de la red RTC a un usuario que se encuentra en una red local o en Internet.

     Si el componente perimetral del dispositivo que recibe la llamada no funciona, las llamadas entrantes a este dispositivo no se realizarán correctamente porque el componente de mediación no puede redirigir la llamada al componente perimetral en el otro dispositivo.

    **Recomendación:** Tener un sistema de supervisión instalado. Después de identificar un mal funcionamiento del componente Edge, cierre todos los componentes del dispositivo en los que el componente Edge no esté disponible.

## <a name="cloud-connector-media-flow"></a>Flujo multimedia de Cloud Connector
<a name="BKMK_MediaFlow"> </a>

En los siguientes diagramas se describe el flujo de una llamada entrante y saliente a través de Cloud Connector Edition. Esta información resulta muy útil para saber cómo se establece la conectividad.

En el primer diagrama, un usuario interno realiza una llamada saliente como se indica a continuación:

1. Gerardo, un usuario hospedado en línea (pero que ahora se encuentra en la red interna), realiza una llamada a un usuario de RTC externo.

2. Rutas de tráfico SIP a Skype empresarial online.

3. Skype empresarial online realiza una búsqueda numérica inversa del número. No se puede realizar la búsqueda de números inverso porque este número no pertenece a ningún usuario de la organización de Skype empresarial.

4. La llamada se enruta al componente perimetral (primero a SIP y flujo multimedia a través de componente perimetral en línea; el tráfico multimedia irá al componente de mediación a través del firewall interno).

5. Si la ruta existe, el componente perimetral retransmite el tráfico al componente de mediación en la red perimetral.

6. El componente de mediación envía el tráfico a la puerta de enlace RTC.

![Flujo multimedia de salida para Cloud Connector](../../media/c495a2bb-305c-46ef-b16d-b8f9f2b937a8.png)

En el diagrama siguiente, un usuario interno recibe una llamada entrante como se indica a continuación:

1. La puerta de enlace RTC recibe una llamada del usuario Gerardo, que está hospedado en línea, pero ahora está en la red interna.

2. El tráfico SIP se redirige al componente de mediación.

3. El componente de mediación envía tráfico SIP al componente Edge y, a continuación, va a Skype empresarial online.

4. Skype empresarial online realiza una búsqueda de números invertidas del número y encuentra que este es el usuario David.

5. La señalización de SIP va a todos los puntos de presencia de Gerardo.

6. El tráfico multimedia se establecerá entre la puerta de enlace y el componente de mediación, así como entre el componente de mediación y el extremo.

![Flujo multimedia de entrada para Cloud Connector](../../media/ba5da6f6-e357-43c6-9e8f-4bfdde97c176.png)

## <a name="monitoring-and-troubleshooting"></a>Supervisión y solución de problemas
<a name="BKMK_Monitor"> </a>

El mecanismo de supervisión y solución de problemas se instala automáticamente con cada dispositivo de Cloud Connector. El mecanismo detecta los siguientes eventos:

- Una o varias máquinas virtuales de un dispositivo de Cloud Connector no están conectadas a un conmutador virtual interno o de Internet.

- El estado de una o varias máquinas virtuales de un dispositivo de Cloud Connector es guardado o detenido.

- Servicios que no se ejecutan.

  Si se detecta uno de los siguientes eventos, se purga todo el dispositivo del conector Cloud y se marca como desconectado para evitar que se intente establecer llamadas a un dispositivo que no funciona correctamente. Las características de recuperación automática de Cloud Connector restaurarán posteriormente los servicios y marcará el dispositivo como en línea. Si la recuperación automática falla por algún motivo, consulte [Troubleshoot your Cloud Connector deployment](troubleshoot-your-cloud-connector-deployment.md).

  - En la máquina virtual del Almacén de administración central:  

     - Agente de replicador maestro de Skype Empresarial

     - Agente de replicador de réplicas de Skype Empresarial

  - En la máquina virtual del servidor de mediación:

     - Agente de replicador de réplicas de Skype Empresarial

     - Servidor de mediación de Skype Empresarial Server

  - En la máquina virtual del servidor perimetral:

     - Agente de replicador de réplicas de Skype Empresarial

     -   Servidor perimetral de acceso de Skype Empresarial Server

     - Servidor perimetral de audio y vídeo de Skype Empresarial Server

     - Autenticación de audio y vídeo de Skype Empresarial Server

     - Servidor perimetral de conferencia web de Skype Empresarial Server

- La regla de entrada del firewall de Windows para "CS RTCSRV" en el servidor perimetral, "CS RTCMEDSRV" en el servidor de mediación, está deshabilitada.

Cloud Connector 2.1 y versiones posteriores admiten la supervisión de Cloud Connector mediante Operations Management Suite (OMS). Para obtener más información, vea [Monitor Cloud Connector using Operations Management Suite (OMS)](monitor-cloud-connector-using-operations-management-suite-oms.md).

## <a name="for-more-information"></a>Más información
<a name="BKMK_MoreInfo"> </a>

Para obtener más información, vea los artículos siguientes:

- [Soluciones de telefonía de Microsoft](https://docs.microsoft.com/en-us/SkypeForBusiness/hybrid/msft-telephony-solutions)

- [Configuración y administración de Skype Empresarial Cloud Connector Edition](configure-skype-for-business-cloud-connector-edition.md)

- [Plan para la omisión de medios en Cloud Connector Edition](plan-for-media-bypass-in-cloud-connector-edition.md)

- [Implementación de omisión de medios en Cloud Connector Edition](deploy-media-bypass-in-cloud-connector.md)


