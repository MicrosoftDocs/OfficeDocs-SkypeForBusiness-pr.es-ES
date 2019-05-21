---
title: Planificar Skype Empresarial en entornos de VDI
author: lanachin
ms.author: v-lanac
ms.reviewer: krishra
manager: serdars
ms.date: 1/9/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ea68414b-bb7e-483a-b731-b6b5a44372b1
description: En este tema se describen las consideraciones de planeación para el uso de Skype empresarial mientras se conecta a un escritorio virtual remoto.
ms.openlocfilehash: 958c13821eea46be91d51d7399722d2af433ccf0
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34277289"
---
# <a name="plan-for-skype-for-business-in-vdi-environments"></a>Planificar Skype Empresarial en entornos de VDI
 
En este tema se describen las consideraciones de planeación para el uso de Skype empresarial mientras se conecta a un escritorio virtual remoto. 
  
El entorno de Infraestructura de escritorio virtual (VDI) se utiliza en algunas organizaciones donde los problemas de seguridad y cumplimiento son especialmente delicados. Sus usuarios trabajan en un escritorio virtual, y todos sus archivos y aplicaciones de escritorio usan los Servicios de Escritorio remoto o una conexión similar. Usar Skype empresarial con audio y vídeo completos en una conexión como esta requiere fuertes cargas de procesamiento de audio y vídeo en el cliente alojado en un escritorio virtual. Hay software complementario VDI disponible que descarga ese procesamiento en la máquina local del usuario final y reduce la carga en el escritorio virtual.
  
Existen tres soluciones disponibles para el componente de complemento VDI, ofrecido por Microsoft, Citrix o VMWare. Para implementaciones nuevas, Microsoft recomienda usar la solución del paquete de optimización en tiempo real de Citrix HDX o el paquete de virtualización horizonte de VMWare. El complemento de VDI original de Lync aún es compatible durante el resto de su ciclo de vida.
  
- El **complemento VDI para Lync** se desarrolló para Lync 2013 y es compatible con el cliente de Lync 2013 o Skype empresarial 2015 que se ejecuta en un escritorio virtual. It's a stand-alone application that installs on the local computer and allows the use of local audio and video devices with a client on a virtual desktop. El complemento no requiere que se instale un cliente de Skype empresarial en el equipo local o en el cliente ligero, que debe ejecutar sistemas operativos Windows 7, Windows 8 o Windows Server 2008. (Los dispositivos de cliente ligero que usan estos sistemas operativos y son admitidos por Microsoft son: Dell Wyse Z90D7, Dell Wyse R90L7, Dell Wyse X90m7, HP T610 y HP t5740e). Este complemento aún se admite, pero no se han previsto actualizaciones futuras. For Citrix-based virtual environments, the Citrix RealTime Optimization Pack is recommended.
    
- El **paquete de optimización en tiempo real de Citrix** se basa en el complemento VDI de Lync y funciona con los clientes de Lync 2013 o Skype empresarial 2016 en un escritorio virtual. Se desarrolló de manera conjunta entre Citrix y Microsoft para mejorar a partir del complemento de VDI original. Puede instalarse en clientes con sistemas operativos Windows y distintos de Windows (incluidos Windows 10, Mac y Linux). Consta de dos componentes: el conector en tiempo real (que está instalado en el escritorio virtual) y el motor de medios en tiempo real (que está instalado en el equipo local del usuario final). Estos dos componentes permiten que el equipo local del usuario Use el cliente de Skype empresarial que se ejecuta en el escritorio virtual con el procesamiento de A/V que se ha movido al equipo local. Para los entornos de escritorio virtual basados en Citrix, se recomienda Citrix RealTime Optimization Pack y se prevé proporcionar mayor compatibilidad en el futuro.
    
- El **paquete** de virtualización del horizonte de VMware para Skype empresarial, desarrollado en colaboración con VMware, le permite ofrecer Skype empresarial en un escritorio virtual mientras ofrece una excelente experiencia para el usuario. La solución funciona aprovechando un motor multimedia en el cliente para crear una solución optimizada, con el punto final del cliente que proporciona capacidades de descarga de medios para las llamadas de audio y vídeo. Esta solución puede proporcionar audio y vídeo directamente entre los puntos de conexión para colaborar uno a uno o descargarlo en una unidad de control multipunto (MCU) central para llamadas en conferencia o reuniones.
    
> [!NOTE]
> Los clientes básicos de Skype empresarial no son compatibles con el paquete de optimización en tiempo real de Citrix HDX ni con el paquete de virtualización horizonte de VMWare. 
  
## <a name="citrix-hdx-realtime-optimization-pack"></a>Citrix HDX RealTime Optimization Pack
<a name="Citrix_RT"> </a>

El complemento de entorno VDI de Citrix (una característica de XenApp y XenDesktop) es compatible con Lync 2013 y Skype empresarial 2015 y 2016 (clientes completos que usan el instalador de cualquier clic para ejecutar, o instaladores MSI publicados después de la versión de Office 2017 PU) clientes instalados en un virtual escrito. Su funcionamiento general se basa en el complemento Microsoft Lync VDI, pero funciona en una mayor variedad de sistemas operativos de cliente, incluidos Windows 10, Macintosh y Linux.
  
Puede encontrar una lista completa de características y tecnologías admitidas en el sitio web de Citrix en [proporcionar Microsoft Skype empresarial a los usuarios de XenApp y XenDesktop](https://www.citrix.com/content/dam/citrix/en_us/documents/products-solutions/delivering-microsoft-lync-to-xenapp-and-xendesktop-users.pdf).
  
Consulte los siguientes vínculos para obtener más información:
  
- [2,1 paquete de optimización en tiempo real](https://docs.citrix.com/en-us/hdx-optimization/2-1.mdl) de Citrix HDX
    
- [Información general técnica](https://docs.citrix.com/en-us/hdx-optimization/2-1/about.mdl)
    
- [CTX200279 de características de Skype para empresas](https://support.citrix.com/article/CTX200279)
    
## <a name="vmware-horizon-virtualization-pack"></a>Paquete de virtualización del horizonte de VMWare
<a name="Citrix_RT"> </a>

La solución de entorno VDI de VMWare es compatible con los clientes de Skype empresarial 2015 y 2016 completos instalados en un escritorio virtual. Su funcionamiento general se basa en el complemento Microsoft Lync VDI, pero funciona en una mayor variedad de sistemas operativos de cliente, incluidos Windows 10, Macintosh y Linux. 
  
Puede encontrar una descripción completa de las características y las tecnologías admitidas en el sitio web de VMWare en los siguientes vínculos:
  
- [Novedades de VMware horizonte 7,4 4,7 cliente &amp; de horizonte](https://blogs.vmware.com/euc/2018/01/vmware-horizon-7-4-horizon-client-4-7-whats-new.mdl)
    
- [Paquete de virtualización del horizonte para Skype empresarial](https://www.vmware.com/products/horizon/skype-for-business.mdl)
    
- [Microsoft Skype empresarial con horizonte de VMWare](https://www.vmware.com/content/dam/digitalmarketing/vmware/en/pdf/products/horizon/vmware-skype-for-business-solution-brief.pdf)
    
## <a name="microsofts-lync-vdi-plug-in"></a>Complemento Lync VDI de Microsoft
<a name="Citrix_RT"> </a>

Con la solución de complemento Microsoft Lync VDI, el usuario tiene que estar en un equipo Windows o en un cliente ligero y tener instalado el complemento de Microsoft Lync VDI para controlar las transmisiones de audio y vídeo del cliente en el escritorio virtual. Los usuarios harán lo siguiente:
  
1. Conectar el dispositivo de audio o vídeo (como un auricular o una cámara) con un equipo local.
    
2. Conéctese a un escritorio virtual remoto con un cliente de Lync 2013 o Skype empresarial 2015.
    
3. Escriba las credenciales de Skype empresarial en el escritorio virtual.
    
4. Vuelva a escribir las credenciales de usuario para establecer una conexión con el complemento VDI para Lync en el equipo local de Windows o en el cliente ligero.
    
Una vez establecida una conexión, el usuario está listo para realizar y recibir llamadas de audio y vídeo. El tráfico en la red y la carga en el escritorio virtual se ven minimizados, dado que el equipo local administra el procesamiento de audio y vídeo.
  
El complemento Microsoft Lync VDI solo se admite en ciertos sistemas operativos de Windows y solo admite clientes de Lync 2013 o Skype empresarial 2015. Consulte [Tecnologías de virtualización compatibles y limitaciones conocidas](vdi-environments.md#Supported_virt) para obtener más información sobre las tecnologías admitidas y las limitaciones.
  
Consulte los siguientes vínculos para obtener más información:
  
- [Tecnologías de virtualización admitidas y limitaciones comunes](vdi-environments.md#Supported_virt)
    
- [Requisitos previos del complemento Lync VDI](vdi-environments.md#VDI_prereq)
    
- [Implementar el complemento VDI para Lync con Skype empresarial Server](../../deploy/deploy-clients/deploy-the-lync-vdi-plug-in.md)
    
- Artículo de [CTX138408](https://support.citrix.com/article/CTX138408) de Citrix Knowledge Center
    
El complemento Microsoft VDI está disponible en [Microsoft Lync vdi 2013 (32 bits)](https://www.microsoft.com/en-us/download/details.aspx?id=35457) o [complemento microsoft Lync vdi 2013 (64 bit)](https://www.microsoft.com/en-us/download/details.aspx?id=35454). Este complemento es compatible con el cliente de Skype empresarial 2015, a pesar del nombre.
  
### <a name="supported-virtualization-technologies-and-known-limitations"></a>Tecnologías de virtualización admitidas y limitaciones comunes
<a name="Supported_virt"> </a>

El complemento VDI para Lync permite llamadas de audio y vídeo para tecnologías de virtualización compatibles. Conforme a las normativas estándar para teléfonos, también se incluye compatibilidad con E911. En las siguientes secciones se describen las tecnologías de virtualización admitidas por el complemento VDI de Lync y las limitaciones de las características conocidas.
  
#### <a name="support-for-virtualization-technologies"></a>Soporte de tecnologías de virtualización

El complemento VDI de Lync admite sesiones de escritorio remoto completas en el escenario de escritorio virtual personal, pero no en el escenario de sesión de escritorio remoto. Estos entornos pueden describirse así:
  
- **Admitido: escritorios virtuales personalizados o infraestructura de escritorio virtual (VDI).** En esta situación, cada usuario inicia sesión en un escritorio virtual personalizable y puede guardar archivos en el escritorio, que se conservan entre sesiones. Servicios de escritorio remoto de Microsoft y vista de horizonte de VMware son implementaciones de ejemplo que se han probado para su uso con Skype empresarial 2015. Otras implementaciones en etapa de validación incluyen Citrix XenDesktop. Para obtener información sobre los entornos de VDI específicos del proveedor y el hardware de cliente que Microsoft ha probado, consulte [infraestructura cualificada para Microsoft Lync](https://go.microsoft.com/fwlink/?LinkID=313435).
    
- **No admitido: sesiones de Escritorio remoto.** En esta situación, cada usuario inicia sesión en una sesión de escritorio virtual genérica que no puede personalizarse. Algunos ejemplos son Microsoft Remote Desktop Sessions (RDSH) y Citrix XenApp combinados con el receptor Citrix.
    
El complemento de VDI para Lync no admite otras tecnologías de virtualización, como la virtualización de aplicaciones, que permite el uso de una aplicación sin requerir la instalación de la aplicación completa de forma local. Algunos ejemplos de implementaciones son Citrix XenApp y Microsoft Application Virtualization (App-V). El streaming de aplicaciones, la comunicación remota de aplicaciones y los modos mixtos de virtualización (por ejemplo, la comunicación remota de aplicaciones en la comunicación remota de escritorio completa) no se admiten.
  
El complemento de VDI para Lync se ha diseñado para usar las API independientes de la plataforma denominadas canales virtuales dinámicos (DVCs). En el caso de entornos que no se admiten de forma explícita, consulte las instrucciones de compatibilidad del proveedor de la solución de VDI.
  
#### <a name="lync-vdi-plug-in-prerequisites"></a>Requisitos previos del componente de VDI de Lync
<a name="VDI_prereq"> </a>

En un entorno de VDI, las máquinas virtuales y el equipo local del usuario deben cumplir los requisitos descritos en esta sección.
  
> [!NOTE]
>  Su proveedor de soluciones de virtualización puede brindarle información sobre la instalación y la implementación del entorno. Para obtener información general sobre cómo implementar un entorno virtualizado basado en Hyper-V y servicios de escritorio remoto, consulte los artículos siguientes en la biblioteca de Microsoft: [Hyper-v](https://go.microsoft.com/fwlink/p/?linkid=247514), [servicios de escritorio remoto en Windows Server 2008 R2](https://go.microsoft.com/fwlink/p/?linkid=247513) 
  
Las máquinas virtuales deben configurarse con Windows 8, Windows 7 o Windows Server 2008 R2 con los Service Packs más recientes.
  
El equipo local del usuario debe cumplir los siguientes requisitos:
  
- El usuario debe estar alojado en Skype empresarial Server o Lync Server 2013.
    
- El equipo local debe estar ejecutando Windows Embedded Standard 7 con SP1, Windows 7 o Windows 8.
    
- Si está usando servicios de escritorio remoto, elija el complemento VDI de 32 bits o 64 bits de Lync para que coincida con el sistema operativo del equipo local. No se requiere que tanto el equipo local como la máquina virtual tengan sistemas operativos de 32 o 64 bits. Si utiliza otra solución o plataforma de virtualización, consulte los requisitos de su proveedor.
    
- El equipo local debe estar ejecutando la [última versión del cliente de escritorio remoto](https://go.microsoft.com/fwlink/p/?LinkId=268032). Instale las últimas actualizaciones del cliente de los Servicios de Escritorio remoto de Microsoft o el último software de cliente de escritorio remoto del proveedor de soluciones de virtualización. 
    
- En el equipo local, configure el cliente de escritorio remoto para que el audio se reproduzca en el equipo local y la grabación remota esté deshabilitada. Para configurar estas opciones de conexión a escritorio remoto en Windows, consulte la sección siguiente, "para configurar las opciones de conexión a escritorio remoto". 
    
El complemento Microsoft VDI está disponible en [Microsoft Lync vdi 2013 (32 bits)](https://www.microsoft.com/en-us/download/details.aspx?id=35457) o [complemento microsoft Lync vdi 2013 (64 bit)](https://www.microsoft.com/en-us/download/details.aspx?id=35454).
  
#### <a name="known-feature-limitations"></a>Limitaciones comunes de la funciones
<a name="VDI_prereq"> </a>

A continuación se indican algunas limitaciones conocidas al usar el cliente de Skype empresarial 2015 en un entorno de VDI:
  
La delegación de llamadas y las características de anonymization de grupo de respuesta son limitadas.
  
No se admiten estas características:
  
- Las páginas de ajuste del dispositivo de audio y de vídeo integrados.
    
- El vídeo de múltiples vistas.
    
- La grabación de las conversaciones.
    
- Unirse a reuniones de forma anónima (es decir, unirse a reuniones de Skype empresarial hospedadas por una organización que no se federa con su organización).
    
- Usar el complemento VDI de Lync junto con un dispositivo de Lync Phone Edition.
    
- La continuación de llamadas en caso de una interrupción de la red.
    
- Las características de tonos de llamada personalizados y de música en espera.
    
El complemento de VDI para Lync no es compatible en un entorno de Office 365.
  
> [!NOTE]
> Citrix RealTime Optimization Pack admite Office 365. Para entornos virtuales basados en Citrix, revise la documentación de la [información general técnica](https://docs.citrix.com/en-us/hdx-optimization/2-0/hdx-realtime-optimization-pack-about.mdl) de Citrix para ver la lista de características y versiones compatibles.
  
## <a name="see-also"></a>Vea también
<a name="Citrix_RT"> </a>

[Implementar el complemento VDI para Lync con Skype empresarial Server](../../deploy/deploy-clients/deploy-the-lync-vdi-plug-in.md)

