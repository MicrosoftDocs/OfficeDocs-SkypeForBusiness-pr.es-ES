---
title: Plan for Skype for Business Cloud Connector Edition
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
description: Encuentre información en Skype Empresarial Cloud Connector Edition, un conjunto de máquinas virtuales empaquetadas (VM) que implementan conectividad RTC local con sistema telefónico (PBX en la nube).
ms.openlocfilehash: ec96662e3dbe432ce8cebe7dc59004350124451e
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/03/2020
ms.locfileid: "47358996"
---
# <a name="plan-for-skype-for-business-cloud-connector-edition"></a>Plan for Skype for Business Cloud Connector Edition

> [!Important]
> Cloud Connector Edition se retirará el 31 de julio de 2021 junto con Skype Empresarial Online. Una vez que su organización haya actualizado a Teams, obtenga información sobre cómo conectar su red de telefonía local a Teams mediante [el enrutamiento directo.](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)

Encuentre información en Skype Empresarial Cloud Connector Edition, un conjunto de máquinas virtuales empaquetadas (VM) que implementan conectividad RTC local con sistema telefónico (PBX en la nube).

Cloud Connector Edition puede ser la solución adecuada para su organización si aún no tiene una implementación existente de Lync Server o Skype Empresarial Server. Si aún está investigando qué solución del sistema telefónico es adecuada para su empresa, consulte [soluciones de telefonía de Microsoft.](https://docs.microsoft.com/SkypeForBusiness/hybrid/msft-telephony-solutions)

En este documento se describen los requisitos de Cloud Connector Edition y las topologías admitidas, y se ayuda a planear la implementación de Cloud Connector Edition. Asegúrese de leer este tema antes de configurar el entorno de Cloud Connector. Cuando esté listo para implementar y configurar Cloud Connector Edition, consulte [Configurar y administrar Skype Empresarial Cloud Connector Edition.](configure-skype-for-business-cloud-connector-edition.md)

Cloud Connector Edition 2.1 ya está disponible. Si aún no ha actualizado a la versión 2.1, consulte [Actualizar a una nueva versión de Cloud Connector](upgrade-to-a-new-version-of-cloud-connector.md). Puede encontrar el archivo de instalación en [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller) .

> [!NOTE]
> Microsoft admite la versión anterior de Cloud Connector Edition durante 60 días después del lanzamiento de una nueva versión. Microsoft admitirá la versión 2.0.1 durante 60 días después del lanzamiento de la versión 2.1 para permitirle tiempo para actualizar. Ya no se admiten todas las versiones anteriores a 2.0.1.

Cloud Connector Edition es una oferta híbrida que consta de un conjunto de máquinas virtuales empaquetadas (VM) que implementan conectividad RTC local con sistema telefónico. Al implementar una topología mínima de Skype Empresarial Server en un entorno virtualizado, los usuarios de su organización que están en la nube pueden recibir servicios PBX desde la nube de Microsoft, pero la conectividad con RTC se proporciona a través de la infraestructura de voz local existente.

![Diagrama de topología que muestra la puerta de enlace de PBX en la nube que conecta PBX en la nube con una implementación local de Skype Empresarial.](../../media/bd898e69-6458-4276-aebe-1854f28ed6fa.png)

Dado que Cloud Connector le permite integrar los servicios del sistema telefónico con su entorno de telefonía existente (por ejemplo, PBX, dispositivos analógicos y centros de llamadas), puede implementar una migración por fases de la solución de telefonía existente al sistema telefónico.

Por ejemplo, supongamos que su empresa tiene un centro de llamadas sofisticado con funciones específicas que el Sistema telefónico no proporciona. Puede dejar a los usuarios del centro de llamadas con la solución existente, pero mover otros usuarios al Sistema telefónico.

Cloud Connector proporcionará enrutamiento entre los usuarios locales y en línea, y puede elegir usar su propio proveedor de RTC con Sistema telefónico.

Tenga en cuenta lo siguiente al planear la implementación de Cloud Connector Edition:

- Para usar Cloud Connector para aprovechar las soluciones de voz en la nube, deberá registrarse en una organización de Microsoft 365 u Office 365 que incluya Sistema telefónico. Si aún no tiene una organización de Microsoft 365 u Office 365, puede aprender a registrarse aquí: [Microsoft 365 para empresas.](https://products.office.com/business/office) Tenga en cuenta que tendrá que suscribirse a un plan que incluya Skype Empresarial Online.

- Para registrar dispositivos de Cloud Connector con el servicio de Skype Empresarial Online y ejecutar varios cmdlets, Cloud Connector 2.0 y versiones posteriores requiere una cuenta dedicada de Microsoft 365 u Office 365 con los derechos de administrador de inquilinos de Skype Empresarial. Las versiones de Cloud Connector anteriores a 2.0 requieren una cuenta dedicada de Microsoft 365 u Office 365 con derechos de administrador global de inquilinos.

- Cloud Connector no requiere una implementación completa de Skype Empresarial Server local.

    Actualmente, Cloud Connector no puede coexistir con los servidores locales de Lync o Skype Empresarial. Si desea mover los usuarios existentes de Lync o Skype Empresarial a Microsoft 365 y seguir proporcionando telefonía local a los usuarios, considere la posibilidad de usar el Sistema telefónico con conectividad local mediante una implementación existente de Skype Empresarial Server. Para obtener más información, vea [Plan your Phone System (Cloud PBX) solution](plan-your-phone-system-cloud-pbx-solution.md) and Plan Phone System with [on-premises PSTN connectivity in Skype for Business Server](plan-phone-system-with-on-premises-pstn-connectivity.md).

- Si tenía una implementación anterior de Skype Empresarial o Lync Server y extendió el esquema, no es necesario limpiar el esquema de la implementación de Cloud Connector, siempre y cuando haya quitado todos los componentes de Skype Empresarial o Lync Server de su entorno.

- Los usuarios están en línea.

- Si su organización ha configurado la sincronización de directorios (DirSync), todas las cuentas de los usuarios que están previstos para la voz híbrida deben crearse primero en la implementación local y, a continuación, sincronizarse con la nube.

- Si es necesario, puede conservar su operador de RTC actual.

- Si desea proporcionar conferencias de acceso telefónico local a los usuarios hospedados en Cloud Connector, puede comprar una licencia de conferencia RTC o pagar a medida que vaya ofertando audioconferencias de Microsoft.

- La licencia de Audioconferencia (o pagar a medida que vaya ofreciendo) también es necesaria para las escalaciones de llamadas. Si un usuario de Skype Empresarial recibe una llamada de un usuario rtc externo y desea agregar un participante más a esa llamada (escalar la llamada a una conferencia), la escalación se realizará a través del servicio de audioconferencia de Microsoft.

- Cloud Connector 2.0 y versiones posteriores ahora admiten la omisión de medios. La omisión de medios permite a un cliente enviar medios directamente al próximo salto de la red telefónica conmutada (RTC), una puerta de enlace o un controlador de borde de sesión (SBC), y eliminar el componente Cloud Connector Edition de la ruta de acceso multimedia. Para obtener más información, vea [Planear la omisión de medios en Cloud Connector Edition](plan-for-media-bypass-in-cloud-connector-edition.md).

- Cloud Connector 2.1 y versiones posteriores admite la supervisión de Cloud Connector mediante Operations Management Suite (OMS). Para obtener más información, vea [Monitor Cloud Connector using Operations Management Suite (OMS)](monitor-cloud-connector-using-operations-management-suite-oms.md)

- Cloud Connector está disponible en todos los países donde Office 365 Enterprise E5 está disponible.

En este tema se presentan las siguientes secciones:

- [Componentes de Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md#BKMK_Components)

- [Topologías de Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md#BKMK_Topologies)

- [Requisitos para la implementación](plan-skype-for-business-cloud-connector-edition.md#BKMK_Requirements)

- [Información que necesita recopilar antes de la implementación](plan-skype-for-business-cloud-connector-edition.md#BKMK_PlanDeployment)

- [Consideraciones del plan de marcado](plan-skype-for-business-cloud-connector-edition.md#BKMK_DailPlan)

- [Consideraciones de alta disponibilidad](plan-skype-for-business-cloud-connector-edition.md#BKMK_HA)

- [Flujo de medios de Cloud Connector](plan-skype-for-business-cloud-connector-edition.md#BKMK_MediaFlow)

- [Supervisión y solución de problemas](plan-skype-for-business-cloud-connector-edition.md#BKMK_Monitor)

- [Más información](plan-skype-for-business-cloud-connector-edition.md#BKMK_MoreInfo)

## <a name="cloud-connector-edition-components"></a>Componentes de Cloud Connector Edition
<a name="BKMK_Components"> </a>

Con Cloud Connector Edition, implementa un conjunto de máquinas virtuales empaquetadas que contienen una topología mínima de Skype Empresarial Server, que consta de un componente perimetral, un componente de mediación y un rol de Almacén de administración central (CMS). También instalará un controlador de dominio, que es necesario para el funcionamiento interno de Cloud Connector. Estos servicios están configurados para la implementación híbrida con su organización de Microsoft 365 u Office 365 que incluye los servicios de Skype Empresarial Online.

![Componentes de Cloud Connector Edition](../../media/f2d4b8a7-c2f4-4cfc-8137-f187399c1298.png)

Los componentes de Cloud Connector proporcionan la siguiente funcionalidad:

- **Componente perimetral:** la comunicación entre la topología local y los servicios en línea pasa por el componente perimetral, que incluye los siguientes componentes:

  - **Servidor perimetral de** acceso: proporciona enrutamiento SIP entre la implementación local y Skype Empresarial Online.

  - **Retransmisión multimedia:** proporciona enrutamiento de medios entre el componente de mediación y otros extremos multimedia.

  - **Autenticación de retransmisión multimedia/MRAS:** genera tokens para el acceso a la retransmisión multimedia.

- **Enrutamiento saliente:** proporciona equilibrio de carga del tráfico de voz entre puertas de enlace o SBC conectados a un dispositivo de Cloud Connector. Las llamadas se dividirán uniformemente entre todas las puertas de enlace o SBC conectadas al dispositivo de Cloud Connector.

    Proporciona enrutamiento a puertas de enlace basadas en directivas. Solo se admiten directivas globales basadas en números RTC de destino (saliente).

- **Rol Almacén de administración central (CMS):** incluye el almacén de configuración para los componentes de la topología, incluida la transferencia de archivos de CMS.

- Réplica del Almacén de administración central **(CMS):** sincroniza la información de configuración de la base de datos global de CMS en el servidor de roles de CMS.

- **Controlador de dominio:** Servicios de dominio de Active Directory de Cloud Connector para almacenar toda la configuración global y los grupos necesarios para implementar los componentes de Cloud Connector. Se creará un bosque para cada dispositivo de Cloud Connector. El controlador de dominio no debe tener ninguna conexión con el Active Directory de producción. Los servicios de Active Directory incluyen:

  - Servicios de dominio de Active Directory

  - Servicios de certificados de Active Directory para emitir certificados internos

- **Componente de mediación:** implementa el protocolo de asignación de puertas de enlace SIP y multimedia entre Skype Empresarial y las puertas de enlace RTC. Incluye una réplica de CMS que sincroniza la configuración de la base de datos global de CMS.

## <a name="cloud-connector-edition-topologies"></a>Topologías de Cloud Connector Edition
<a name="BKMK_Topologies"> </a>

A efectos de esta discusión, nos referiremos a los sitios RTC. Un sitio RTC es una combinación de dispositivos de Cloud Connector, implementados en la misma ubicación y con puertas de enlace RTC comunes conectadas a ellos. Los sitios RTC le permiten:

- Proporcione conectividad a las puertas de enlace más cercanas a los usuarios.

- Permita la escalabilidad implementando varios dispositivos de Cloud Connector en uno o más sitios RTC.

- Permitir la alta disponibilidad mediante la implementación de varios dispositivos de Cloud Connector en un único sitio RTC.

En este tema se presentan los sitios RTC. Para obtener más información acerca de la planeación de los sitios RTC, vea [Plan for Cloud Connector Edition PSTN sites](plan-for-cloud-connector-edition-pstn-sites.md).

Puede implementar las siguientes topologías de Cloud Connector:

- Un único dispositivo de Cloud Connector Edition por sitio RTC. Esta topología se recomienda para fines de evaluación solo porque no proporciona alta disponibilidad.

- Varios dispositivos de Cloud Connector Edition por sitio RTC para proporcionar alta disponibilidad.

- Varios sitios RTC con varios dispositivos de Cloud Connector Edition para proporcionar escalabilidad con alta disponibilidad. Puede implementar hasta 200 sitios.

Al planear la topología, tenga en cuenta lo siguiente:

- Con Cloud Connector 2.0 y versiones posteriores, un sitio RTC puede tener hasta 16 dispositivos de Cloud Connector. Las versiones anteriores admiten hasta 4 dispositivos por sitio.

- Hay dos tipos de configuraciones de hardware probadas con Cloud Connector:

  - La versión más grande es capaz de controlar grandes volúmenes de llamadas simultáneas y es compatible con todos los tipos de entornos de producción.

  - La versión más pequeña está diseñada para ejecutarse en hardware de gama inferior y se puede usar con fines de evaluación o para sitios con volúmenes de llamadas bajos. Si implementa una versión más pequeña de Cloud Connector, debe tener en cuenta los requisitos de hardware de clase de producción (como las fuentes de alimentación duales).

- Si tiene Cloud Connector versión 2.0 o posterior e implementa la configuración máxima de 16 dispositivos (con hardware más grande), el sitio RTC puede administrar hasta 8.000 llamadas simultáneas. Si implementa la versión más pequeña, el límite admitido es 800.

    También debe dedicar algunos dispositivos para alta disponibilidad. La recomendación mínima es que se debe reservar un dispositivo para alta disponibilidad.

  - Con la versión 2, si implementa una configuración 15+1, el sitio RTC puede administrar hasta 7.500 llamadas simultáneas.

  - Si tiene una versión anterior e implementa la configuración máxima de 3 + 1 (con hardware más grande), el sitio RTC puede administrar hasta 1500 llamadas simultáneas. Si implementa la versión más pequeña, el límite admitido es 150.

-  Si necesita tener más llamadas por sitio RTC, puede escalar verticalmente implementando sitios RTC adicionales en la misma ubicación.

> [!NOTE]
> A menos que se indique lo contrario, los diagramas y ejemplos siguientes suponen el uso de la versión más grande de Cloud Connector.

### <a name="single-cloud-connector-appliance-within-a-single-pstn-site"></a>Dispositivo de Cloud Connector único dentro de un único sitio RTC

En el siguiente diagrama se muestra un único dispositivo de Cloud Connector Edition dentro de un único sitio RTC. Tenga en cuenta que Cloud Connector consta de cuatro máquinas virtuales instaladas en una máquina host física que se encuentra dentro de una red perimetral por motivos de seguridad.

![Un conector de nube con un sitio RTC](../../media/7ffe6953-8c66-4323-940e-cd2e6c3c2a66.png)

### <a name="multiple-cloud-connector-appliances-within-a-single-pstn-site"></a>Varios dispositivos de Cloud Connector dentro de un único sitio RTC

 Por motivos de escalabilidad y alta disponibilidad, puede elegir tener varias ediciones de Cloud Connector en un único sitio RTC, como se muestra en el siguiente diagrama. Tenga en cuenta lo siguiente:

- Las llamadas se distribuyen en orden aleatorio entre los conectores de nube de un grupo.

- Por motivos de planeación de la capacidad, debe tener en cuenta la capacidad de controlar la carga si uno o más conectores de nube se desconectan, en función de los cálculos siguientes:

  - **N+1 cuadros.** Para la versión más grande de Cloud Connector, N+1 cuadros admiten 500 N llamadas simultáneas con \* un 99,8 % de disponibilidad.

    Para la versión más pequeña de Cloud Connector, N+1 cuadros admiten 50 N llamadas simultáneas con \* un 99,8 % de disponibilidad.

  - **N+2 cuadros.** Para la versión más grande de Cloud Connector, N+2 cuadros admiten 500 N llamadas simultáneas con \* un 99,9 % de disponibilidad.

    Para la versión más pequeña de Cloud Connector, N+2 cuadros admiten 50 N llamadas simultáneas con \* un 99,9 % de disponibilidad.

![Dos conectores en la nube dentro de un sitio RTC](../../media/fc0dc47f-5595-42cb-9432-9c8ff3e134e9.png)

### <a name="multiple-pstn-sites-with-one-or-more-cloud-connectors-per-site"></a>Varios sitios RTC con uno o más conectores en la nube por sitio

También puede elegir tener varios sitios RTC con una o más ediciones de Cloud Connector en cada sitio. Si el sitio RTC alcanza el límite de llamadas simultáneas, puede agregar otro sitio RTC para controlar la carga.

Varios sitios RTC también le permiten proporcionar conectividad a las puertas de enlace más cercanas a los usuarios. Por ejemplo, supongamos que tiene puertas de enlace RTC en Seattle y Ámsterdam. Puede implementar dos sitios RTC (uno en Seattle y otro en Ámsterdam) y asignar usuarios para que usen el sitio RTC más cercano a ellos. Los usuarios de Seattle se enrutarán al sitio RTC y a las puertas de enlace de Seattle, mientras que los usuarios de Ámsterdam se enrutarán al sitio RTC de Ámsterdam y a las puertas de enlace:

![Cloud Connector Edition en 2 sitios RTC](../../media/16ead6d3-67da-4e71-b4d5-d895b4c9384e.png)

## <a name="requirements-for-deployment"></a>Requisitos para la implementación
<a name="BKMK_Requirements"> </a>

Antes de implementar Cloud Connector Edition, asegúrese de que tiene lo siguiente para su entorno:

- **Para el equipo host:** Las máquinas virtuales de Cloud Connector deben implementarse en hardware dedicado que ejecute Windows Server 2012 R2 Datacenter Edition (inglés) con el rol de Hyper-V habilitado.

    Para la versión 2.0 y posteriores, la tarjeta de red del equipo host enlazada al conmutador de la red corporativa de Skype Empresarial debe tener una dirección IP configurada en la misma subred que los equipos de red corporativa de Cloud Connector.

- Para las versiones 2.1 y posteriores, el dispositivo host debe tener instalado .NET Framework 4.6.1 o posterior.

- **Para las máquinas virtuales:** Una imagen ISO (.iso) de Windows Server 2012 R2 (inglés). La ISO se convertirá en VHD para las máquinas virtuales que ejecutarán Skype Empresarial Cloud Connector Edition.

- El hardware necesario para admitir la instalación de las 4 máquinas virtuales para cada Edición de Cloud Connector en la implementación. Se recomiendan las siguientes configuraciones:

  - Procesador dual de 64 bits, seis núcleos (12 núcleos reales), 2,50 gigahercios (GHz) o superior

  - 64 gigabytes (GB) de RAM de ECC

  - Cuatro discos SAS de 6 GB (o más) de 10 K RPM y 128 MB de caché SAS de 6 GB, configurados en una configuración RAID 5

  - Tres adaptadores de red de alto rendimiento RJ45 de 1 Gbps

- Si decide implementar la versión más pequeña de Cloud Connector Edition que admite hasta 50 llamadas simultáneas, necesitará el siguiente hardware:

  - Intel i7 4790 de cuatro núcleos con gráficos Intel 4600 (no se necesitan gráficos de gama alta)

  - 32 GB DESC3-1600 que no son ECC

  - 2: 1 TB 7200RPM SATA III (6 Gbps) en RAID 0

  - 2: Ethernet de 1 Gbps (RJ45)

- Si se requiere un servidor proxy en el equipo host para navegar por Internet, debe realizar los siguientes cambios de configuración:

  - Para omitir el proxy, especifique la configuración de Proxy WinHTTP establecida con el servidor proxy y una lista de omisión que incluya "192.168.213". \* red usada por los servicios de cloud Connector Managements y la subred de la red corporativa de Skype Empresarial, tal como se define en el archivo CloudConnector.ini cliente. De lo contrario, se producirá un error en la conectividad de administración e impedirá la implementación y recuperación automática de Cloud Connector. El siguiente es un comando de configuración winhttp de ejemplo: proxy de conjunto de netsh winhttp "10.10.10.175:8080" bypass-list=" \* .local;1. \* ; 172.20. \* ;192.168.218. \* ' \<local\> ".

  - Especifica la configuración de proxy por equipo en lugar de por usuario. De lo contrario, se producirá un error en las descargas de Cloud Connector. Puedes especificar la configuración de proxy por equipo con un cambio en el Registro o con la configuración de directiva de grupo de la siguiente manera:

  - **Registro:** HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows\CurrentVersion\Internet Settings] ProxySettingsPerUser dword:00000000

  - **Directiva de grupo:** Plantillas \> administrativas del equipo Componentes de Windows Internet \> \> Explorer: configurar proxy por equipo (en lugar de por usuario)

- PBX/tronco cualificado o SBC/puerta de enlace cualificado (se recomienda un mínimo de dos puertas de enlace).

    Cloud Connector admite los mismos controladores de borde de sesión (SBC) certificados para Skype Empresarial. Para obtener más información, consulte [Infraestructura de telefonía para Skype Empresarial.](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways)

- Una cuenta de administrador de servidor local con permisos para instalar y configurar Hyper-V en los servidores host. La cuenta debe tener permisos de administrador en el servidor local donde está instalado y configurado Hyper-V.

- Durante la implementación, se le pedirá que cree una cuenta de administrador de dominio con permisos para crear y publicar la topología en el dominio de Cloud Connector.

- Los registros DNS externos, que se definen en el archivo CloudConnector.ini incluido con el paquete de instalación:

  - Registro DNS externo para el servicio perimetral de acceso del componente perimetral; por ejemplo, ap. \<Domain Name\> . Necesita un registro por sitio RTC. Este registro debe contener direcciones IP de todos los bordes de ese sitio.

- Una organización de Microsoft 365 u Office 365 con todos los registros DNS y SRV necesarios creados.

    > [!IMPORTANT]
    > Al integrar el inquilino con Cloud Connector Edition, no se admite el uso del sufijo de dominio predeterminado, .onmicrosoft.com, como dominio SIP para su organización. > no puede usar sip.\<Domain Name\> como el nombre de la interfaz proxy de acceso perimetral de Cloud Connector porque Microsoft 365 y Office 365 usan este registro DNS.

- Un certificado para el servidor perimetral externo obtenido de una entidad de certificación (CA) pública.

- Se han completado las reglas de firewall para permitir el tráfico a través de los puertos necesarios.

- Una conexión a Internet para el equipo host y las máquinas virtuales. Cloud Connector descarga parte del software de Internet; por lo tanto, debe proporcionar información de puerta de enlace y servidor DNS para que el equipo host de Cloud Connector y las máquinas virtuales puedan conectarse a Internet y descargar el software necesario.

- Un módulo de PowerShell remoto de inquilino instalado en el equipo host.

- Las credenciales de administrador de Skype Empresarial para ejecutar PowerShell remoto.

    > [!IMPORTANT]
    > La cuenta de administrador NO DEBE tener habilitada la autenticación multifactor.

> [!NOTE]
> La implementación de Cloud Connector solo se admite en la plataforma virtualizada de Microsoft Hyper-V. No se admiten otras plataformas, como VMware y Amazon Web Services.

> [!NOTE]
> Las instrucciones de hardware mínimas para ejecutar Cloud Connector se basan en la capacidad básica de hardware (núcleos, MHz, gigabytes, entre otros) con algún búfer para dar cabida a problemas de rendimiento intangibles que se atajen en la arquitectura de cualquier equipo. Microsoft ha ejecutado las peores pruebas de carga de casos en hardware disponible comercialmente que reúne las instrucciones mínimas. Se comprueba la calidad de los medios y el rendimiento del sistema. Los partners oficiales de dispositivos de Cloud Connector de Microsoft tienen implementaciones de hardware específicas de Cloud Connector en las que han probado de forma independiente el rendimiento y se adaptan a la idoneidad de su hardware para cumplir los requisitos de carga y calidad.

> [!NOTE]
> Los dispositivos producidos por AudioCodes y Sonus han modificado el código y se ejecutan en la edición Windows Server Standard de los servidores. Estos dispositivos son compatibles.

## <a name="information-you-need-to-gather-before-deployment"></a>Información que necesita recopilar antes de la implementación
<a name="BKMK_PlanDeployment"> </a>

Antes de comenzar la implementación, debe determinar el tamaño de la implementación, los dominios SIP que se están prestando servicio y la información de configuración de cada sitio RTC que planea implementar. Para empezar, hará lo siguiente:

- Identifique todos los dominios SIP que recibirá esta implementación en función de los URI de SIP en uso en su empresa.

- Determine el número de sitios RTC que necesita implementar.

- Asegúrese de que tiene el hardware necesario para admitir las cuatro máquinas virtuales que instalará para cada Edición de Cloud Connector.

Para cada sitio RTC que planee implementar, debe:

- Cree nombres para todos los componentes de cada dispositivo de Cloud Connector (vea [Determinar los parámetros de implementación).](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams)

- Definir intervalos de puertos (vea [Puertos y protocolos).](plan-skype-for-business-cloud-connector-edition.md#BKMB_Ports)

- Cree registros DNS externos para el componente perimetral (vea [Requisitos para la implementación).](plan-skype-for-business-cloud-connector-edition.md#BKMK_Requirements)

- Determine los requisitos de certificado para el componente perimetral (vea [Requisitos de certificado).](plan-skype-for-business-cloud-connector-edition.md#BKMK_Certs)

### <a name="ports-and-protocols"></a>Puertos y protocolos
<a name="BKMB_Ports"> </a>

Al definir intervalos de puertos multimedia, tenga en cuenta lo siguiente:

- Los clientes siempre usan el intervalo de puertos de 50000 a 50019 para el tráfico de medios: este intervalo está predefinido en Skype Empresarial Online y no se puede cambiar.

- De forma predeterminada, el componente de mediación usará el intervalo de puertos de 49 152 a 57 500 para el tráfico de medios. Sin embargo, la conexión se establece a través del firewall interno y, por motivos de seguridad, puede limitar este intervalo de puertos en la topología. Necesitará hasta 4 puertos por llamada. Si desea limitar el número de puertos entre el componente de mediación y la puerta de enlace RTC, también deberá configurar el intervalo de puertos correspondiente en la puerta de enlace.

- Debe implementar Cloud Connector en una red perimetral. Esto significa que tendrá dos firewalls:

  - El primer firewall es externo entre Internet y la red perimetral.

  - El segundo firewall es interno entre la red perimetral y la red interna.

    Los clientes pueden estar en Internet o en la red interna:

  - Los clientes de Internet se conectarán a la RTC a través del firewall externo a través del componente perimetral.

  - Los clientes de la red interna se conectarán a través del firewall interno al componente de mediación de la red perimetral, que conectará el tráfico a la puerta de enlace RTC o SBC.

    Esto significa que debe abrir puertos en ambos firewalls.

En las tablas siguientes se describen los puertos y los intervalos de puertos para los firewalls internos y externos.

En esta tabla se muestran los puertos y los intervalos de puertos para habilitar la comunicación entre los clientes de la red interna y el componente de mediación:

**Firewall interno**



|**IP de origen**|**IP de destino**|**Puerto de origen**|**Puerto de destino**|
|:-----|:-----|:-----|:-----|
|Componente de mediación de Cloud Connector  <br/> |Puerta de enlace RTC/SBC  <br/> |Cualquiera  <br/> |TCP 5060\*\*  <br/> |
|Puerta de enlace RTC/SBC  <br/> |Componente de mediación de Cloud Connector  <br/> |Cualquiera  <br/> |TCP 5068/ TLS 5067  <br/> |
|Componente de mediación de Cloud Connector  <br/> |Puerta de enlace RTC/SBC  <br/> |UDP 49 152 - 57 500  <br/> |Cualquiera\*\*\*  <br/> |
|Puerta de enlace RTC/SBC  <br/> |Componente de mediación de Cloud Connector  <br/> |Cualquiera\*\*\*  <br/> |UDP 49 152 - 57 500  <br/> |
|Componente de mediación de Cloud Connector  <br/> |Clientes internos  <br/> |TCP 49 152 - 57 500\*  <br/> |TCP 50.000-50.019  <br/> (Opcional)  <br/> |
|Componente de mediación de Cloud Connector  <br/> |Clientes internos  <br/> |UDP 49 152 - 57 500\*  <br/> |UDP 50.000-50.019  <br/> |
|Clientes internos  <br/> |Componente de mediación de Cloud Connector  <br/> |TCP 50.000-50.019  <br/> |TCP 49 152 - 57 500\*  <br/> |
|Clientes internos  <br/> |Componente de mediación de Cloud Connector  <br/> |UDP 50.000-50.019  <br/> |UDP 49 152 -57 500\*  <br/> |

\* Este es el intervalo de puertos predeterminado en el componente de mediación. Para un flujo de llamadas óptimo, se requieren cuatro puertos por llamada.

\*\* Este puerto debe configurarse en la puerta de enlace SBC/RTC; 5060 es un ejemplo. Puede configurar otros puertos en la puerta de enlace RTC/SBC.

\*\*\* Tenga en cuenta que también puede limitar el intervalo de puertos en su SBC/Puerta de enlace si lo permite el fabricante de SBC/Gateway.

Por motivos de seguridad, puede limitar el intervalo de puertos para el componente de mediación mediante el cmdlet [Set-CsMediationServer.](https://docs.microsoft.com/powershell/module/skype/set-csmediationserver?view=skype-ps)

Por ejemplo, el siguiente comando limita el número de puertos que el componente de mediación usará para el tráfico multimedia a 50 000 - 51 000 para audio (entrada y salida). El componente de mediación podrá administrar 250 llamadas simultáneas con esta configuración. Tenga en cuenta que es posible que también desee limitar este intervalo en la puerta de enlace RTC/SBC:

```powershell
Set-CSMediationServer -Identity MediationServer:mspool.contoso.com -AudioPortStart 50000 - AudioPortCount 1000
```

Para recuperar el nombre del componente de mediación y ver los puertos predeterminados, puede usar el cmdlet [Get-CsService](https://docs.microsoft.com/powershell/module/skype/get-csservice?view=skype-ps) de la siguiente manera:

```powershell
Get-CsService -MediationServer | Select-Object Identity, AudioPortStart, AudioPortCount
```

En la tabla siguiente se muestran los puertos y los intervalos de puertos para habilitar la comunicación entre el componente perimetral de Cloud Connector y el firewall externo. En esta tabla se muestra una recomendación mínima.

En este caso, todo el tráfico de medios a Internet fluirá a través del servidor perimetral en línea de la siguiente manera: punto final de usuario-- Perímetro en \> línea-- \> Perímetro de Cloud Connector:

**Firewall externo: configuración mínima**



|**IP de origen**|**IP de destino**|**Puerto de origen**|**Puerto de destino**|
|:-----|:-----|:-----|:-----|
|Cualquiera  <br/> |Interfaz perimetral externa de Cloud Connector  <br/> |Cualquiera  <br/> |TCP(MTLS) 5061  <br/> |
|Interfaz perimetral externa de Cloud Connector  <br/> |Cualquiera  <br/> |Cualquiera  <br/> |TCP(MTLS) 5061  <br/> |
|Interfaz perimetral externa de Cloud Connector  <br/> |Cualquiera  <br/> |Cualquiera  <br/> |TCP 80  <br/> |
|Interfaz perimetral externa de Cloud Connector  <br/> |Cualquiera  <br/> |Cualquiera  <br/> |UDP 53  <br/> |
|Interfaz perimetral externa de Cloud Connector  <br/> |Cualquiera  <br/> |Cualquiera  <br/> |TCP 53  <br/> |
|Interfaz perimetral externa de Cloud Connector  <br/> |Cualquiera  <br/> |UDP 3478  <br/> |UDP 3478  <br/> |
|Cualquiera  <br/> |Interfaz perimetral externa de Cloud Connector  <br/> |TCP 50.000-59.999  <br/> |TCP 443  <br/> |
|Cualquiera  <br/> |Interfaz perimetral externa de Cloud Connector  <br/> |UDP 3478  <br/> |UDP 3478  <br/> |
|Interfaz perimetral externa de Cloud Connector  <br/> |Cualquiera  <br/> |TCP 50.000-59.999  <br/> |TCP 443  <br/> |

En la siguiente tabla se muestran los puertos y los intervalos de puertos para habilitar la comunicación entre el componente perimetral de Cloud Connector y el firewall externo. En esta tabla se muestra la solución recomendada.

En este caso, todo el tráfico multimedia para el punto final de Internet puede fluir directamente al componente perimetral de Cloud Connector. La ruta de acceso multimedia será Punto de conexión de usuario - \> Perímetro de Cloud Connector.

> [!NOTE]
> Esta solución no funcionará si el punto final del usuario está detrás de una NAT simétrica.

**Firewall externo: configuración recomendada**


|**IP de origen**|**IP de destino**|**Puerto de origen**|**Puerto de destino**|
|:-----|:-----|:-----|:-----|
|Cualquiera  <br/> |Interfaz perimetral externa de Cloud Connector  <br/> |Cualquiera  <br/> |TCP(MTLS) 5061  <br/> |
|Interfaz perimetral externa de Cloud Connector  <br/> |Cualquiera  <br/> |Cualquiera  <br/> |TCP(MTLS) 5061  <br/> |
|Interfaz perimetral externa de Cloud Connector  <br/> |Cualquiera  <br/> |Cualquiera  <br/> |TCP 80  <br/> |
|Interfaz perimetral externa de Cloud Connector  <br/> |Cualquiera  <br/> |Cualquiera  <br/> |UDP 53  <br/> |
|Interfaz perimetral externa de Cloud Connector  <br/> |Cualquiera  <br/> |Cualquiera  <br/> |TCP 53  <br/> |
|Interfaz perimetral externa de Cloud Connector  <br/> |Cualquiera  <br/> |TCP 50.000-59.999  <br/> |Cualquiera  <br/> |
|Interfaz perimetral externa de Cloud Connector  <br/> |Cualquiera  <br/> |UDP 3478; UDP 50.000-59.999  <br/> |Cualquiera  <br/> |
|Cualquiera  <br/> |Interfaz perimetral externa de Cloud Connector  <br/> |Cualquiera  <br/> |TCP 443; TCP 50.000-59.999  <br/> |
|Cualquiera  <br/> |Interfaz perimetral externa de Cloud Connector  <br/> |Cualquiera  <br/> |UDP 3478; UDP 50.000 - 59.999  <br/> |

### <a name="host-internet-connectivity-requirements"></a>Requisitos de conectividad a Internet de host
<a name="BKMB_Ports"> </a>

El equipo host debe ser capaz de llegar a recursos externos para instalar, actualizar y administrar correctamente Cloud Connector. En la tabla siguiente se muestran los destinos y puertos necesarios entre el equipo host y los recursos externos.

|Dirección  <br/> |IP de origen  <br/> |IP de destino  <br/> |Puerto de origen  <br/> |Puerto de destino  <br/> |Protocolo  <br/> |Finalidad  <br/> |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Salida  <br/> |IP de host de Cloud Connector  <br/> |cualquiera  <br/> |cualquiera  <br/> |53  <br/> |TCP/UDP  <br/> |DNS  <br/> |
|Salida  <br/> |IP de host de Cloud Connector  <br/> |cualquiera  <br/> |cualquiera  <br/> |80, 443  <br/> |TCP  <br/> |Lista de revocación de certificados (CRL)  <br/> |
|Salida  <br/> |IP de host de Cloud Connectorr  <br/> |cualquiera  <br/> |cualquiera  <br/> |80, 443  <br/> |TCP  <br/> |Actualización de Cloud Connector  <br/> Skype Empresarial Online  <br/> PowerShell de administración  <br/> Windows Update  <br/> |

Si se necesitan reglas más restrictivas, consulte las siguientes direcciones URL de la lista blanca:

- [Direcciones URL de lista de revocación de](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2) certificados en intervalos de direcciones IP y URL [de Office 365](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US)

- Windows Update: [Cómo configurar un firewall para actualizaciones de software](https://technet.microsoft.com/library/bb693717.aspx)

- PowerShell de administración de Skype Empresarial Online: \* .online.lync.com

    Si necesitas una exclusión de proxy para este destino, deberás agregarla a la lista de omisión de WinHTTP.

- Actualización de Cloud Connector: [Centro de descarga](https://aka.ms/CloudConnectorInstaller) [https://go.microsoft.com](https://go.microsoft.com) y [https://download.microsoft.com](https://download.microsoft.com)

### <a name="dns-name-resolution-for-the-edge-component"></a>Resolución de nombres DNS para el componente perimetral
<a name="BKMB_Ports"> </a>

El componente perimetral debe resolver los nombres externos de los servicios de Microsoft 365 u Office 365 y los nombres internos de otros componentes de Cloud Connector.

Cada componente perimetral es un equipo con varias propiedades con interfaces externas e internas. Cloud Connector implementa servidores DNS en el componente controlador de dominio dentro de la red perimetral. Puede apuntar el servidor perimetral al servidor DNS dentro del perímetro para todas las resoluciones de nombres, pero debe habilitar el servidor DNS de Cloud Connector para resolver nombres externos estableciendo una zona DNS que contenga uno o más registros DNS A para consultas externas que hacen referencia a búsquedas de nombres a otros servidores DNS públicos.

En el archivo .ini, si establece el nombre fqdN de las puertas de enlace desde el mismo espacio de dominio que el dominio SIP, la zona autoritativa para este dominio SIP se creará en el servidor DNS dentro del perímetro. Si el servidor perimetral apunta a este servidor DNS para resolver nombres, edge nunca resolverá el _sipfederationtls.\<yourdomain\> Registro DNS, que es necesario para el flujo de llamadas. En este caso, Microsoft recomienda proporcionar un servidor DNS en la interfaz perimetral externa para resolver las búsquedas de nombres de Internet y cada componente perimetral debe usar un archivo HOST para resolver otros nombres de componentes de Cloud Connector en direcciones IP.

> [!NOTE]
> Por motivos de seguridad, se recomienda no apuntar el servidor DNS de Cloud Connector a los servidores internos del dominio de producción para la resolución de nombres.

### <a name="determine-deployment-parameters"></a>Determinar los parámetros de implementación
<a name="BKMK_SiteParams"> </a>

En primer lugar, debe definir los siguientes parámetros de implementación comunes:


|**Elemento**|**Descripción**|**Notas**|
|:-----|:-----|:-----|
|Dominios SIP  <br/> |Uri de SIP en uso por parte de los usuarios de la empresa. Proporcione todos los dominios SIP a los que prestará servicio esta implementación. Puede tener más de un dominio SIP.  <br/> ||
|Número de sitios RTC  <br/> |El número de sitios RTC que va a implementar.  <br/> ||

Para cada sitio RTC que planee implementar, deberá recopilar la siguiente información antes de comenzar la implementación. Deberá proporcionar esta información al actualizar el archivo CloudConnector.ini archivo.

Al configurar la información de puerta de enlace, recuerde lo siguiente:

- Si solo tiene una puerta de enlace, quite la sección del archivo .ini de la segunda puerta de enlace. Si hay más de dos puertas de enlace, siga el formato existente para agregar nuevas.

- Asegúrese de que la dirección IP y el puerto de las puertas de enlace sean correctos.

- Para admitir ha de nivel de puerta de enlace RTC, mantenga la puerta de enlace secundaria o agregue puertas de enlace adicionales.

(Opcional) Para restringir los números de llamadas salientes, actualice el valor de LocalRoute.



|**Parámetros del sitio**|**Descripción**|**Notas**|
|:-----|:-----|:-----|
|Nombre de dominio de la máquina virtual  <br/> |Nombre de dominio de los componentes internos de Cloud Connector. Este dominio debe ser diferente del dominio de producción. El nombre debe ser el mismo en todos los dispositivos de Cloud Connector.  <br/> Nombre en el archivo .ini: "VirtualMachineDomain"  <br/> |Se prefiere el dominio .local.  <br/> |
|Nombre del controlador de dominio de Cloud Connector  <br/> |Nombre del controlador de dominio.  <br/> Nombre en el archivo .ini: "ServerName"  <br/> |Debe tener 15 caracteres o menos. Escriba solo el nombre Netbios.  <br/> |
|Máscara de ip/subred del controlador de dominio de Cloud Connector  <br/> |Dirección IP del controlador de dominio.  <br/> Nombre en el archivo .ini: "IP"  <br/> ||
|FQDN de servicio de Microsoft 365 u Office 365 Online  <br/> |Debe ser el valor predeterminado en la mayoría de los casos para la instancia internacional de Microsoft 365 u Office 365.  <br/> Nombre en el archivo .ini: "OnlineSipFederationFqdn"  <br/> ||
|SiteName  <br/> |Nombre del sitio de Skype Empresarial; por ejemplo, Seattle.  <br/> Nombre en el archivo .ini: "SiteName"  <br/> Para la versión 1.4.1 y posteriores, el nombre del sitio debe ser diferente para cada sitio y el nombre debe coincidir con el sitio RTC, si existe, definido en Microsoft 365 u Office 365. Tenga en cuenta que los sitios RTC se crearán automáticamente al registrar el primer dispositivo en un sitio.  <br/> ||
|HardwareType  <br/> Versión 1.4.1 y posteriores  <br/> |Tipo de hardware. El valor predeterminado es Normal. También puede establecer en Mínimo.  <br/> ||
|Country Code  <br/> |Código de país para marcado.  <br/> Nombre en el archivo .ini: "CountryCode"  <br/> ||
|Ciudad  <br/> |Ciudad (opcional).  <br/> Nombre en archivo .ini: "Ciudad"  <br/> ||
|Estado  <br/> |Estado (opcional).  <br/> Nombre en archivo .ini: "State"  <br/> ||
|Dirección IP de máquina virtual base  <br/> |La dirección IP de la máquina virtual base temporal que se usará para crear el VHDX para todas las máquinas virtuales de Cloud Connector. Esta DIRECCIÓN IP debe estar en la misma subred de red corporativa perimetral definida en el siguiente paso y requiere acceso a Internet. Asegúrese de definir la puerta de enlace predeterminada corporativa y el DNS enrutable a Internet.  <br/> Nombre en archivo .ini: "BaseVMIP"  <br/> ||
|WSUSServer  <br/> WSUSStatusServer  <br/> Versión 1.4.1 y posteriores  <br/> |La dirección de Windows Server Update Services (WSUS): un servidor de intranet para hospedar actualizaciones de Microsoft Update.  <br/> Puedes dejar en blanco si no se necesita WSUS.  <br/> ||
|Máscara de subred para la red interna  <br/> |Cloud Connector configura una red IP para la comunicación interna entre los componentes de Cloud Connector. El servidor perimetral también debe estar conectado a otra subred que permita la conectividad a Internet.  <br/> Nombre en el archivo .ini: "CorpnetIPPrefixLength" en "Parámetros para un grupo de servidores de red de VM"  <br/> ||
|Máscara de subred para la red externa  <br/> |Para la red externa del componente perimetral.  <br/> Nombre en el archivo .ini: "InternetIPPrefix" en "Parámetros para un grupo de servidores de red de VM"  <br/> ||
|Nombre del modificador para la red interna  <br/> |Nombre del conmutador que se usará para la red interna de Cloud Connector.  <br/> En la mayoría de los casos se puede usar el valor predeterminado sugerido.  <br/> Nombre en el archivo .ini: "CorpnetSwitchName" en "Parámetros para un grupo de servidores de red de VM"  <br/> ||
|Nombre del modificador para la red externa  <br/> |Nombre del conmutador que se usará para la red externa de Cloud Connector.  <br/> En la mayoría de los casos se puede usar el valor predeterminado sugerido.  <br/> Nombre en el archivo .ini: "InternetSwitchName" en "Parámetros para un grupo de servidores de red de VM"  <br/> ||
|Puerta de enlace predeterminada para red interna  <br/> |Esta puerta de enlace debe proporcionar acceso a Internet (Internet también requiere la configuración del servidor DNS) y se configurará en interfaces internas de componentes de Cloud Connector.  <br/> Nombre en el archivo .ini: "CorpnetDefaultGateway" en "Parámetros para un grupo de servidores de red de VM"  <br/> ||
|Puerta de enlace predeterminada para la interfaz externa del componente perimetral  <br/> |Se configurará en la interfaz externa del componente perimetral.  <br/> Nombre en el archivo .ini: "InternetDefaultGateway" en "Parámetros para un grupo de servidores de red de VM"  <br/> ||
|Servidor DNS para red interna  <br/> |Se configurará en la interfaz interna de la máquina virtual temporal. Debe proporcionar la resolución de nombres para los nombres de Internet. Sin proporcionar un servidor DNS, se producirá un error en la conexión a Internet y la implementación no finalizará.  <br/> Nombre en archivo .ini: "CorpnetDNSIPAddress" en "Parámetros para un grupo de servidores de red de VM"  <br/> ||
|Servidor DNS para la interfaz externa del componente perimetral  <br/> |Se configurará en la interfaz externa de Edge.  <br/> Nombre en el archivo .ini: "InternetDNSIPAddress" en "Parámetros para un grupo de servidores de red de VM"  <br/> ||
|Nombre del conmutador de administración  <br/> |El conmutador de administración es un conmutador temporal que se creará automáticamente y que se usará para la configuración de Cloud Connector durante la implementación. Se desconectará automáticamente después de la implementación. Debe ser una subred diferente de cualquier otra red usada en Cloud Connector.  <br/> En la mayoría de los casos se puede usar el valor predeterminado sugerido.  <br/> Nombre en el archivo .ini: "ManagementSwitchName" en "Parámetros para un grupo de servidores de red de VM"  <br/> ||
|Dirección de subred de administración/máscara de subred  <br/> |La subred de administración es una subred temporal que se creará automáticamente y que se usará para la configuración de Cloud Connector durante la implementación. Se quitará automáticamente después de la implementación. Debe ser una subred diferente de cualquier otra red usada en Cloud Connector.  <br/> Nombres en el archivo .ini: "ManagementIPPrefix" y "ManagementIPPrefixLength" en "Parámetros para un grupo de servidores de red de VM"  <br/> ||
|Equipo del Almacén de administración central (CMS)  <br/> |FQDN único usado para el Almacén de administración central (CMS). El nombre de dominio de AD se usará para generar el FQDN.  <br/> Nombre en el archivo .ini: "ServerName" en "Parámetros para el servicio de administración central principal"  <br/> |Debe tener 15 caracteres o menos. Escriba solo el nombre Netbios.  <br/> (Nombre del grupo cms = nombre del servidor)  <br/> |
|Dirección IP del equipo CMS  <br/> |Dirección IP del servidor CMS (interno en la red perimetral).  <br/> Nombre en archivo INI: "IP" en "Parámetros para el servicio de administración central principal"  <br/> ||
|Nombre del recurso compartido de archivos  <br/> |Nombre del recurso compartido de archivos que se creará en el servidor CMS para los datos de replicación de Skype Empresarial (por ejemplo, CmsFileStore).  <br/> En la mayoría de los casos se puede usar el valor predeterminado sugerido.  <br/> Nombre en el archivo .ini: "CmsFileStore" en "Parámetros para el servicio de administración central principal"  <br/> ||
|Nombre del grupo de servidores del componente de mediación  <br/> |Nombre del grupo de servidores del componente de mediación. Escriba solo el nombre Netbios. El nombre de dominio de AD se usará para generar el FQDN.  <br/> Nombre en el archivo .ini: "PoolName" en "Parámetros para un grupo de servidores de mediación"  <br/> |Debe tener 15 caracteres o menos. Escriba solo el nombre Netbios.  <br/> |
|Nombre del componente de mediación  <br/> |Nombre del componente de mediación 1. Escriba solo el nombre Netbios. El nombre de dominio de AD se usará para generar el FQDN.  <br/> Nombre en el archivo .ini: "ServerName" en "Parámetros para un grupo de servidores de mediación"  <br/> |Debe tener 15 caracteres o menos. Escriba solo el nombre Netbios.  <br/> |
|Dirección IP del equipo del componente de mediación  <br/> |IP de red corporativa interna para el componente de mediación (interno en la red perimetral).  <br/> Nombre en archivo .ini: "IP" en "Parámetros para un grupo de servidores de mediación"  <br/> ||
|Nombre interno del grupo de servidores perimetrales  <br/> |Nombre del grupo de servidores del componente perimetral. Escriba solo el nombre Netbios. El nombre de dominio de AD se usará para generar el FQDN.  <br/> Nombre en el archivo .ini: "InternalPoolName" en "Parámetros para un grupo de servidores perimetrales"  <br/> |Debe tener 15 caracteres o menos. Escriba solo el nombre Netbios.  <br/> |
|Nombre interno del servidor perimetral  <br/> |Nombre del componente perimetral. Escriba solo el nombre Netbios. El nombre de dominio de AD se usará para generar el FQDN.  <br/> Nombre en el archivo .ini: "InternalServerName" en "Parámetros para un grupo de servidores perimetrales"  <br/> |Debe tener 15 caracteres o menos. Escriba solo el nombre Netbios.  <br/> |
|IP interna del servidor perimetral  <br/> |IP de red perimetral interna del componente perimetral para comunicarse con otros componentes de Cloud Connector.  <br/> Nombre en el archivo .ini: "InternalServerIPs" en "Parámetros para un grupo de servidores perimetrales"  <br/> ||
|Nombre externo del grupo de servidores de Access  <br/> |Nombre del servidor perimetral de acceso; por ejemplo, AP. Este nombre debe coincidir con el nombre proporcionado para el certificado SSL. Escriba solo el nombre Netbios. El nombre de dominio SIP se usará para generar el FQDN. Se usará un nombre de grupo externo para todos los componentes perimetrales del grupo. Se requiere un grupo de acceso perimetral por cada sitio RTC.  <br/> Nombre en el archivo .ini: "ExternalSIPPoolName" en "Parámetros para un grupo de servidores perimetrales"  <br/> |Debe tener 15 caracteres o menos. Escriba solo el nombre Netbios.  <br/> "sip" está reservado y, por lo tanto, no se puede usar como nombre.  <br/> El nombre fqdN generado debe coincidir con el nombre proporcionado para el certificado SSL.  <br/> |
|IP externa del servidor perimetral de acceso  <br/> |IP externa del componente perimetral: ya sea IP pública si no hay nat disponible o IP traducida (especifique ambas direcciones si están asignadas).  <br/> Nombre en archivo .ini: "ExternalSIPIPs" en "Parámetros para un grupo de servidores perimetrales"  <br/> ||
|Nombre de retransmisión multimedia  <br/> |Nombre del servidor perimetral de retransmisión multimedia de audio y vídeo; por ejemplo, MR. Se usará un nombre de grupo externo para todos los componentes perimetrales de un grupo. Se requiere un grupo de servidores de retransmisión de medios perimetrales por cada sitio RTC.  <br/> Nombre en el archivo .ini: "ExternalMRFQDNPoolName" en "Parámetros para un grupo de servidores perimetrales"  <br/> |Debe tener 15 caracteres o menos. Escriba solo el nombre Netbios.  <br/> |
|IP externa del perímetro de retransmisión multimedia  <br/> |Actualmente solo se admite una IP, por lo que será la misma IP que el servidor perimetral de acceso, ya sea pública o asignada (especifique ambas direcciones si están asignadas). Puede ser la misma dirección que la IP externa del componente perimetral del servidor perimetral de acceso. Tenga en cuenta que si Edge está detrás de NAT, también debe especificar el valor para el siguiente parámetro.  <br/> Nombre en el archivo .ini: "ExternalMRIPs" en "Parámetros para un grupo de servidores perimetrales"  <br/> ||
|IP externa del servidor perimetral de retransmisión multimedia (si el perímetro está detrás de NAT)  <br/> |Si el servidor perimetral está detrás de NAT, también debe especificar la dirección pública del dispositivo NAT.  <br/> Nombre en el archivo .ini: "ExternalMRPublicIPs" en "Parámetros para un grupo de servidores perimetrales"  <br/> ||
|Crear y modelar puerta de enlace de voz 1  <br/> |Especifique la forma y el modelo de la puerta de enlace SBC/Voice. Tenga en cuenta que puede conectar un dispositivo o tronco SIP desde la lista de dispositivos probados en [https://technet.Microsoft.com/UCOIP](https://technet.Microsoft.com/UCOIP) .  <br/> ||
|Make and Model de Voice Gateway 2 (copie esta fila si tiene más de 2 puertas de enlace)  <br/> |Especifique la forma y el modelo de la puerta de enlace de voz. Ten en cuenta que puedes conectar un dispositivo de la lista de dispositivos probados en [https://technet.Microsoft.com/UCOIP](https://technet.Microsoft.com/UCOIP) .  <br/> ||
|Nombre de puerta de enlace de voz 1  <br/> |Se usa para generar el FQDN del equipo con dominio de AD. Obligatorio si se va a usar TLS entre el componente de mediación y la puerta de enlace de voz. Si no tiene previsto usar FQDN (por ejemplo, TLS no es necesario o la puerta de enlace de voz no admite la conexión con FQDN (solo IP)), especifique.  <br/> ||
|Nombre de puerta de enlace de voz 2 (copie esta fila si tiene más de 2 puertas de enlace)  <br/> |Se usa para generar el FQDN del equipo con dominio de AD. Obligatorio si se va a usar TLS entre el componente de mediación y la puerta de enlace de voz. Si no tiene previsto usar FQDN (por ejemplo, TLS no es necesario o la puerta de enlace de voz no admite la conexión con FQDN (solo IP)), especifique.  <br/> ||
|Dirección IP de puerta de enlace de voz 1  <br/> |Dirección IP de la puerta de enlace de voz.  <br/> ||
|Dirección IP de puerta de enlace de voz 2 (copie esta fila si tiene más de 2 puertas de enlace)  <br/> |Dirección IP de la puerta de enlace de voz.  <br/> ||
|Puerto # de puerta de enlace de voz 1 (copie esta fila si tiene más de 2 puertas de enlace)  <br/> |Puerto en el que escuchará el tronco SIP de puerta de enlace de voz, por ejemplo, 5060.  <br/> ||
|Puerto de puerta de enlace de voz 2 #  <br/> |Puerto en el que escuchará el tronco SIP de puerta de enlace de voz, por ejemplo, 5060.  <br/> ||
|Protocolo de puerta de enlace de voz 1 para tráfico SIP  <br/> |TCP o TLS.  <br/> ||
|Protocolo de puerta de enlace de voz 2 para el tráfico SIP (copie esta fila si tiene más de 2 puertas de enlace)  <br/> |TCP o TLS.  <br/> ||
|Intervalo de puertos de medios externos para el tráfico hacia y desde el componente perimetral  <br/> |Intervalo de puertos TCP/UDP para el tráfico multimedia hacia y desde la interfaz externa del perímetro. Siempre debe comenzar desde 50 000. Consulte "Puertos y protocolos" para obtener más información.  <br/> |50000 - 59 999  <br/> |
|Intervalo de puertos multimedia para comunicarse con/desde el componente de mediación a través del firewall interno  <br/> |Intervalo de puertos UDP que el componente de mediación usará para comunicarse con clientes y puertas de enlace (recomendación 4 puertos por llamada).  <br/> ||
|Intervalo de puertos multimedia para comunicarse con el cliente de Skype Empresarial a través de firewall interno  <br/> |Por motivos de planeación, no se puede cambiar. Los puertos deben abrirse en el firewall interno para comunicarse entre los clientes de Skype Empresarial dentro de la red interna y con el componente de mediación.  <br/> |50 000- 50 019  <br/> |
|Contraseña del certificado público  <br/> |Debe proporcionarse en el script.  <br/> ||
|Contraseña de administrador de modo seguro  <br/> Solo la versión 1.4.2  <br/> |Contraseña de administrador de modo seguro para el dominio CC interno.  <br/> ||
|Contraseña de administrador de dominio de Cloud Connector  <br/> Solo la versión 1.4.2  <br/> |Contraseña para administrador de dominio de Cloud Connector (diferente de su dominio de producción). El nombre de usuario es Administrador. No puede cambiar el nombre de usuario.  <br/> ||
|Contraseña de administrador de máquinas virtuales  <br/> Solo la versión 1.4.2  <br/> |Se usa para configurar la red de administración durante la implementación.  <br/> El nombre de usuario es Administrador. No puede cambiar el nombre de usuario.  <br/> ||
|CABackupFile  <br/> Versión 2.0 y posteriores  <br/> |Se usa para guardar el servicio de entidad de certificación del servidor de Active Directory en un archivo al implementar varios dispositivos en un sitio de Cloud Connector. Asegúrese de usar la misma contraseña para todos los dispositivos de un sitio de Cloud Connector con el fin de importar correctamente el archivo de copia de seguridad de ca a un nuevo dispositivo agregado.  <br/> ||
|CCEService  <br/> Versión 2.0 y posteriores  <br/> |Se usa para el servicio de administración de Cloud Connector; necesita acceso al directorio de sitios de Cloud Connector. Asegúrese de usar la misma contraseña para todos los dispositivos de un sitio de Cloud Connector.  <br/> ||
|Administrador de inquilinos de Microsoft 365 u Office 365  <br/> | Cloud Connector usa la cuenta para actualizar y administrar la configuración de inquilino de Cloud Connector: <br/>  Versión 2.0 y posteriores: Credenciales para una cuenta dedicada de Microsoft 365 u Office 365 con derechos de administrador de Skype Empresarial. <br/>  Versiones anteriores a la versión 2.0: Credenciales para una cuenta dedicada de Microsoft 365 u Office 365 con derechos de administrador global de inquilinos. <br/> ||
|Habilitar la compatibilidad con REFER  <br/> |Esto definirá si la compatibilidad con SIP REFER está habilitada o deshabilitada en la configuración del tronco para su IP/PBX. El valor predeterminado es True. Si su puerta de enlace IP/PBX admite REFER, deje esto como True. Si no es así, este valor debe cambiarse a False. Si no está seguro de si la puerta de enlace admite REFER, consulte [Qualified IP-PBXs and Gateways](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways).   <br/> ||
|EnableFastFailoverTimer  <br/> Versión 2.0 y posteriores  <br/> |Con el valor predeterminado "True", si la puerta de enlace no responde a las llamadas salientes en un plazo de 10 segundos, se enrutan a la siguiente puerta de enlace disponible; si no hay troncos adicionales, la llamada se descartará automáticamente.  <br/> Sin embargo, en una organización con redes lentas y respuestas de puerta de enlace, o cuando el proceso de establecimiento de llamadas tarda más de 10 segundos, esto podría provocar la pérdida innecesaria de llamadas.  <br/> Al realizar llamadas a algunos países, por ejemplo Los Emiratos Árabes Unidos o Afganistán, el proceso de establecimiento de llamadas puede tardar más de 10 segundos. Tendrá que cambiar el valor a False si encuentra problemas similares. No olvide cambiar la configuración correspondiente en el SBC o la puerta de enlace conectados.  <br/> El valor puede ser True o False. El valor predeterminado es True.  <br/> ||
|ForwardCallHistory  <br/> Versión 2.0 y posteriores  <br/> | Este parámetro se usa para activar los encabezados SIP que se usan para informar al autor de la llamada inicial en escenarios de llamadas simultáneas, reenvío de llamadas y transferencia de llamadas. Si se establece el parámetro en True, se activarán dos encabezados SIP: <br/>  History-Info <br/>  Referred-By <br/>  El encabezado History-Info se usa para volver a dirigir solicitudes SIP y "proporcionar un mecanismo estándar para capturar la información del historial de solicitudes para habilitar una amplia variedad de servicios para redes y usuarios finales"[(RFC 4244 - Sección 1.1](http://www.ietf.org/rfc/rfc4244.txt)). Para las interfaces troncales de Cloud Connector, esto se usa en escenarios de simultánea y de reenvío de llamadas.  <br/>  El valor puede ser True o False. El valor predeterminado es False. <br/> ||
|Reenviar PAI  <br/> Versión 2.0 y posteriores  <br/> |PAI es una extensión privada para SIP que permite que los servidores SIP aserten la identidad de los usuarios autenticados. Para el proveedor de troncos SIP, PAI puede usarse para facturación en caso de History-Info y Referred-By encabezados no estén presentes. Cuando forward P-Asserted-Identity está habilitado en la configuración, el servidor de mediación reenviará los encabezados PAI con URI de tel SIP desde Cloud Connector al tronco &amp; SIP. El servidor de mediación reenviará los encabezados PAI con los números E.164 de TEL URI SOLO recibidos en el tronco &amp; SIP a Cloud Connector. El servidor de mediación también reenviará los encabezados de privacidad recibidos en cualquier dirección. Si la solicitud SIP enviada por el servidor de mediación incluye un encabezado de privacidad con el formato "Privacidad: id", junto con el encabezado PAI, la identidad afirmada debe mantenerse privada fuera del dominio de confianza de red.  <br/> El valor puede ser True o False. El valor predeterminado es False.  <br/> ||

### <a name="certificate-requirements"></a>Requisitos de certificado
<a name="BKMK_Certs"> </a>

Cada componente perimetral requiere un certificado de una entidad de certificación pública. Los certificados deben tener una clave privada exportable para copiar entre componentes perimetrales. Para cumplir los requisitos de certificado, deberá decidir entre las siguientes opciones y proporcionar el nombre del sujeto (SN) y el nombre alternativo del sujeto (SAN) para el certificado.

 **Si tiene un único dominio SIP:**

- **Opción 1.** El nombre del sujeto debe contener el nombre del grupo que asignó a los componentes perimetrales. Tenga en cuenta que el nombre del sujeto no sip.sipdomain.com porque este nombre está reservado para el componente perimetral de Skype Empresarial en línea. El SAN debe contener el sip.sipdomain.com y el nombre del grupo de servidores perimetrales de acceso:

  ```console
  SN = accessedgepoolnameforsite1.sipdomain.com, SAN = sip.sipdomain.com,
  acessedgepoolnameforsite1.sipdomain.com
  ```

- **Opción 2.** Si desea usar un único certificado comodín en todos los servidores del grupo de servidores perimetrales que implemente, puede usar una entrada de SAN comodín de .sipdomain.com en lugar del nombre del grupo de servidores perimetrales en el \* certificado. El nombre del sujeto puede ser el nombre del grupo de servidores perimetrales de acceso de cualquiera de los grupos de servidores perimetrales que haya implementado:

  ```console
  SN = accessedgepoolnameforsite1.sipdomain.com, SAN = sip.sipdomain.com, SAN = *.sipdomain.com
  ```

> [!NOTE]
> No debe crear una entrada DNS externa para sip. \<sipdomain\> . com porque este nombre pertenece a la implementación de Microsoft 365 u Office 365.

> [!NOTE]
> Si desea usar un único certificado para todos los grupos de servidores perimetrales implementados en su organización y no puede usar un certificado comodín como se define en la opción 2, deberá incluir el FQDN de todos los grupos de servidores perimetrales implementados en el nombre de SAN en el certificado.

 **Si tiene varios dominios SIP:**

Deberá agregar una sip.sipdomain.com para cada dominio SIP y el nombre de los grupos de servidores perimetrales de acceso por dominio (puede ser un grupo físico pero con nombres diferentes). A continuación se muestra un ejemplo de entradas SN y SAN en un escenario de dominio sip múltiple:

- **Opción 1.** El nombre del sujeto debe contener el nombre del grupo que asignó para los componentes perimetrales. Tenga en cuenta que el nombre del sujeto no sip.sipdomain.com porque este nombre está reservado para el componente perimetral de Skype Empresarial en línea. El SAN debe contener el sip.sipdomain.com y el nombre del grupo de servidores perimetrales de acceso:

  ```console
  SN = accessedgepoolnameforsite1.sipdomain1.com, SAN = sip.sipdomain1.com, sip.sipdomain2.com,
  acessedgepoolnameforsite1.sipdomain1.com
  ```

- <strong>Opción 2.</strong> Si desea usar un único certificado comodín en todos los servidores del grupo de servidores perimetrales que implemente, puede usar una entrada de SAN comodín de .sipdomain.com en lugar del nombre del grupo de servidores perimetrales en el \* certificado. El nombre del sujeto puede ser el nombre del grupo de servidores perimetrales de acceso de cualquiera de los grupos de servidores perimetrales que haya implementado:

  ```console
  SN = accessedgepoolnameforsite1.sipdomain.com, SAN = sip.sipdomain1.com, sip.sipdomain2.com,
  SAN = *.sipdomain1.com
  ```

> [!NOTE]
> No debe crear una entrada DNS externa para sip. \<sipdomain\> . com porque este nombre pertenece a la implementación de Microsoft 365 u Office 365.

Para fines de implementación, puede usar la tabla siguiente:

|**Opción**|**Descripción**|**Notas**|
|:-----|:-----|:-----|
|¿Qué opción usará para la implementación?  <br/> |Opción 1 o 2  <br/> ||
|SN  <br/> |Proporcionar el SN para el certificado  <br/> ||
|SAN  <br/> |Proporciona el SAN para su certificado  <br/> ||

Si usa TLS entre la puerta de enlace y el servidor de mediación, deberá obtener el certificado raíz o la cadena de certificados completa para el certificado asignado a la puerta de enlace.

## <a name="dial-plan-considerations"></a>Consideraciones del plan de marcado
<a name="BKMK_DailPlan"> </a>

Cloud Connector requiere el uso de un plan de marcado en línea. Para obtener más información sobre cómo configurar un plan de marcado en línea, consulte [¿Qué son los planes de marcado?](/microsoftteams/what-are-dial-plans) 
  
## <a name="high-availability-considerations"></a>Consideraciones de alta disponibilidad
<a name="BKMK_HA"> </a>

Al implementar Cloud Connector Edition para alta disponibilidad, se implementan al menos dos dispositivos que actúan como copia de seguridad entre sí. Cada dispositivo consta de cuatro componentes: perimetral, mediación, almacén de administración central (CMS) y controlador de dominio.

En general, si un componente de un dispositivo no funciona, Cloud Connector Edition puede seguir controlando las llamadas, pero debe tener en cuenta lo siguiente:

- **Consideraciones de componentes de controlador de dominio, CMS y mediación**

    Supongamos que el componente cms o controlador de dominio de un dispositivo se cae. El dispositivo aún puede controlar las llamadas entrantes y salientes, pero si reinicia un componente de mediación cuando no se puede acceder al controlador de dominio o al componente CMS, la mediación no funcionará. Lo mismo se aplica al reinicio del componente CMS cuando el controlador de dominio está abajo.

    **Recomendación:** Antes de reiniciar los componentes, compruebe la disponibilidad de los demás componentes del dispositivo.

- **Consideraciones sobre componentes perimetrales**

    Si el componente perimetral de un dispositivo no está disponible, el comportamiento de las llamadas entrantes y salientes será diferente del siguiente:

  - **Llamada saliente:** una llamada de su usuario en Internet a una red RTC.

    El mecanismo de distribución de llamadas en la nube identificará que un componente perimetral está caído y enrutará todas las llamadas a otro dispositivo, para que la llamada saliente sea correcta.

  - **Llamada entrante:** una llamada de la red RTC a un usuario que se encuentra en una red local o en Internet.

     Si el componente perimetral del dispositivo que recibió la llamada no funciona, las llamadas entrantes a este dispositivo no se realizarán correctamente porque el componente de mediación no puede redirigir la llamada al componente perimetral en el otro dispositivo.

    **Recomendación:** Tener un sistema de supervisión en su lugar. Después de identificar un mal funcionamiento del componente perimetral, apague todos los componentes del dispositivo donde el componente perimetral no está disponible.

## <a name="cloud-connector-media-flow"></a>Flujo de medios de Cloud Connector
<a name="BKMK_MediaFlow"> </a>

Los diagramas siguientes describen el flujo de una llamada entrante y saliente a través de Cloud Connector Edition. Esta información es útil para comprender cómo se establece la conectividad.

En el primer diagrama, un usuario interno hace una llamada saliente de la siguiente manera:

1. David, un usuario conectado, pero ahora en la red interna, hace una llamada a un usuario RTC externo.

2. Rutas de tráfico SIP a Skype Empresarial Online.

3. Skype Empresarial Online realiza una búsqueda inversa de números del número. Se produce un error en la búsqueda inversa de números porque este número no pertenece a nadie de la organización de Skype Empresarial.

4. La llamada se enruta al componente perimetral (sip y flujo de medios a través del perímetro en línea en primer lugar; Los medios irán al componente de mediación a través del firewall interno).

5. Si la ruta existe, el componente perimetral retransmite el tráfico al componente de mediación de la red perimetral.

6. El componente de mediación envía el tráfico a la puerta de enlace RTC.

![Flujo de medios salientes para Cloud Connector](../../media/c495a2bb-305c-46ef-b16d-b8f9f2b937a8.png)

En el siguiente diagrama, un usuario interno recibe una llamada entrante de la siguiente manera:

1. La puerta de enlace RTC recibe una llamada para el usuario David, que está conectado, pero que ahora está en la red interna.

2. El tráfico SIP se enruta al componente de mediación.

3. El componente de mediación envía tráfico SIP al componente perimetral y, a continuación, va a Skype Empresarial Online.

4. Skype Empresarial Online realiza una búsqueda inversa de números del número y descubre que se trata del usuario David.

5. La señalización SIP va a todos los puntos de presencia de David.

6. El tráfico de medios se establecerá entre la puerta de enlace y el componente de mediación, y entre el componente de mediación y el punto final.

![Flujo de medios entrantes para Cloud Connector](../../media/ba5da6f6-e357-43c6-9e8f-4bfdde97c176.png)

## <a name="monitoring-and-troubleshooting"></a>Supervisión y solución de problemas
<a name="BKMK_Monitor"> </a>

El mecanismo de supervisión y solución de problemas se instala automáticamente con cada dispositivo de Cloud Connector. El mecanismo detecta los siguientes eventos:

- Una o más máquinas virtuales de un dispositivo de Cloud Connector no están conectadas a un conmutador virtual interno o de Internet.

- Una o varias máquinas virtuales de un dispositivo de Cloud Connector están en estado guardado o detenido.

- Servicios que no se están ejecutando.

  Si se detecta uno de los siguientes eventos, todo el dispositivo de Cloud Connector se purga y se marca como sin conexión para evitar el intento de establecer llamadas a un dispositivo que no funciona correctamente. Las características de recuperación automática de Cloud Connector restaurarán posteriormente los servicios y marcarán el dispositivo como en línea. Si se produce un error en la recuperación automática por algún motivo, consulte [Solucionar problemas de la implementación de Cloud Connector.](troubleshoot-your-cloud-connector-deployment.md)

  - En la máquina virtual del Almacén de administración central:

     - Agente replicador maestro de Skype Empresarial

     - Agente del replicador de réplicas de Skype Empresarial

  - En la máquina virtual del servidor de mediación:

     - Agente del replicador de réplicas de Skype Empresarial

     - Mediación de Skype Empresarial Server

  - En la máquina virtual del servidor perimetral

     - Agente del replicador de réplicas de Skype Empresarial

     -  Servidor perimetral de acceso de Skype Empresarial Server

     - Perímetro de audio y vídeo de Skype Empresarial Server

     - Autenticación de audio y vídeo de Skype Empresarial Server

     - Servidor perimetral de conferencia web de Skype Empresarial Server

- Regla de entrada del firewall de Windows para "RTCSRV de CS" en el servidor perimetral, "CS RTCMEDSRV" en el servidor de mediación está deshabilitado.

Cloud Connector 2.1 y versiones posteriores admite la supervisión de Cloud Connector mediante Operations Management Suite (OMS). Para obtener más información, vea [Monitor Cloud Connector using Operations Management Suite (OMS)](monitor-cloud-connector-using-operations-management-suite-oms.md)

## <a name="for-more-information"></a>Más información
<a name="BKMK_MoreInfo"> </a>

Para obtener más información, vea los artículos siguientes: 

- [Soluciones de telefonía de Microsoft](https://docs.microsoft.com/SkypeForBusiness/hybrid/msft-telephony-solutions)

- [Configurar y administrar Skype Empresarial Cloud Connector Edition](configure-skype-for-business-cloud-connector-edition.md)

- [Plan para la omisión de medios en Cloud Connector Edition](plan-for-media-bypass-in-cloud-connector-edition.md)

- [Implementar la omisión de medios en Cloud Connector Edition](deploy-media-bypass-in-cloud-connector.md)


