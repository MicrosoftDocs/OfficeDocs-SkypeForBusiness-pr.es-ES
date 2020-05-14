---
title: Planeación de Skype empresarial en entornos de VDI
author: lanachin
ms.author: v-lanac
ms.reviewer: krishra
manager: serdars
ms.date: 1/9/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ea68414b-bb7e-483a-b731-b6b5a44372b1
description: En este tema se describen las consideraciones de planeación para usar Skype empresarial mientras se conecta a un escritorio virtual remoto.
ms.openlocfilehash: 6886eab8a13db852e0aa86b63d08aa33f82fdaed
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2020
ms.locfileid: "44219530"
---
# <a name="plan-for-skype-for-business-in-vdi-environments"></a>Planeación de Skype empresarial en entornos de VDI
 
En este tema se describen las consideraciones de planeación para usar Skype empresarial mientras se conecta a un escritorio virtual remoto. 
  
Un entorno de infraestructura de escritorio virtual (VDI) se usa en algunas organizaciones donde los problemas de seguridad y cumplimiento son especialmente confidenciales. Sus usuarios realizan su trabajo en un escritorio virtual con todas sus aplicaciones de escritorio y archivos mediante servicios de escritorio remoto o una conexión remota similar. Uso de Skype empresarial con audio y vídeo completos en una conexión como esa requiere una carga pesada de procesamiento de audio y vídeo en el cliente hospedado en un escritorio virtual. Hay disponible software de complemento de VDI adicional que descarga ese procesamiento en el equipo local del usuario final y reduce la carga en el escritorio virtual.
  
Hay tres soluciones disponibles para el componente de complemento VDI, ofrecidas por Microsoft, Citrix o VMWare. Para implementaciones nuevas, Microsoft recomienda usar la soluci? o el paquete de optimización en tiempo real de Citrix HDX o el paquete de virtualización horizonte de VMWare. El complemento de VDI de Lync original todavía es compatible para el resto de su ciclo de vida.
  
- El **complemento Lync VDI** se desarrolló para Lync 2013 y es compatible con el cliente de Lync 2013 o Skype empresarial 2015 que se ejecuta en un escritorio virtual. Se trata de una aplicación independiente que se instala en el equipo local y permite el uso de dispositivos de audio y vídeo locales con un cliente en un escritorio virtual. El complemento no requiere que se instale un cliente de Skype empresarial en el equipo local o en el cliente ligero, que debe ejecutar sistemas operativos Windows 7, Windows 8 o Windows Server 2008. (Los dispositivos de cliente ligero que usan estos sistemas operativos y que son compatibles con Microsoft son: Dell Wyse Z90D7, Dell Wyse R90L7, Dell Wyse X90m7, HP T610 y HP t5740e). Este complemento aún es compatible, pero no se planea ninguna actualización futura. Para los entornos virtuales basados en Citrix, se recomienda Citrix RealTime Optimization Pack.
    
- El **paquete de optimización en tiempo real de Citrix** se basa en el complemento de VDI de Lync y funciona con los clientes de Lync 2013 o Skype empresarial 2016 en un escritorio virtual. Citrix y Microsoft desarrollaron coautores para mejorar el complemento original de VDI. Se puede instalar en clientes con sistemas operativos Windows y que no sean Windows (incluidos Windows 10, Mac y Linux). Consta de dos componentes: el conector en tiempo real (que se instala en el escritorio virtual) y el motor de medios en tiempo real (que se instala en el equipo local del usuario final). Estos dos componentes permiten que el equipo local del usuario Use el cliente de Skype empresarial que se ejecuta en el escritorio virtual con el procesamiento A/V que se ha movido al equipo local. En el caso de los entornos de escritorio virtuales basados en Citrix, se recomienda Citrix RealTime Optimization Pack y se planea más soporte técnico.
    
- El **paquete de virtualización del horizonte de VMware** para Skype empresarial, desarrollado en colaboración con VMware, le permite ofrecer Skype empresarial en un escritorio virtual a la vez que ofrece una excelente experiencia del usuario. La solución funciona aprovechando un motor multimedia en el cliente para crear una solución optimizada, con el punto de conexión de cliente que proporciona capacidades de descarga de medios para las llamadas de audio y vídeo. Esta solución puede proporcionar audio y vídeo directamente entre los puntos de conexión para colaborar uno a uno o descargarlo en una unidad de control multipunto (MCU) central para las llamadas de conferencia entre varias partes o las reuniones.
    
> [!NOTE]
> Los clientes de Skype empresarial Basic no son compatibles con el paquete de optimización en tiempo real de Citrix HDX o el paquete de virtualización del horizonte de VMWare. 
  
## <a name="citrix-hdx-realtime-optimization-pack"></a>Paquete de optimización en tiempo real de Citrix HDX
<a name="Citrix_RT"> </a>

El complemento de entorno de VDI de Citrix (una característica de XenApp y XenDesktop) es compatible con Lync 2013 y Skype empresarial 2015 y 2016 (clientes completos que usan los clientes de cualquier clic para ejecutar el instalador, o los instaladores de MSI publicados después de enero de 2017 PU), instalados en un escritorio virtual. Su funcionamiento general se basa en el complemento Microsoft Lync VDI, pero funciona en una variedad más amplia de sistemas operativos cliente, incluidos Windows 10, Macintosh y Linux.
  
Puede encontrar una lista completa de las características y tecnologías admitidas en el sitio web de Citrix en [proporcionar Microsoft Skype empresarial a los usuarios de XenApp y XenDesktop](https://www.citrix.com/content/dam/citrix/en_us/documents/products-solutions/delivering-microsoft-lync-to-xenapp-and-xendesktop-users.pdf).
  
Revise los siguientes vínculos para obtener más información:
  
- Citrix [HDX Realtime Optimization Pack 2,1](https://docs.citrix.com/en-us/hdx-optimization/2-1.mdl)
    
- [Introducción técnica](https://docs.citrix.com/en-us/hdx-optimization/2-1/about.mdl)
    
- [Compatibilidad con características de Skype empresarial CTX200279](https://support.citrix.com/article/CTX200279)
    
## <a name="vmware-horizon-virtualization-pack"></a>Paquete de virtualización del horizonte de VMWare
<a name="Citrix_RT"> </a>

La solución de entorno de VMWare VDI es compatible con los clientes de Skype empresarial 2015 y 2016 completos instalados en un escritorio virtual. Su funcionamiento general se basa en el complemento Microsoft Lync VDI, pero funciona en una variedad más amplia de sistemas operativos cliente, incluidos Windows 10, Macintosh y Linux. 
  
Puede encontrar una descripción completa de las características y tecnologías compatibles en el sitio web de VMWare en los siguientes vínculos:
  
- [What's New in VMware horizonte 7,4 cliente de horizonte de horizonte &amp; 4,7](https://blogs.vmware.com/euc/2018/01/vmware-horizon-7-4-horizon-client-4-7-whats-new.mdl)
    
- [Paquete de virtualización del horizonte para Skype empresarial](https://www.vmware.com/products/horizon/skype-for-business.mdl)
    
- [Microsoft Skype empresarial con horizonte de VMWare](https://www.vmware.com/content/dam/digitalmarketing/vmware/en/pdf/products/horizon/vmware-skype-for-business-solution-brief.pdf)
    
## <a name="microsofts-lync-vdi-plug-in"></a>Complemento Microsoft VDI para Lync
<a name="Citrix_RT"> </a>

Con la solución de complemento Microsoft Lync VDI, el usuario tiene que estar en un equipo con Windows o en un cliente ligero y tener instalado Microsoft Lync VDI plugin para controlar las secuencias de audio y vídeo desde el cliente en el escritorio virtual. Un usuario hará lo siguiente:
  
1. Conecte un dispositivo de audio o vídeo (como un auricular o una cámara) a un equipo local.
    
2. Conéctese a un escritorio virtual remoto con un cliente de Lync 2013 o Skype empresarial 2015.
    
3. Escriba las credenciales de Skype empresarial en el escritorio virtual.
    
4. Vuelva a escribir las credenciales de usuario para establecer una conexión con el complemento de VDI de Lync en el equipo local con Windows o el cliente ligero.
    
Una vez establecida una conexión, el usuario está listo para realizar y recibir llamadas de audio y vídeo. El tráfico en la red y la carga en el escritorio virtual se minimizan, ya que el equipo local administra el procesamiento de audio y vídeo.
  
El complemento Microsoft Lync VDI solo se admite en determinados sistemas operativos de Windows y solo admite clientes de Lync 2013 o Skype empresarial 2015. Consulte [tecnologías de virtualización admitidas y limitaciones conocidas](vdi-environments.md#Supported_virt) para obtener más información sobre las tecnologías y limitaciones compatibles.
  
Revise los siguientes vínculos para obtener más información:
  
- [Tecnologías de virtualización admitidas y limitaciones conocidas](vdi-environments.md#Supported_virt)
    
- [Requisitos previos del complemento Lync VDI](vdi-environments.md#VDI_prereq)
    
- [Implementar el complemento Lync VDI con Skype empresarial Server](../../deploy/deploy-clients/deploy-the-lync-vdi-plug-in.md)
    
- Artículo [CTX138408](https://support.citrix.com/article/CTX138408) de Citrix Knowledge Center
    
El complemento Microsoft VDI está disponible en el complemento [Microsoft Lync vdi 2013 (32 bits)](https://www.microsoft.com/download/details.aspx?id=35457) o [microsoft Lync vdi 2013 (64 bits)](https://www.microsoft.com/download/details.aspx?id=35454). Este complemento es compatible con el cliente de Skype empresarial 2015, a pesar del nombre.
  
### <a name="supported-virtualization-technologies-and-known-limitations"></a>Tecnologías de virtualización admitidas y limitaciones conocidas
<a name="Supported_virt"> </a>

El complemento de VDI de Lync permite llamadas de audio y vídeo para tecnologías de virtualización compatibles. De acuerdo con las regulaciones telefónicas estándar, también se incluye compatibilidad con E911. En las siguientes secciones se describen las tecnologías de virtualización que son compatibles con el complemento VDI de Lync y las limitaciones de características conocidas.
  
#### <a name="support-for-virtualization-technologies"></a>Compatibilidad con tecnologías de virtualización

El complemento Lync VDI admite sesiones remotas de escritorio completas en el escenario de escritorio virtual personal, pero no en el escenario de sesión de escritorio remoto. Estos escenarios se pueden describir de la siguiente manera:
  
- **Se admite: escritorios virtuales personalizados o infraestructura de escritorio virtual (VDI).** En este escenario, cada usuario inicia sesión en un escritorio virtual personalizable y puede guardar archivos en el escritorio que se conservan entre sesiones. Los servicios de escritorio remoto de Microsoft y la vista del horizonte de VMware son implementaciones de ejemplo que se han probado para su uso con Skype empresarial 2015. Otras implementaciones sometidas a validación incluyen Citrix XenDesktop. Para obtener información sobre entornos VDI específicos del proveedor y hardware de cliente que han sido probados por Microsoft, consulte [infraestructura apta para Microsoft Lync](https://go.microsoft.com/fwlink/?LinkID=313435).
    
- **No admitido: sesiones de escritorio remoto.** En este escenario, cada usuario inicia sesión en una sesión de escritorio virtual genérica que no se puede personalizar. Algunos ejemplos son las sesiones de escritorio remoto de Microsoft (RDSH) y Citrix XenApp junto con el receptor Citrix.
    
El complemento de VDI de Lync no admite otras tecnologías de virtualización, como la virtualización de aplicaciones, que permite el uso de una aplicación sin necesidad de instalar la aplicación completa de forma local. Las implementaciones de ejemplo incluyen Citrix XenApp y Microsoft Application Virtualization (App-V). No se admiten la transmisión por secuencias de aplicaciones, la comunicación remota de aplicaciones y los modos mixtos de virtualización (por ejemplo, el acceso remoto de aplicaciones en el entorno remoto de escritorio completo).
  
El complemento Lync VDI se diseñó para usar las API independientes de la plataforma, denominadas canales virtuales dinámicos (DVC). Para escenarios que no se admiten de forma explícita, consulte las instrucciones de compatibilidad del proveedor de la solución de VDI.
  
#### <a name="lync-vdi-plug-in-prerequisites"></a>Requisitos previos del complemento Lync VDI
<a name="VDI_prereq"> </a>

En un entorno de VDI, las máquinas virtuales y el equipo local del usuario deben cumplir los requisitos descritos en esta sección.
  
> [!NOTE]
>  El proveedor de soluciones de virtualización puede proporcionar detalles sobre cómo instalar e implementar su entorno. Para obtener información general acerca de la implementación de un entorno virtualizado basado en Hyper-V y servicios de escritorio remoto, vea los siguientes artículos en la biblioteca de Microsoft: [Hyper-v](https://go.microsoft.com/fwlink/p/?linkid=247514), [servicios de escritorio remoto en Windows Server 2008 R2](https://go.microsoft.com/fwlink/p/?linkid=247513) 
  
Las máquinas virtuales deben configurarse con Windows 8, Windows 7 o Windows Server 2008 R2 con los últimos Service Packs.
  
El equipo local del usuario debe cumplir con los siguientes requisitos:
  
- El usuario debe estar alojado en Skype empresarial Server o Lync Server 2013.
    
- El equipo local debe ejecutar Windows Embedded Standard 7 con SP1, Windows 7 con SP1 o Windows 8.
    
- Si está usando los servicios de escritorio remoto, elija el complemento de VDI de Lync de 32 bits o 64 bits para que se ajuste al sistema operativo del equipo local. No es necesario que el equipo local y la máquina virtual tengan sistemas operativos de 32 o 64 bits. Si está usando otra solución o plataforma de virtualización, consulte los requisitos del proveedor.
    
- El equipo local debe ejecutar la [última versión del cliente de escritorio remoto](https://go.microsoft.com/fwlink/p/?LinkId=268032). Instale las últimas actualizaciones de cliente de los servicios de escritorio remoto de Microsoft o el último software cliente de escritorio remoto del proveedor de soluciones de virtualización. 
    
- En el PC local, configure el cliente de escritorio remoto para que el audio se reproduzca en el PC local y que la grabación remota esté deshabilitada. Para configurar estas opciones para conexión a escritorio remoto en Windows, consulte la sección siguiente, "para configurar las opciones de conexión a escritorio remoto". 
    
El complemento Microsoft VDI está disponible en el complemento [Microsoft Lync vdi 2013 (32 bits)](https://www.microsoft.com/download/details.aspx?id=35457) o [microsoft Lync vdi 2013 (64 bits)](https://www.microsoft.com/download/details.aspx?id=35454).
  
#### <a name="known-feature-limitations"></a>Limitaciones de las características conocidas
<a name="VDI_prereq"> </a>

A continuación se indican las limitaciones conocidas al usar el cliente de Skype empresarial 2015 en un entorno de VDI:
  
La delegación de llamadas y las características de anonymization del agente de grupo de respuesta tienen compatibilidad limitada.
  
No se admiten estas características:
  
- Las páginas de ajuste del dispositivo de audio y de vídeo integrados.
    
- Vídeo de varias vistas.
    
- La grabación de las conversaciones.
    
- Unirse a reuniones de forma anónima (es decir, unirse a reuniones de Skype empresarial hospedadas por una organización que no se federe con la organización).
    
- Usar el complemento de VDI de Lync junto con un dispositivo de Lync Phone Edition.
    
- La continuación de llamadas en caso de una interrupción de la red.
    
- Tonos personalizados y características de música en espera.
    
El complemento de VDI para Lync no es compatible con los entornos Microsoft 365 o Office 365.
  
> [!NOTE]
> El paquete de optimización en tiempo real de Citrix no es compatible con Microsoft 365 y Office 365. Para los entornos virtuales basados en Citrix, revise la documentación de [información general técnica](https://docs.citrix.com/en-us/hdx-optimization/2-0/hdx-realtime-optimization-pack-about.mdl) de Citrix para obtener una lista de las características y versiones compatibles.
  
## <a name="see-also"></a>Vea también
<a name="Citrix_RT"> </a>

[Implementar el complemento Lync VDI con Skype empresarial Server](../../deploy/deploy-clients/deploy-the-lync-vdi-plug-in.md)

