---
title: Planeación de Skype Empresarial en entornos VDI
author: cichur
ms.author: v-cichur
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
description: En este tema se analizan las consideraciones de planeación para usar Skype Empresarial al conectarse a un escritorio virtual remoto.
ms.openlocfilehash: ca466b490fc04f44f2b8402c2f05aa1560e79774
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51112796"
---
# <a name="plan-for-skype-for-business-in-vdi-environments"></a>Planeación de Skype Empresarial en entornos VDI
 
En este tema se analizan las consideraciones de planeación para usar Skype Empresarial al conectarse a un escritorio virtual remoto. 
  
Un entorno de infraestructura de escritorio virtual (VDI) se usa en algunas organizaciones donde los problemas de seguridad y cumplimiento son especialmente confidenciales. Sus usuarios hacen su trabajo en un escritorio virtual con todas sus aplicaciones de escritorio y archivos con Servicios de Escritorio remoto o una conexión remota similar. El uso de Skype Empresarial con audio y vídeo completos en una conexión como esa requiere una gran cantidad de procesamiento de audio y vídeo en el cliente que se encuentra en un escritorio virtual. Hay disponible un software de complemento VDI adicional que descarga ese procesamiento en la máquina local del usuario final y reduce la carga en el escritorio virtual.
  
Hay tres soluciones disponibles para el componente de complemento VDI, ofrecido por Microsoft, Citrix o VMWare. Para las nuevas implementaciones, Microsoft recomienda usar la solución Citrix HDX RealTime Optimization Pack o VMWare Horizon Virtualization Pack. El complemento VDI de Lync original sigue siendo compatible durante el resto de su ciclo de vida.
  
- El complemento **VDI** de Lync se desarrolló para Lync 2013 y es compatible con el cliente de Lync 2013 o Skype Empresarial 2015 que se ejecuta en un escritorio virtual. Es una aplicación independiente que se instala en el equipo local y permite el uso de dispositivos de audio y vídeo locales con un cliente en un escritorio virtual. El complemento no requiere que se instale un cliente de Skype Empresarial en el equipo local o en el cliente ligero, que debe ejecutar sistemas operativos Windows 7, Windows 8 o Windows Server 2008. (Los dispositivos cliente ligeros que usan estos sistemas operativos y compatibles con Microsoft incluyen: Dell Wyse Z90D7, Dell Wyse R90L7, Dell Wyse X90m7, HP t610 y HP t5740e). Este complemento sigue siendo compatible, pero no se planean actualizaciones futuras. Para entornos virtuales basados en Citrix, se recomienda Citrix RealTime Optimization Pack.
    
- **Citrix RealTime Optimization Pack** se basa en el complemento VDI de Lync y funciona con clientes de Lync 2013 o Skype Empresarial 2016 en un escritorio virtual. Fue desarrollado por Citrix y Microsoft para mejorar el complemento VDI original. Se puede instalar en clientes con windows y sistemas operativos que no son windows (incluidos Windows 10, Mac y Linux). Consta de dos componentes: realTime Connector (que está instalado en el escritorio virtual) y RealTime Media Engine (que se instala en el equipo local del usuario final). Estos dos componentes permiten al equipo local del usuario usar el cliente de Skype Empresarial que se ejecuta en el escritorio virtual con el procesamiento A/V movido al equipo local. Para entornos de escritorio virtual basados en Citrix, se recomienda Citrix RealTime Optimization Pack y se planea más compatibilidad.
    
- VmWare **Horizon Virtualization Pack** para Skype Empresarial, desarrollado en colaboración con VMWare, le permite ofrecer Skype Empresarial en un escritorio virtual y ofrecer una excelente experiencia de usuario. La solución funciona aprovechando un motor multimedia en el cliente para crear una solución optimizada, con el extremo de cliente que proporciona capacidades de descarga de medios para llamadas de audio y vídeo. Esta solución que puede entregar audio y vídeo directamente entre los puntos de conexión para la colaboración uno a uno, o descargarla a una unidad de control multipunto central (MCU) para reuniones o llamadas de conferencias de varias partes.
    
> [!NOTE]
> Los clientes de Skype Empresarial Basic no son compatibles con Citrix HDX RealTime Optimization Pack o VMWare Horizon Virtualization Pack. 
  
## <a name="citrix-hdx-realtime-optimization-pack"></a>Citrix HDX RealTime Optimization Pack
<a name="Citrix_RT"> </a>

El complemento de entorno VDI de Citrix (una característica de XenApp y XenDesktop) es compatible con lync 2013 y Skype Empresarial 2015 y 2016 (clientes completos con cualquier clic para ejecutar instalador o instaladores MSI lanzados después de la PU de enero de 2017) instalados en un escritorio virtual. Su funcionamiento general se basa en el complemento VDI de Microsoft Lync, pero funciona en una amplia variedad de sistemas operativos cliente, incluidos Windows 10, Macintosh y Linux.
  
Puede encontrar una lista completa de características y tecnologías compatibles en el sitio web de Citrix en [Delivering Microsoft Skype for Business to XenApp and XenDesktop Users](https://www.citrix.com/content/dam/citrix/en_us/documents/products-solutions/delivering-microsoft-lync-to-xenapp-and-xendesktop-users.pdf).
  
Revise los siguientes vínculos para obtener más información:
  
- Citrix [HDX RealTime Optimization Pack 2.1](https://docs.citrix.com/en-us/hdx-optimization/2-1.mdl)
    
- [Introducción técnica](https://docs.citrix.com/en-us/hdx-optimization/2-1/about.mdl)
    
- [Compatibilidad con características de Skype Empresarial CTX200279](https://support.citrix.com/article/CTX200279)
    
## <a name="vmware-horizon-virtualization-pack"></a>VMWare Horizon Virtualization Pack
<a name="Citrix_RT"> </a>

La solución de entorno VDI de VMWare es compatible con los clientes completos de Skype Empresarial 2015 y 2016 instalados en un escritorio virtual. Su funcionamiento general se basa en el complemento VDI de Microsoft Lync, pero funciona en una amplia variedad de sistemas operativos cliente, incluidos Windows 10, Macintosh y Linux. 
  
Puede encontrar una explicación completa de las características y las tecnologías compatibles en el sitio web de VMWare en los siguientes vínculos:
  
- [Novedades de VMware Horizon 7.4 &amp; Horizon Client 4.7](https://blogs.vmware.com/euc/2018/01/vmware-horizon-7-4-horizon-client-4-7-whats-new.mdl)
    
- [Paquete de virtualización de Horizon para Skype Empresarial](https://www.vmware.com/products/horizon/skype-for-business.mdl)
    
- [Microsoft Skype Empresarial con VMWare Horizon](https://www.vmware.com/content/dam/digitalmarketing/vmware/en/pdf/products/horizon/vmware-skype-for-business-solution-brief.pdf)
    
## <a name="microsofts-lync-vdi-plug-in"></a>Complemento Lync VDI de Microsoft
<a name="Citrix_RT"> </a>

Con la solución de complemento VDI de Microsoft Lync, el usuario debe estar en un equipo Windows o cliente ligero y tener instalado el complemento VDI de Lync de Microsoft para controlar las secuencias de audio y vídeo del cliente en el escritorio virtual. Un usuario:
  
1. Conecta un dispositivo de audio y vídeo (como auriculares o cámara) a un equipo local.
    
2. Conéctese a un escritorio virtual remoto con un cliente de Lync 2013 o Skype Empresarial 2015.
    
3. Escriba las credenciales de Skype Empresarial en el escritorio virtual.
    
4. Vuelva a escribir las credenciales de usuario para establecer una conexión con el complemento VDI de Lync en el equipo local de Windows o cliente ligero.
    
Una vez establecida una conexión, el usuario está listo para realizar y recibir llamadas de audio y vídeo. El tráfico en la red y la carga en el escritorio virtual se minimizan, ya que el equipo local controla el procesamiento de audio y vídeo.
  
El complemento Lync VDI de Microsoft solo se admite en determinados sistemas operativos Windows y solo admite clientes de Lync 2013 o Skype Empresarial 2015. Consulte [Tecnologías de virtualización admitidas y](vdi-environments.md#Supported_virt) limitaciones conocidas para obtener más información sobre las tecnologías y limitaciones admitidas.
  
Revise los siguientes vínculos para obtener más información:
  
- [Tecnologías de virtualización admitidas y limitaciones conocidas](vdi-environments.md#Supported_virt)
    
- [Requisitos previos del complemento VDI de Lync](vdi-environments.md#VDI_prereq)
    
- [Implementar el complemento VDI de Lync con Skype Empresarial Server](../../deploy/deploy-clients/deploy-the-lync-vdi-plug-in.md)
    
- Artículo de Citrix Knowledge Center [CTX138408](https://support.citrix.com/article/CTX138408)
    
El complemento VDI de Microsoft está disponible en el complemento [VDI 2013 de Microsoft Lync (32 bits)](https://www.microsoft.com/download/details.aspx?id=35457) o el complemento [VDI 2013 de Microsoft Lync (64 bits).](https://www.microsoft.com/download/details.aspx?id=35454) Este complemento es compatible con el cliente de Skype Empresarial 2015, a pesar del nombre.
  
### <a name="supported-virtualization-technologies-and-known-limitations"></a>Tecnologías de virtualización admitidas y limitaciones conocidas
<a name="Supported_virt"> </a>

El complemento VDI de Lync permite llamadas de audio y vídeo para tecnologías de virtualización compatibles. De acuerdo con las normativas telefónicas estándar, también se incluye la compatibilidad con E911. En las secciones siguientes se describen las tecnologías de virtualización compatibles con el complemento VDI de Lync y las limitaciones de características conocidas.
  
#### <a name="support-for-virtualization-technologies"></a>Compatibilidad con tecnologías de virtualización

El complemento VDI de Lync admite sesiones remotas de escritorio completo en el escenario de escritorio virtual personal, pero no en el escenario de sesión de escritorio remoto. Estos escenarios se pueden describir de la siguiente manera:
  
- **Compatible: Escritorios virtuales personalizados o Infraestructura de escritorio virtual (VDI).** En este escenario, cada usuario inicia sesión en un escritorio virtual personalizable y puede guardar archivos en el escritorio que persisten entre sesiones. Microsoft Remote Desktop Services y VMware Horizon View son implementaciones de ejemplo que se han probado para su uso con Skype Empresarial 2015. Otras implementaciones en proceso de validación son Citrix XenDesktop. Para obtener información acerca de los entornos VDI específicos del proveedor y el hardware de cliente probados por Microsoft, vea [Infrastructure qualified for Microsoft Lync](../../../SfbPartnerCertification/lync-cert/qualified-ip-pbx-gateway.md).
    
- **No compatible: sesiones de Escritorio remoto.** En este escenario, cada usuario inicia sesión en una sesión genérica de escritorio virtual que no se puede personalizar. Algunos ejemplos son Sesiones de Escritorio remoto de Microsoft (RDSH) y Citrix XenApp combinados con Citrix Receiver.
    
El complemento VDI de Lync no admite otras tecnologías de virtualización, como la virtualización de aplicaciones, que permite el uso de una aplicación sin necesidad de instalar la aplicación completa localmente. Entre las implementaciones de ejemplo se incluyen Citrix XenApp y Microsoft Application Virtualization (App-V). No se admiten los modos de streaming de aplicaciones, comunicación remota de aplicaciones y virtualización mixta (por ejemplo, comunicación remota de aplicaciones en la comunicación remota de escritorio completo).
  
El complemento VDI de Lync se diseñó para usar API independientes de la plataforma denominadas Canales virtuales dinámicos (DVCs). Para escenarios que no se admiten explícitamente, consulte instrucciones de soporte del proveedor de soluciones VDI.
  
#### <a name="lync-vdi-plug-in-prerequisites"></a>Requisitos previos del complemento VDI de Lync
<a name="VDI_prereq"> </a>

En un entorno VDI, las máquinas virtuales y el equipo local del usuario deben cumplir los requisitos descritos en esta sección.
  
> [!NOTE]
>  El proveedor de soluciones de virtualización puede proporcionar detalles sobre cómo instalar e implementar su entorno. Para obtener información general acerca de la implementación de un entorno virtualizado basado en Servicios de Hyper-V y Escritorio remoto, vea los siguientes artículos en microsoft library: [Hyper-V](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc753637(v=ws.10)), [Remote Desktop Services in Windows Server 2008 R2](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/dd736539(v=ws.10)) 
  
Las máquinas virtuales deben configurarse con Windows 8, Windows 7 o Windows Server 2008 R2 con los service pack más recientes.
  
El equipo local del usuario debe cumplir los siguientes requisitos:
  
- El usuario debe estar en Skype Empresarial Server o Lync Server 2013.
    
- El equipo local debe ejecutar Windows Embedded Standard 7 con SP1, Windows 7 con SP1 o Windows 8.
    
- Si usa Servicios de Escritorio remoto, elija el complemento VDI de Lync de 32 o 64 bits para que coincida con el sistema operativo del equipo local. No es necesario que el equipo local y la máquina virtual tengan sistemas operativos de 32 o 64 bits. Si usa otra plataforma o solución de virtualización, consulte los requisitos de su proveedor.
    
- El equipo local debe ejecutar la [versión más reciente del cliente de escritorio remoto](/windows-server/remote/remote-desktop-services/clients/remote-desktop-clients). Instale las últimas actualizaciones de cliente de los servicios de escritorio remoto de Microsoft o el último software cliente de escritorio remoto del proveedor de soluciones de virtualización. 
    
- En el PC local, configure el cliente de escritorio remoto para que el audio se reproduzca en el PC local y que la grabación remota esté deshabilitada. Para configurar estas opciones para la conexión de Escritorio remoto en Windows, consulte la siguiente sección, "Para configurar las opciones de conexión de Escritorio remoto". 
    
El complemento VDI de Microsoft está disponible en el complemento [VDI 2013 de Microsoft Lync (32 bits)](https://www.microsoft.com/download/details.aspx?id=35457) o el complemento [VDI 2013 de Microsoft Lync (64 bits).](https://www.microsoft.com/download/details.aspx?id=35454)
  
#### <a name="known-feature-limitations"></a>Limitaciones de características conocidas
<a name="VDI_prereq"> </a>

Las siguientes son limitaciones conocidas al usar el cliente de Skype Empresarial 2015 en un entorno VDI:
  
Hay compatibilidad limitada con las características de anonimización de agentes de grupo de respuesta y delegación de llamadas.
  
No se admiten estas características:
  
- Las páginas de ajuste del dispositivo de audio y de vídeo integrados.
    
- Vídeo de vista múltiple.
    
- La grabación de las conversaciones.
    
- Unirse a reuniones de forma anónima (es decir, unirse a reuniones de Skype Empresarial hospedadas por una organización que no se federa con su organización).
    
- Usar el complemento VDI de Lync junto con un dispositivo Lync Phone Edition.
    
- La continuación de llamadas en caso de una interrupción de la red.
    
- Tonos personalizados y características de música en espera.
    
El complemento VDI de Lync no se admite en entornos de Microsoft 365 u Office 365.
  
> [!NOTE]
> Citrix RealTime Optimization Pack admite Microsoft 365 y Office 365. Para entornos virtuales basados en [](https://docs.citrix.com/en-us/hdx-optimization/2-0/hdx-realtime-optimization-pack-about.mdl) Citrix, revise la documentación de Información general técnica de Citrix para obtener la lista de características y versiones admitidas.
  
## <a name="see-also"></a>Ver también
<a name="Citrix_RT"> </a>

[Implementar el complemento VDI de Lync con Skype Empresarial Server](../../deploy/deploy-clients/deploy-the-lync-vdi-plug-in.md)