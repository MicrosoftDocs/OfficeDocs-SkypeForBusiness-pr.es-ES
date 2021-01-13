---
title: Planear Skype Empresarial en entornos VDI
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
ms.openlocfilehash: 66fe9dd0be2dd079597837b8d25c29b3f047b0c6
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816110"
---
# <a name="plan-for-skype-for-business-in-vdi-environments"></a>Planear Skype Empresarial en entornos VDI
 
En este tema se analizan las consideraciones de planeación para usar Skype Empresarial al conectarse a un escritorio virtual remoto. 
  
Un entorno de infraestructura de escritorio virtual (VDI) se usa en algunas organizaciones en las que los problemas de seguridad y cumplimiento son especialmente confidenciales. Sus usuarios hacen su trabajo en un escritorio virtual con todas sus aplicaciones de escritorio y archivos mediante Servicios de Escritorio remoto o una conexión remota similar. El uso de Skype Empresarial con audio y vídeo completos en una conexión como esta requiere cargas intensas de procesamiento de audio y vídeo en el cliente que se encuentra en un escritorio virtual. Hay disponible un software de complemento VDI adicional que descarga ese procesamiento en la máquina local del usuario final y reduce la carga en el escritorio virtual.
  
Hay tres soluciones disponibles para el componente de complemento VDI, ofrecido por Microsoft, Citrix o VMWare. Para las nuevas implementaciones, Microsoft recomienda usar la solución Citrix HDX RealTime Optimization Pack o VMWare Horizon Virtualization Pack. El complemento VDI de Lync original sigue siendo compatible durante el resto de su ciclo de vida.
  
- El complemento **Lync VDI** se desarrolló para Lync 2013 y es compatible con el cliente de Lync 2013 o Skype Empresarial 2015 que se ejecuta en un escritorio virtual. Es una aplicación independiente que se instala en el equipo local y permite el uso de dispositivos locales de audio y vídeo con un cliente en un escritorio virtual. El complemento no requiere que un cliente de Skype Empresarial esté instalado en el equipo local o en el cliente ligero, que debe ejecutar sistemas operativos Windows 7, Windows 8 o Windows Server 2008. (Los dispositivos cliente ligeros que usan estos sistemas operativos y que son compatibles con Microsoft incluyen: Dell Wyse Z90D7, Dell Wyse R90L7, Dell Wyse X90m7, HP t610 y HP t5740e). Este complemento sigue siendo compatible, pero no se planean actualizaciones futuras. Para entornos virtuales basados en Citrix, se recomienda Citrix RealTime Optimization Pack.
    
- **Citrix RealTime Optimization Pack** se basa en el complemento Lync VDI y funciona con clientes de Lync 2013 o Skype Empresarial 2016 en un escritorio virtual. Fue desarrollado por Citrix y Microsoft para mejorar el complemento VDI original. Se puede instalar en clientes con windows y sistemas operativos que no sean windows (incluidos Windows 10, Mac y Linux). Consta de dos componentes: RealTime Connector (que está instalado en el escritorio virtual) y RealTime Media Engine (que se instala en el equipo local del usuario final). Estos dos componentes permiten al equipo local del usuario usar el cliente de Skype Empresarial que se ejecuta en el escritorio virtual con el procesamiento de A/V movido al equipo local. Para entornos de escritorio virtual basados en Citrix, se recomienda Citrix RealTime Optimization Pack y se planea una mayor compatibilidad.
    
- VmWare **Horizon Virtualization Pack** para Skype Empresarial, desarrollado en colaboración con VMWare, le permite ofrecer Skype Empresarial en un escritorio virtual a la vez que ofrece una excelente experiencia de usuario. La solución funciona aprovechando un motor multimedia en el cliente para crear una solución optimizada, con el punto de conexión de cliente que proporciona capacidades de descarga de medios para llamadas de audio y vídeo. Esta solución que puede ofrecer audio y vídeo directamente entre los puntos de conexión para la colaboración uno a uno, o descargarla en una unidad de control multipunto (MCU) central para reuniones o llamadas de conferencia entre varias entidades.
    
> [!NOTE]
> Los clientes de Skype Empresarial Basic no son compatibles con Citrix HDX RealTime Optimization Pack o VMWare Horizon Virtualization Pack. 
  
## <a name="citrix-hdx-realtime-optimization-pack"></a>Citrix HDX RealTime Optimization Pack
<a name="Citrix_RT"> </a>

El complemento de entorno VDI de Citrix (una característica de XenApp y XenDesktop) es compatible con lync 2013 y Skype Empresarial 2015 y 2016 (clientes completos con cualquier clic para ejecutar instalador o instaladores MSI publicados después de la ACTUALIZACIÓN de enero de 2017) instalados en un escritorio virtual. Su funcionamiento general se basa en el complemento VDI de Microsoft Lync, pero funciona en una amplia variedad de sistemas operativos cliente, incluidos Windows 10, Macintosh y Linux.
  
Puede encontrar una lista completa de características y tecnologías compatibles en el sitio web de Citrix en Entregar Microsoft Skype Empresarial a los usuarios [de XenApp y XenDesktop.](https://www.citrix.com/content/dam/citrix/en_us/documents/products-solutions/delivering-microsoft-lync-to-xenapp-and-xendesktop-users.pdf)
  
Revise los siguientes vínculos para obtener más información:
  
- Citrix [HDX RealTime Optimization Pack 2.1](https://docs.citrix.com/en-us/hdx-optimization/2-1.mdl)
    
- [Introducción técnica](https://docs.citrix.com/en-us/hdx-optimization/2-1/about.mdl)
    
- [Compatibilidad con características de Skype Empresarial CTX200279](https://support.citrix.com/article/CTX200279)
    
## <a name="vmware-horizon-virtualization-pack"></a>VMWare Horizon Virtualization Pack
<a name="Citrix_RT"> </a>

La solución de entorno VDI de VMWare es compatible con los clientes completos de Skype Empresarial 2015 y 2016 instalados en un escritorio virtual. Su funcionamiento general se basa en el complemento VDI de Microsoft Lync, pero funciona en una amplia variedad de sistemas operativos cliente, incluidos Windows 10, Macintosh y Linux. 
  
Puede encontrar una explicación completa de las características y tecnologías compatibles en el sitio web de VMWare en los siguientes vínculos:
  
- [Novedades de VMware Horizon 7.4 &amp; Horizon Client 4.7](https://blogs.vmware.com/euc/2018/01/vmware-horizon-7-4-horizon-client-4-7-whats-new.mdl)
    
- [Paquete de virtualización de Horizon para Skype Empresarial](https://www.vmware.com/products/horizon/skype-for-business.mdl)
    
- [Microsoft Skype Empresarial con VMWare Horizon](https://www.vmware.com/content/dam/digitalmarketing/vmware/en/pdf/products/horizon/vmware-skype-for-business-solution-brief.pdf)
    
## <a name="microsofts-lync-vdi-plug-in"></a>Complemento Lync VDI de Microsoft
<a name="Citrix_RT"> </a>

Con la solución de complemento VDI de Microsoft Lync, el usuario debe estar en un equipo Windows o un cliente ligero y tener instalado el complemento VDI de Lync de Microsoft para controlar las secuencias de audio y vídeo desde el cliente en el escritorio virtual. Un usuario hará lo siguiente:
  
1. Conecta un dispositivo de audio y vídeo (como unos auriculares o una cámara) a un equipo local.
    
2. Conéctese a un escritorio virtual remoto con un cliente de Lync 2013 o Skype Empresarial 2015.
    
3. Escriba las credenciales de Skype Empresarial en el escritorio virtual.
    
4. Vuelva a escribir las credenciales de usuario para establecer una conexión con el complemento Lync VDI en el equipo local de Windows o el cliente ligero.
    
Una vez establecida una conexión, el usuario está listo para realizar y recibir llamadas de audio y vídeo. El tráfico de la red y la carga en el escritorio virtual están minimizados, ya que el equipo local controla el procesamiento de audio y vídeo.
  
El complemento Lync VDI de Microsoft solo se admite en determinados sistemas operativos Windows y solo admite clientes de Lync 2013 o Skype Empresarial 2015. Consulta [Tecnologías de virtualización compatibles y limitaciones conocidas](vdi-environments.md#Supported_virt) para obtener más información sobre las tecnologías y limitaciones admitidas.
  
Revise los siguientes vínculos para obtener más información:
  
- [Tecnologías de virtualización admitidas y limitaciones conocidas](vdi-environments.md#Supported_virt)
    
- [Requisitos previos del complemento Lync VDI](vdi-environments.md#VDI_prereq)
    
- [Implementar el complemento Lync VDI con Skype Empresarial Server](../../deploy/deploy-clients/deploy-the-lync-vdi-plug-in.md)
    
- Artículo de Citrix Knowledge Center [CTX138408](https://support.citrix.com/article/CTX138408)
    
El complemento VDI de Microsoft está disponible en el complemento [Microsoft Lync VDI 2013 (32 bits)](https://www.microsoft.com/download/details.aspx?id=35457) o en el complemento de [Microsoft Lync VDI 2013 (64 bits).](https://www.microsoft.com/download/details.aspx?id=35454) Este complemento es compatible con el cliente de Skype Empresarial 2015, a pesar del nombre.
  
### <a name="supported-virtualization-technologies-and-known-limitations"></a>Tecnologías de virtualización admitidas y limitaciones conocidas
<a name="Supported_virt"> </a>

El complemento Lync VDI permite las llamadas de audio y vídeo para las tecnologías de virtualización compatibles. En cumplimiento con las normativas telefónicas estándar, también se incluye compatibilidad con E911. En las secciones siguientes se describen las tecnologías de virtualización compatibles con el complemento Lync VDI y las limitaciones de características conocidas.
  
#### <a name="support-for-virtualization-technologies"></a>Compatibilidad con tecnologías de virtualización

El complemento Lync VDI admite sesiones remotas de escritorio completo en el escenario de escritorio virtual personal, pero no en el escenario de sesión de Escritorio remoto. Estos escenarios se pueden describir de la siguiente manera:
  
- **Compatible: Escritorios virtuales personalizados o Infraestructura de escritorio virtual (VDI).** En este escenario, cada usuario inicia sesión en un escritorio virtual personalizable y es capaz de guardar archivos en el escritorio que persisten entre sesiones. Los Servicios de Escritorio remoto de Microsoft y VMware Horizon View son implementaciones de ejemplo que se han probado para su uso con Skype Empresarial 2015. Otras implementaciones que se están validando son Citrix XenDesktop. Para obtener información sobre los entornos VDI específicos del proveedor y el hardware de cliente que microsoft ha probado, consulte Infraestructura cualificada [para Microsoft Lync.](https://go.microsoft.com/fwlink/?LinkID=313435)
    
- **No compatible: Sesiones de Escritorio remoto.** En este escenario, cada usuario inicia sesión en una sesión genérica de escritorio virtual que no se puede personalizar. Algunos ejemplos son sesiones de Escritorio remoto de Microsoft (RDSH) y Citrix XenApp combinadas con Citrix Receiver.
    
El complemento Lync VDI no admite otras tecnologías de virtualización, como la virtualización de aplicaciones, que permite el uso de una aplicación sin necesidad de instalar la aplicación completa localmente. Entre las implementaciones de ejemplo se incluyen Citrix XenApp y Microsoft Application Virtualization (App-V). No se admiten el streaming de aplicaciones, la comunicación remota de aplicaciones y los modos mixtos de virtualización (por ejemplo, comunicación remota de aplicaciones en comunicación remota de escritorio completo).
  
El complemento Lync VDI se diseñó para usar API independientes de la plataforma denominadas canales virtuales dinámicos (DVC). Para escenarios que no se admiten explícitamente, consulte las instrucciones de compatibilidad del proveedor de soluciones VDI.
  
#### <a name="lync-vdi-plug-in-prerequisites"></a>Requisitos previos del complemento Lync VDI
<a name="VDI_prereq"> </a>

En un entorno de VDI, las máquinas virtuales y el equipo local del usuario deben cumplir los requisitos descritos en esta sección.
  
> [!NOTE]
>  El proveedor de soluciones de virtualización puede proporcionar detalles sobre cómo instalar e implementar su entorno. Para obtener información general sobre la implementación de un entorno virtualizado basado en Hyper-V y servicios de Escritorio remoto, vea los siguientes artículos en la Biblioteca de Microsoft: [Hyper-V](https://go.microsoft.com/fwlink/p/?linkid=247514), Servicios de Escritorio remoto en [Windows Server 2008 R2](https://go.microsoft.com/fwlink/p/?linkid=247513) 
  
Las máquinas virtuales deben configurarse con Windows 8, Windows 7 o Windows Server 2008 R2 con los Service Pack más recientes.
  
El equipo local del usuario debe cumplir los siguientes requisitos:
  
- El usuario debe estar en Skype Empresarial Server o Lync Server 2013.
    
- El equipo local debe ejecutar Windows Embedded Standard 7 con SP1, Windows 7 con SP1 o Windows 8.
    
- Si usa Servicios de Escritorio remoto, elija el complemento Lync VDI de 32 o 64 bits para que coincida con el sistema operativo del equipo local. No es necesario que el equipo local y la máquina virtual tengan sistemas operativos de 32 o 64 bits. Si usa otra solución o plataforma de virtualización, consulte los requisitos de su proveedor.
    
- El equipo local debe ejecutar la [versión más reciente del cliente de Escritorio remoto.](https://go.microsoft.com/fwlink/p/?LinkId=268032) Instale las últimas actualizaciones de cliente de los servicios de escritorio remoto de Microsoft o el último software cliente de escritorio remoto del proveedor de soluciones de virtualización. 
    
- En el PC local, configure el cliente de escritorio remoto para que el audio se reproduzca en el PC local y que la grabación remota esté deshabilitada. Para configurar estas opciones para la conexión a Escritorio remoto en Windows, consulte la sección siguiente, "Para configurar las opciones de conexión a Escritorio remoto". 
    
El complemento VDI de Microsoft está disponible en el complemento [Microsoft Lync VDI 2013 (32 bits)](https://www.microsoft.com/download/details.aspx?id=35457) o en el complemento de [Microsoft Lync VDI 2013 (64 bits).](https://www.microsoft.com/download/details.aspx?id=35454)
  
#### <a name="known-feature-limitations"></a>Limitaciones de características conocidas
<a name="VDI_prereq"> </a>

Las siguientes son limitaciones conocidas al usar el cliente de Skype Empresarial 2015 en un entorno de VDI:
  
Hay compatibilidad limitada con las características de delegación de llamadas y anonimización de agente de grupo de respuesta.
  
No se admiten estas características:
  
- Las páginas de ajuste del dispositivo de audio y de vídeo integrados.
    
- Vídeo de varias vistas.
    
- La grabación de las conversaciones.
    
- Unirse a reuniones de forma anónima (es decir, unirse a reuniones de Skype Empresarial hospedadas por una organización que no está federada con su organización).
    
- Usar el complemento Lync VDI junto con un dispositivo Lync Phone Edition.
    
- La continuación de llamadas en caso de una interrupción de la red.
    
- Tonos personalizados y características de música en espera.
    
El complemento Lync VDI no se admite en entornos de Microsoft 365 u Office 365.
  
> [!NOTE]
> Citrix RealTime Optimization Pack es compatible con Microsoft 365 y Office 365. Para entornos virtuales basados en Citrix, revise la documentación de Información técnica [general](https://docs.citrix.com/en-us/hdx-optimization/2-0/hdx-realtime-optimization-pack-about.mdl) de Citrix para ver la lista de características y versiones compatibles.
  
## <a name="see-also"></a>Ver también
<a name="Citrix_RT"> </a>

[Implementar el complemento Lync VDI con Skype Empresarial Server](../../deploy/deploy-clients/deploy-the-lync-vdi-plug-in.md)

