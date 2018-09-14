---
title: Planificar Skype Empresarial en entornos de VDI
ms.author: jambirk
author: jambirk
ms.reviewer: krishra
manager: serdars
ms.date: 1/9/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ea68414b-bb7e-483a-b731-b6b5a44372b1
description: En este tema se describe las consideraciones de planeación para el uso de Skype para la empresa mientras se conecta a un escritorio virtual remoto.
ms.openlocfilehash: e4e23ecfba1e7d789dccd5a6cea0e32733643ce4
ms.sourcegitcommit: b265545216ff36772d5dc2df381a9046bc71098e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/13/2018
ms.locfileid: "23965694"
---
# <a name="plan-for-skype-for-business-in-vdi-environments"></a>Planificar Skype Empresarial en entornos de VDI
 
En este tema se describe las consideraciones de planeación para el uso de Skype para la empresa mientras se conecta a un escritorio virtual remoto. 
  
El entorno de Infraestructura de escritorio virtual (VDI) se utiliza en algunas organizaciones donde los problemas de seguridad y cumplimiento son especialmente delicados. Sus usuarios trabajan en un escritorio virtual, y todos sus archivos y aplicaciones de escritorio usan los Servicios de Escritorio remoto o una conexión similar. Usar Skype para la empresa con completa de audio y vídeo en una conexión que requieren cargas elevadas de audio y vídeo de procesamiento en el cliente hospedados en un escritorio virtual. Software adicional de complemento de VDI está disponible que descarga el que el procesamiento en el equipo local del usuario final y reduce la carga en el escritorio virtual.
  
Existen tres soluciones disponibles para el componente de complemento de VDI, ofrecido por Microsoft, Citrix o VMWare. Para las implementaciones de nuevo, Microsoft recomienda el uso de la solución de Citrix HDX en tiempo real Optimization Pack o el paquete de virtualización de VMWare horizonte. El complemento de VDI de Lync original sigue siendo compatible con el resto de su ciclo de vida.
  
- El **Complemento de VDI de Lync** se desarrolló para Lync 2013 y es compatible con el Lync 2013 o Skype para cliente 2015 empresariales que se ejecutan en un escritorio virtual. Es una aplicación independiente que se instala en el equipo local y permite usar dispositivos de audio y vídeo locales con un cliente en un escritorio virtual. El complemento no requiere un Skype para cliente empresarial esté instalado en el equipo local o un cliente ligero, que debe ejecutar sistemas operativos Windows 7, Windows 8 o Windows Server 2008. (Los dispositivos de cliente ligero con estos sistemas operativos y compatible con Microsoft: Dell Wyse Z90D7, Dell Wyse R90L7, Dell Wyse X90m7, t610 de HP y HP t5740e.) Este complemento todavía se admite, pero planeados no hay actualizaciones en el futuro. Para los entornos virtuales basados en Citrix, se recomienda Citrix RealTime Optimization Pack.
    
- El **Paquete de optimización de Citrix en tiempo real** se basa en el complemento de VDI de Lync y funciona con Lync 2013 o Skype para clientes empresariales 2016 en un escritorio virtual. Se desarrolló de manera conjunta entre Citrix y Microsoft para mejorar a partir del complemento de VDI original. Puede instalarse en clientes con sistemas operativos Windows y distintos de Windows (incluidos Windows 10, Mac y Linux). Consta de dos componentes: el conector en tiempo real (que se instala en el escritorio virtual) y el motor de multimedia en tiempo real (que se instala en el equipo local del usuario final). Estos dos componentes de permitir que el equipo del usuario local que se usará el Skype para clientes empresariales que se ejecutan en el escritorio virtual con el / procesamiento V movido en el equipo local. Para los entornos de escritorio virtual basados en Citrix, se recomienda Citrix RealTime Optimization Pack y se prevé proporcionar mayor compatibilidad en el futuro.
    
- El **Paquete de virtualización de VMWare horizonte** de Skype para la empresa, desarrollado en colaboración con VMWare, permite entregar Skype para la empresa en un escritorio virtual al tiempo que ofrece una experiencia de usuario excelente. El funcionamiento de la solución al aprovechar un motor de medios en el cliente para crear una solución optimizada, con el extremo de cliente que proporciona los medios capacidades para llamadas de audio y vídeo de descarga. Esta solución que puede entregar audio y vídeo, ya sea directamente entre los extremos de colaboración espontánea o descarga a una central Control unidad multipunto (MCU) para llamadas de conferencia con varios participantes o reuniones.
    
> [!NOTE]
> El Skype para clientes empresariales básicos no son compatibles con el paquete de optimización de Citrix HDX en tiempo real o el paquete de virtualización de VMWare horizonte. 
  
## <a name="citrix-hdx-realtime-optimization-pack"></a>Citrix HDX RealTime Optimization Pack
<a name="Citrix_RT"> </a>

Complemento de entorno de Citrix VDI (una característica de XenApp y XenDesktop) es compatible con Lync 2013 y Skype para profesionales de 2015 y 2016 clientes (clientes completa mediante cualquier clic para ejecutar el instalador o instaladores MSI publicados después de 2017 PU de enero) instalados en un virtual escritorio. Su funcionamiento general se basa en el complemento de Microsoft Lync VDI, pero funciona en una mayor variedad de sistemas operativos de cliente, incluidos el 10 de Windows, Macintosh y Linux.
  
Una lista completa de las características y tecnologías admitidas puede encontrarse en el sitio Web de Citrix en [Ofrecer Microsoft Skype para la empresa a XenApp y XenDesktop a los usuarios](https://www.citrix.com/content/dam/citrix/en_us/documents/products-solutions/delivering-microsoft-lync-to-xenapp-and-xendesktop-users.pdf).
  
Consulte los siguientes vínculos para obtener más información:
  
- Citrix [HDX en tiempo real Optimization Pack 2.1](https://docs.citrix.com/en-us/hdx-optimization/2-1.mdl)
    
- [Información general técnica](https://docs.citrix.com/en-us/hdx-optimization/2-1/about.mdl)
    
- [CTX200279 Skype para compatibilidad con la característica empresarial](https://support.citrix.com/article/CTX200279)
    
## <a name="vmware-horizon-virtualization-pack"></a>Paquete de virtualización de VMWare horizonte
<a name="Citrix_RT"> </a>

Solución de entorno de VMWare VDI es compatible con Skype para profesionales de 2015 y 2016 clientes completos instalados en un escritorio virtual. Su funcionamiento general se basa en el complemento de Microsoft Lync VDI, pero funciona en una mayor variedad de sistemas operativos de cliente, incluidos el 10 de Windows, Macintosh y Linux. 
  
Una explicación completa de las características y tecnologías admitidas puede encontrarse en el sitio Web de VMWare en los siguientes vínculos:
  
- [What ' s New in VMware horizonte 7.4 &amp; cliente horizonte 4.7](https://blogs.vmware.com/euc/2018/01/vmware-horizon-7-4-horizon-client-4-7-whats-new.mdl)
    
- [Paquete de virtualización de horizonte de Skype para la empresa](https://www.vmware.com/products/horizon/skype-for-business.mdl)
    
- [Microsoft Skype para la empresa con VMWare horizonte](https://www.vmware.com/content/dam/digitalmarketing/vmware/en/pdf/products/horizon/vmware-skype-for-business-solution-brief.pdf)
    
## <a name="microsofts-lync-vdi-plug-in"></a>Complemento Lync VDI de Microsoft
<a name="Citrix_RT"> </a>

Con la solución de complemento de Microsoft Lync VDI, el usuario tiene que estar en un equipo de Windows o un cliente ligero y tener de Microsoft Lync VDI plugin instalada para administrar las secuencias de audio y vídeo desde el cliente en el escritorio virtual. Los usuarios harán lo siguiente:
  
1. Conectar el dispositivo de audio o vídeo (como un auricular o una cámara) con un equipo local.
    
2. Conectarse a un escritorio virtual remoto con Lync 2013 o Skype para cliente empresarial 2015.
    
3. Escriba las credenciales de Skype para la empresa en el escritorio virtual.
    
4. Volver a escribir las credenciales de usuario para establecer una conexión con el complemento en el equipo local de Windows o un cliente ligero de VDI de Lync.
    
Una vez establecida una conexión, el usuario está listo para realizar y recibir llamadas de audio y vídeo. El tráfico en la red y la carga en el escritorio virtual se ven minimizados, dado que el equipo local administra el procesamiento de audio y vídeo.
  
Complemento Lync VDI de Microsoft solo es compatible con algunos sistemas operativos Windows y sólo es compatible con Lync 2013 o Skype para clientes empresariales 2015. Consulte [Tecnologías de virtualización compatibles y limitaciones conocidas](vdi-environments.md#Supported_virt) para obtener más información sobre las tecnologías admitidas y las limitaciones.
  
Consulte los siguientes vínculos para obtener más información:
  
- [Tecnologías de virtualización admitidas y limitaciones comunes](vdi-environments.md#Supported_virt)
    
- [Requisitos previos del complemento Lync VDI](vdi-environments.md#VDI_prereq)
    
- [Implementación del complemento Lync VDI con Skype para Business Server](../../deploy/deploy-clients/deploy-the-lync-vdi-plug-in.md)
    
- Artículo del centro de conocimientos de Citrix [CTX138408](https://support.citrix.com/article/CTX138408)
    
El complemento de VDI de Microsoft está disponible en el [complemento de Microsoft Lync VDI 2013 (32 bits)](https://www.microsoft.com/en-us/download/details.aspx?id=35457) o el [complemento de VDI de Microsoft Lync 2013 (64 bits)](https://www.microsoft.com/en-us/download/details.aspx?id=35454). Este complemento es compatible con la Skype para cliente empresarial 2015, a pesar del nombre.
  
### <a name="supported-virtualization-technologies-and-known-limitations"></a>Tecnologías de virtualización admitidas y limitaciones comunes
<a name="Supported_virt"> </a>

El complemento de VDI Lync permite audio y vídeo de llamada de tecnologías de virtualización compatibles. Conforme a las normativas estándar para teléfonos, también se incluye compatibilidad con E911. En las secciones siguientes se describen las tecnologías de virtualización que son compatibles con el complemento VDI de Lync y las limitaciones de características conocidas.
  
#### <a name="support-for-virtualization-technologies"></a>Soporte de tecnologías de virtualización

El complemento de VDI Lync admite sesiones remotas escritorio completo en el escenario de escritorio virtual personal, pero no en el escenario de sesión de escritorio remoto. Estos entornos pueden describirse así:
  
- **Admitido: escritorios virtuales personalizados o infraestructura de escritorio virtual (VDI).** En esta situación, cada usuario inicia sesión en un escritorio virtual personalizable y puede guardar archivos en el escritorio, que se conservan entre sesiones. Servicios de escritorio remoto de Microsoft y VMware horizonte vista son implementaciones de ejemplo que se han probado para su uso con Skype para profesionales de 2015. Otras implementaciones en etapa de validación incluyen Citrix XenDesktop. Para obtener información acerca de los entornos de VDI específica del proveedor y el hardware de cliente que se han probado por Microsoft, vea [infraestructura compatibles con Microsoft Lync](https://go.microsoft.com/fwlink/?LinkID=313435).
    
- **No admitido: sesiones de Escritorio remoto.** En esta situación, cada usuario inicia sesión en una sesión de escritorio virtual genérica que no puede personalizarse. Algunos ejemplos son las sesiones de escritorio remoto (RDSH) de Microsoft y Citrix XenApp combinar con Citrix receptor.
    
El complemento Lync VDI no es compatible con otras tecnologías de virtualización, como la virtualización de aplicaciones, lo que permite el uso de una aplicación sin requerir la instalación de la aplicación completa localmente. Algunos ejemplos de implementaciones son Citrix XenApp y Microsoft Application Virtualization (App-V). El streaming de aplicaciones, la comunicación remota de aplicaciones y los modos mixtos de virtualización (por ejemplo, la comunicación remota de aplicaciones en la comunicación remota de escritorio completa) no se admiten.
  
El complemento de VDI Lync se diseñó para usar API independiente de la plataforma denominadas dinámicos Virtual canales (DVCs). En el caso de entornos que no se admiten de forma explícita, consulte las instrucciones de compatibilidad del proveedor de la solución de VDI.
  
#### <a name="lync-vdi-plug-in-prerequisites"></a>Requisitos previos del componente de VDI de Lync
<a name="VDI_prereq"> </a>

En un entorno VDI, las máquinas virtuales y el equipo del usuario local deben cumplir los requisitos descritos en esta sección.
  
> [!NOTE]
>  Su proveedor de soluciones de virtualización puede brindarle información sobre la instalación y la implementación del entorno. Para obtener información general sobre la implementación de un entorno virtualizado basado en Hyper-V y servicios de escritorio remoto, vea los siguientes artículos en Microsoft Library: [Hyper-V](https://go.microsoft.com/fwlink/p/?linkid=247514), [Servicios de escritorio remoto en Windows Server 2008 R2](https://go.microsoft.com/fwlink/p/?linkid=247513) 
  
Máquinas virtuales debe configurarse con Windows 8, Windows 7 o Windows Server 2008 R2 con el service Pack más recientes.
  
El equipo del usuario local debe cumplir los siguientes requisitos:
  
- El usuario debe estar alojado en Skype para Business Server o Lync Server 2013.
    
- El equipo local debe ejecutar Windows Embedded Standard 7 con SP1, Windows 7 con SP1 o Windows 8.
    
- Si está usando Servicios de escritorio remoto, elija el 32 bits o 64 bits Lync VDI Plug-in para que coincida con el sistema operativo del equipo local. No se requiere que tanto el equipo local como la máquina virtual tengan sistemas operativos de 32 o 64 bits. Si utiliza otra solución o plataforma de virtualización, consulte los requisitos de su proveedor.
    
- El equipo local debe ejecutar la [versión más reciente del cliente de escritorio remoto](https://go.microsoft.com/fwlink/p/?LinkId=268032). Instale las últimas actualizaciones del cliente de los Servicios de Escritorio remoto de Microsoft o el último software de cliente de escritorio remoto del proveedor de soluciones de virtualización. 
    
- En el equipo local, configure el cliente de escritorio remoto para que el audio se reproduzca en el equipo local y la grabación remota esté deshabilitada. Para configurar estas opciones de conexión a Escritorio remoto en Windows, vea la siguiente sección, "para configurar la conexión a Escritorio remoto." 
    
El complemento de VDI de Microsoft está disponible en el [complemento de Microsoft Lync VDI 2013 (32 bits)](https://www.microsoft.com/en-us/download/details.aspx?id=35457) o el [complemento de VDI de Microsoft Lync 2013 (64 bits)](https://www.microsoft.com/en-us/download/details.aspx?id=35454).
  
#### <a name="known-feature-limitations"></a>Limitaciones comunes de la funciones
<a name="VDI_prereq"> </a>

Los siguientes son conocidos limitaciones cuando se usa el Skype para cliente de 2015 empresarial en un entorno VDI:
  
No hay compatibilidad limitada para las características de delegación de llamada y Anonymization de agente de grupo de respuesta.
  
No se admiten estas características:
  
- Las páginas de ajuste del dispositivo de audio y de vídeo integrados.
    
- El vídeo de múltiples vistas.
    
- La grabación de las conversaciones.
    
- Unirse a reuniones de forma anónima (es decir, que se unen a Skype para reuniones de negocios hospedadas por una organización que no podrá federarse con su organización).
    
- Uso del complemento junto con un dispositivo de Lync Phone Edition Lync VDI.
    
- La continuación de llamadas en caso de una interrupción de la red.
    
- Las características de tonos de llamada personalizados y de música en espera.
    
El complemento de VDI Lync no se admite en un entorno de Office 365.
  
> [!NOTE]
> Citrix RealTime Optimization Pack admite Office 365. Para entornos virtuales basados en Citrix, revise la documentación de [Información general técnica](https://docs.citrix.com/en-us/hdx-optimization/2-0/hdx-realtime-optimization-pack-about.mdl) de Citrix para la lista de características admitidas y versiones.
  
## <a name="see-also"></a>Vea también
<a name="Citrix_RT"> </a>

[Implementación del complemento Lync VDI con Skype para Business Server](../../deploy/deploy-clients/deploy-the-lync-vdi-plug-in.md)

