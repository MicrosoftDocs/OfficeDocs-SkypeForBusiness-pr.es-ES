---
title: Instalar la Herramienta de planeación en Skype Empresarial Server 2015
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 4/5/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b95b3301-fa1e-4b96-9af4-05b43d39db8d
description: Antes de empezar a diseñar y planear su Skype para la infraestructura de servidor de negocios 2015 utilizando el Skype para la herramienta de planeación de 2015 Business Server, primero debe instalar la herramienta de planeación. La herramienta de planeación no deben implementarse una estación de trabajo o servidor que forma parte del dominio o infraestructura donde planea instalar Skype para Business Server 2015. El archivo Léame que acompaña a la herramienta de planeación detalla información importante sobre la instalación y el uso de la herramienta. Se ha duplicado aquí una parte de la información del archivo Léame para mayor claridad.
ms.openlocfilehash: 1c5c56031890aaff035e237e2ff7ab6d89d6ba2b
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="install-the-planning-tool-in-skype-for-business-server-2015"></a>Instalar la Herramienta de planeación en Skype Empresarial Server 2015
 
Antes de empezar a diseñar y planear su Skype para la infraestructura de servidor de negocios 2015 utilizando el Skype para la herramienta de planeación de 2015 Business Server, primero debe instalar la herramienta de planeación. La herramienta de planeación no deben implementarse una estación de trabajo o servidor que forma parte del dominio o infraestructura donde planea instalar Skype para Business Server 2015. El archivo Léame que acompaña a la herramienta de planeación detalla información importante sobre la instalación y el uso de la herramienta. Se ha duplicado aquí una parte de la información del archivo Léame para mayor claridad.
  
> [!IMPORTANT]
> La herramienta de planeación requiere instalación por un usuario con derechos de administrador y permisos en el equipo en el que se va a instalar la herramienta. 
  
Los sistemas operativos compatibles para la instalación y el funcionamiento de la herramienta de planeación son:
  
- Windows 10 
    
- Windows 8
    
- Windows 8.1
    
- Windows Server 2012
    
- Windows Server 2012 R2
    
- Edición de 32 bits de Windows 7
    
- Edición de 64 bits de Windows 7 usando Windows en Win32 (WOW)
    
- Windows Server 2008 R2 usando WOW
    
Además, la herramienta de planeación requiere Microsoft.NET Framework 4.5.
  
Una vez cumplidos los requisitos de preinstalación, a continuación, puede instalar la herramienta de planeación.
  
## 

### <a name="to-install-the-planning-tool"></a>Para instalar la Herramienta de planeación

1. Inicie sesión en el equipo local como miembro del grupo Administradores.
    
2. Mediante el Explorador de Windows o una ventana de comandos, busque el directorio donde descargó los archivos de instalación de la herramienta de planeación.
    
3. Busque el archivo SkypeForBusinessPlanningTool.msi. En el Explorador de Windows, haga doble clic en el archivo. En la ventana de línea de comandos, escriba el nombre del archivo y presione **Entrar** para ejecutarlo.
    
4. En la página principal del **Asistente para la instalación de la herramienta de planeación de Skype Empresarial Server 2015**, haga clic en **Siguiente**.
    
5. Lea el **Contrato de licencia para el usuario final**, seleccione **Acepto los términos del contrato de licencia**, si quiere aceptar los términos de uso del contrato de licencia, y haga clic en **Siguiente**.
    
6. Elija dónde quiere instalar los archivos de la Herramienta de planeación. La ubicación predeterminada es C:\Program Files (x86)\Skype for Business Server 2015\Planning Tool. Si desea cambiar la ubicación de instalación, haga clic en **Cambiar**. En **Cambiar carpeta de destino**, busque o escriba la ubicación donde desea instalar los archivos. Después, haga clic en **Aceptar** y en **Siguiente**.
    
7. El programa de instalación está preparado para instalar la herramienta de planeación. Haga clic en **Instalar** para comenzar el proceso de instalación.
    
8. La instalación se iniciará y se mostrará el progreso de la misma. Una vez completado el proceso de instalación, haga clic en **Finalizar**.
    
9. La herramienta de planeación está lista para su uso.
    
## <a name="optional-software"></a>Optional Software
<a name="Optional_Software"> </a>

El Skype para la herramienta de planeación de 2015 Business Server está diseñado para exportar a Microsoft Excel y Microsoft Visio. Mientras que estas aplicaciones no son necesarias para el funcionamiento de la herramienta de planeación, agreguen un valor significativo para la instalación y la documentación del diseño.
  
### <a name="microsoft-excel"></a>Microsoft Excel

La exportación de su diseño a Microsoft Excel genera un informe con cuatro pestañas en la hoja de cálculo:
  
- Resumen: muestra información sobre la configuración del sitio, incluyendo información de perfil de servidor, configuración de capacidad y recuento de usuarios.
    
- Perfil de hardware - muestra un informe con las configuraciones de hardware recomendadas para servidores que se especifican en la topología, incluidos CPU, memoria, disco e interfaz de red. También contempla la cantidad y las especificaciones recomendadas para los componentes de servidor. De igual modo, cada servidor está definido por el sitio para proporcionar una representación completa de los requisitos del servidor por sitio.
    
- Requisitos de puertos: muestra un informe de todos los puertos están habilitados y la asociación (DNS LB) de equilibrio de carga de sistema de nombres de dominio y equilibradores de carga de hardware (HLB). Este informe es útil para planear las configuraciones de DNS LB y HLB y del firewall.
    
- Resumen: muestra el resumen general de los ajustes que sean necesarios para configurar la red del servidor perimetral.
    
- Informe de certificados - muestra el nombre del sujeto y los nombres alternativos de asunto que se requieren para los certificados necesarios para obtener los servidores Edge.
    
- Informe - muestra los puertos de origen y de destino y direcciones IP para las interfaces externas e internas del firewall.
    
- Informe DNS - muestra el nombre de dominio completo (FQDN) y direcciones IP/VIP requerido por cada entrada DNS que cree.
    
### <a name="microsoft-visio"></a>Microsoft Visio

La exportación del diseño a Microsoft Visio genera un diagrama para su uso en fines de documentación de la topología y la infraestructura configuradas. El diagrama importado se puede modificar y reorganizar para adaptarlo a sus necesidades de documentación. El típico diagrama de Visio incluirá:
  
> [!NOTE]
> Si el diseño es lo suficientemente grande como para requerir más de tres servidores frontales, se creará una página adicional para el grupo de Front-End, servidores frontales, el equipo que ejecuta SQL Server, direcciones IP y nombres de dominio completos. 
  
- Topología global - diagrama de Skype configurado para sitios de Business Server 2015.
    
- Ficha nombre de sitio: muestra la topología de configuración del sitio con el servidor perimetral, firewall, public switched teléfono red (PSTN) con puertas de enlace y la implementación de servidor interno. Implementación interna consta de servidores configurados y agrupaciones de grupos, incluyendo el Front-End, servidores basados en SQL Server, servicios de dominio de Active Directory, directores, servidores de Exchange Unified Messaging (UM) servidores, servidores de buzones de Exchange, Office Web Apps, Servidores de mediación y los servidores de charla persistente.
    
- Diagrama de red: diagrama que detalla la configuración de servidor perimetral con las direcciones IP y los FQDN asociado del borde. El equilibrio de carga de DNS y los equilibradores de carga de hardware también están incluidos. Además, el grupo de servidor Front-End o Front-End y directores se muestran, con LB de DNS asociado o HLB y la dirección IP asignada (la herramienta de planeación es compatible con direcciones IPv4 e IPv6) y FQDN.
    
## <a name="see-also"></a>Vea también
<a name="Optional_Software"> </a>

#### 

[Instalación de la herramienta de planificación](http://technet.microsoft.com/library/ebdc9e26-4b22-4b02-85b9-7462bcfe7c93.aspx)

