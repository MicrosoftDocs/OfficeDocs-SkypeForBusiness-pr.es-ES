---
title: Planificar Skype Empresarial en entornos de VDI
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 1/9/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: Strat_SB_Admin
ms.assetid: ea68414b-bb7e-483a-b731-b6b5a44372b1
description: Este tema describen consideraciones de diseño para utilizar Skype para el negocio al conectarse a un escritorio virtual remoto.
ms.openlocfilehash: facf154940b7a82ddc41ac07b87a8af1a5313f5e
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="plan-for-skype-for-business-in-vdi-environments"></a>Planificar Skype Empresarial en entornos de VDI
 
Este tema describen consideraciones de diseño para utilizar Skype para el negocio al conectarse a un escritorio virtual remoto. 
  
El entorno de Infraestructura de escritorio virtual (VDI) se utiliza en algunas organizaciones donde los problemas de seguridad y cumplimiento son especialmente delicados. Sus usuarios trabajan en un escritorio virtual, y todos sus archivos y aplicaciones de escritorio usan los Servicios de Escritorio remoto o una conexión similar. Mediante Skype para negocios con completa de audio y vídeo en una conexión que requieren cargas pesadas de audio y vídeo de procesamiento en el cliente que se encuentran en un escritorio virtual. Hay software de complemento adicional de VDI que descarga ese proceso en el equipo local del usuario final y reduce la carga en el escritorio virtual.
  
Existen tres soluciones para el componente de complemento de VDI, ofrecido por Microsoft, Citrix o VMWare. Para implementaciones nuevas, Microsoft recomienda utilizar la solución de Citrix HDX RealTime Optimization Pack o el paquete de virtualización de VMWare Horizon. El complemento de VDI Lync original sigue siendo compatible con el resto de su ciclo de vida.
  
- El **Plug-in de Lync VDI** se desarrolló para 2013 de Lync y es compatible con el de 2013 Lync o Skype para cliente de negocios 2015 ejecutándose en un escritorio virtual. Es una aplicación independiente que se instala en el equipo local y permite usar dispositivos de audio y vídeo locales con un cliente en un escritorio virtual. El complemento no requiere un Skype para Business client esté instalado en el equipo local o cliente ligero, que debe ejecutar sistemas operativos Windows 7, Windows 8 o Windows Server 2008. (Los dispositivos thin client utiliza estos sistemas operativos y compatibles con Microsoft incluyen: Dell Wyse Z90D7, Wyse R90L7 de Dell, Dell Wyse X90m7, t610 de HP y HP t5740e.) Este complemento se sigue admitiendo, pero no se planifican actualizaciones futuras. Para los entornos virtuales basados en Citrix, se recomienda Citrix RealTime Optimization Pack.
    
- El **Paquete de optimización de Citrix en tiempo real** se basa en el complemento de VDI Lync y funciona con Lync 2013 o Skype para clientes empresariales 2016 en un escritorio virtual. Se desarrolló de manera conjunta entre Citrix y Microsoft para mejorar a partir del complemento de VDI original. Puede instalarse en clientes con sistemas operativos Windows y distintos de Windows (incluidos Windows 10, Mac y Linux). Consta de dos componentes: el conector en tiempo real (que se instala en el escritorio virtual) y el motor de los medios de comunicación en tiempo real (que se instala en el equipo local del usuario final). Estos dos componentes permiten el equipo del usuario local utilizar el Skype para Business client que se ejecutan en el escritorio virtual con la letra A y procesamiento de V se movió al equipo local. Para los entornos de escritorio virtual basados en Citrix, se recomienda Citrix RealTime Optimization Pack y se prevé proporcionar mayor compatibilidad en el futuro.
    
- El **Pack de virtualización de VMWare horizonte** de Skype para el negocio, desarrollado en colaboración con VMWare, le permite ofrecer Skype para el negocio en un escritorio virtual al tiempo que ofrece una gran experiencia de usuario. Capacidades para llamadas de audio y vídeo de descarga de las obras de solución al aprovechar un motor de multimedia en el cliente para crear una solución optimizada, con el extremo de cliente proporcionando los medios de comunicación. Esta solución que puede ofrecer audio y vídeo, bien directamente entre los extremos de colaboración uno a uno, o descargar a una central Control unidad multipunto (MCU) para llamadas de conferencia con varios participantes o reuniones.
    
> [!NOTE]
> No se admiten el Skype para 2015 básica de negocios o clientes de 2016 con Citrix HDX RealTime Optimization Pack o el paquete de virtualización de VMWare Horizon. 
  
## <a name="citrix-hdx-realtime-optimization-pack"></a>Citrix HDX RealTime Optimization Pack
<a name="Citrix_RT"> </a>

Plugin de entorno de Citrix VDI (una característica de XenApp y XenDesktop) es compatible con 2013 de Lync y Skype para negocios 2015 y 2016 clientes (clientes completa mediante cualquier clic para ejecutar el instalador o instaladores de MSI que se publicaron con posterioridad a enero de 2017 PU) instalados en un virtual ordenador de sobremesa. Su funcionamiento global se basa en el complemento de Microsoft Lync VDI, pero funciona en una mayor variedad de sistemas operativos, incluidos Windows 10, Macintosh y Linux.
  
Encontrará una lista completa de características y tecnologías admitidas en el sitio Web de Citrix en [Ofrecer Microsoft Skype para negocio XenApp y XenDesktop usuarios](https://www.citrix.com/content/dam/citrix/en_us/documents/products-solutions/delivering-microsoft-lync-to-xenapp-and-xendesktop-users.pdf).
  
Consulte los siguientes vínculos para obtener más información:
  
- Citrix [HDX RealTime Optimization Pack 2.1](https://docs.citrix.com/en-us/hdx-optimization/2-1.mdl)
    
- [Introducción técnica](https://docs.citrix.com/en-us/hdx-optimization/2-1/about.mdl)
    
- [CTX200279 Skype para compatibilidad con la función de negocio](https://support.citrix.com/article/CTX200279)
    
## <a name="vmware-horizon-virtualization-pack"></a>Pack de virtualización de VMWare horizonte
<a name="Citrix_RT"> </a>

Solución para entornos de VMWare VDI es compatible con Skype para negocios 2015 y 2016 clientes completos instalados en un escritorio virtual. Su funcionamiento global se basa en el complemento de Microsoft Lync VDI, pero funciona en una mayor variedad de sistemas operativos, incluidos Windows 10, Macintosh y Linux. 
  
Encontrará una explicación completa de las características y tecnologías admitidas en el sitio Web de VMWare en los siguientes vínculos:
  
- [Novedades de VMware Horizon 7.4 &amp; horizonte cliente 4.7](https://blogs.vmware.com/euc/2018/01/vmware-horizon-7-4-horizon-client-4-7-whats-new.mdl)
    
- [Pack de virtualización horizonte de Skype para empresas](https://www.vmware.com/products/horizon/skype-for-business.mdl)
    
- [Skype de Microsoft para el negocio con el horizonte de VMWare](https://www.vmware.com/content/dam/digitalmarketing/vmware/en/pdf/products/horizon/vmware-skype-for-business-solution-brief.pdf)
    
## <a name="microsofts-lync-vdi-plug-in"></a>Complemento Lync VDI de Microsoft
<a name="Citrix_RT"> </a>

Con la solución de complemento de Microsoft Lync VDI, el usuario debe estar en un equipo con Windows o cliente ligero y tener el plugin de Lync VDI de Microsoft instalado para controlar secuencias de audio y vídeo en el cliente de escritorio virtual. Los usuarios harán lo siguiente:
  
1. Conectar el dispositivo de audio o vídeo (como un auricular o una cámara) con un equipo local.
    
2. Conectarse a un escritorio virtual remoto con Lync 2013 o Skype para cliente de negocios 2015.
    
3. Especifique credenciales de Skype para el negocio en el escritorio virtual.
    
4. Vuelva a escribir las credenciales de usuario para establecer una conexión con el complemento en el equipo local de Windows o un cliente ligero de VDI de Lync.
    
Una vez establecida una conexión, el usuario está listo para realizar y recibir llamadas de audio y vídeo. El tráfico en la red y la carga en el escritorio virtual se ven minimizados, dado que el equipo local administra el procesamiento de audio y vídeo.
  
Lync VDI de Microsoft complemento sólo se admite en determinados sistemas operativos de Windows y sólo admite 2013 Lync o Skype para clientes de negocios 2015. Consulte [Tecnologías de virtualización compatibles y limitaciones conocidas](vdi-environments.md#Supported_virt) para obtener más información sobre las tecnologías admitidas y las limitaciones.
  
Consulte los siguientes vínculos para obtener más información:
  
- [Tecnologías de virtualización admitidas y limitaciones comunes](vdi-environments.md#Supported_virt)
    
- [Requisitos previos del complemento Lync VDI](vdi-environments.md#VDI_prereq)
    
- [Implementar la VDI Lync complemento con Skype para Business Server 2015](../../deploy/deploy-clients/deploy-the-lync-vdi-plug-in.md)
    
- Artículo del centro de conocimientos de Citrix [CTX138408](https://support.citrix.com/article/CTX138408)
    
El complemento VDI de Microsoft está disponible en el [complemento de VDI de Microsoft Lync 2013 (32 bits)](https://www.microsoft.com/en-us/download/details.aspx?id=35457) o [complemento de VDI de Microsoft Lync 2013 (64 bits)](https://www.microsoft.com/en-us/download/details.aspx?id=35454). Este plugin es compatible con el Skype para cliente de negocios 2015, a pesar del nombre.
  
### <a name="supported-virtualization-technologies-and-known-limitations"></a>Tecnologías de virtualización admitidas y limitaciones comunes
<a name="Supported_virt"> </a>

La VDI Lync Plug-in permite audio y vídeo de llamada para las tecnologías de virtualización compatibles. Conforme a las normativas estándar para teléfonos, también se incluye compatibilidad con E911. Las secciones siguientes describen las tecnologías de virtualización que son compatibles con el complemento de VDI de Lync y las limitaciones de características conocidas.
  
#### <a name="support-for-virtualization-technologies"></a>Soporte de tecnologías de virtualización

La VDI Lync complemento admite sesiones remotas escritorio completo en el escenario de escritorio virtual personal, pero no en el escenario de sesión de escritorio remoto. Estos entornos pueden describirse así:
  
- **Admitido: escritorios virtuales personalizados o infraestructura de escritorio virtual (VDI).** En esta situación, cada usuario inicia sesión en un escritorio virtual personalizable y puede guardar archivos en el escritorio, que se conservan entre sesiones. Servicios de escritorio remoto de Microsoft y VMware Horizon vista son ejemplos de implementaciones que se han probado para su uso con Skype para negocios 2015. Otras implementaciones en etapa de validación incluyen Citrix XenDesktop. Para obtener información acerca de los entornos VDI específicos del proveedor y hardware de cliente que han sido probados por Microsoft, vea [infraestructura calificados para Microsoft Lync](https://go.microsoft.com/fwlink/?LinkID=313435).
    
- **No admitido: sesiones de Escritorio remoto.** En esta situación, cada usuario inicia sesión en una sesión de escritorio virtual genérica que no puede personalizarse. Algunos ejemplos son las sesiones de escritorio remoto (RDSH) de Microsoft y Citrix XenApp combinado con Citrix Receiver.
    
La VDI Lync complemento es incompatible con otras tecnologías de virtualización, como application virtualization, que permite el uso de una aplicación sin necesidad de instalar localmente la aplicación completa. Algunos ejemplos de implementaciones son Citrix XenApp y Microsoft Application Virtualization (App-V). El streaming de aplicaciones, la comunicación remota de aplicaciones y los modos mixtos de virtualización (por ejemplo, la comunicación remota de aplicaciones en la comunicación remota de escritorio completa) no se admiten.
  
La VDI Lync complemento se diseñó para utilizar API de plataforma independiente denominado canales dinámicos de Virtual (DVCs). En el caso de entornos que no se admiten de forma explícita, consulte las instrucciones de compatibilidad del proveedor de la solución de VDI.
  
#### <a name="lync-vdi-plug-in-prerequisites"></a>Requisitos previos del componente de VDI de Lync
<a name="VDI_prereq"> </a>

En un entorno VDI, las máquinas virtuales y el equipo del usuario local deben cumplir los requisitos descritos en esta sección.
  
> [!NOTE]
>  Su proveedor de soluciones de virtualización puede brindarle información sobre la instalación y la implementación del entorno. Para obtener información general acerca de cómo implementar un entorno virtualizado basado en Hyper-V y los servicios de escritorio remoto, consulte los artículos siguientes en Microsoft TechNet Library: [Hyper-V](https://go.microsoft.com/fwlink/p/?linkid=247514), [Servicios de escritorio remoto en Windows Server 2008 R2](https://go.microsoft.com/fwlink/p/?linkid=247513) 
  
Máquinas virtuales debe configurarse con Windows 8, Windows 7 o Windows Server 2008 R2 con el service Pack más recientes.
  
El equipo del usuario local debe cumplir los siguientes requisitos:
  
- El usuario debe ser alojado en Skype para Business Server 2015 o Lync Server 2013.
    
- El equipo local debe ejecutar Windows Embedded estándar 7 con SP1, Windows 7 con SP1 o Windows 8.
    
- Si utiliza servicios de escritorio remoto, elija el 32 bits o 64 bits Lync VDI Plug-in para que coincida con el sistema operativo del equipo local. No se requiere que tanto el equipo local como la máquina virtual tengan sistemas operativos de 32 o 64 bits. Si utiliza otra solución o plataforma de virtualización, consulte los requisitos de su proveedor.
    
- El equipo local debe estar ejecutando la [versión más reciente del cliente de escritorio remoto](https://go.microsoft.com/fwlink/p/?LinkId=268032). Instale las últimas actualizaciones del cliente de los Servicios de Escritorio remoto de Microsoft o el último software de cliente de escritorio remoto del proveedor de soluciones de virtualización. 
    
- En el equipo local, configure el cliente de escritorio remoto para que el audio se reproduzca en el equipo local y la grabación remota esté deshabilitada. Para configurar estas opciones de conexión a Escritorio remoto en Windows, consulte la sección siguiente, "para"configurar las opciones de conexión a Escritorio remoto. 
    
El complemento VDI de Microsoft está disponible en el [complemento de VDI de Microsoft Lync 2013 (32 bits)](https://www.microsoft.com/en-us/download/details.aspx?id=35457) o [complemento de VDI de Microsoft Lync 2013 (64 bits)](https://www.microsoft.com/en-us/download/details.aspx?id=35454).
  
#### <a name="known-feature-limitations"></a>Limitaciones comunes de la funciones
<a name="VDI_prereq"> </a>

Los siguientes son conocidos limitaciones cuando se utiliza el Skype para cliente de 2015 de negocio en un entorno VDI:
  
Hay compatibilidad limitada para las características de delegación de llamar y Anonymization de agente del grupo de respuesta.
  
No se admiten estas características:
  
- Las páginas de ajuste del dispositivo de audio y de vídeo integrados.
    
- El vídeo de múltiples vistas.
    
- La grabación de las conversaciones.
    
- Unirse a reuniones de forma anónima (es decir, unirse a Skype para reuniones de negocios alojadas por una organización que no federarse con su organización).
    
- Usando el complemento junto con un dispositivo de Lync Phone Edition de VDI de Lync.
    
- La continuación de llamadas en caso de una interrupción de la red.
    
- Las características de tonos de llamada personalizados y de música en espera.
    
La VDI Lync Plug-in no se admite en un entorno de Office 365.
  
> [!NOTE]
> Citrix RealTime Optimization Pack admite Office 365. Para entornos virtuales basados en Citrix, revise la documentación de [Introducción técnica](https://docs.citrix.com/en-us/hdx-optimization/2-0/hdx-realtime-optimization-pack-about.mdl) de Citrix para la lista de versiones y características compatibles.
  
## <a name="see-also"></a>Vea también
<a name="Citrix_RT"> </a>

[Implementar la VDI Lync complemento con Skype para Business Server 2015](../../deploy/deploy-clients/deploy-the-lync-vdi-plug-in.md)

