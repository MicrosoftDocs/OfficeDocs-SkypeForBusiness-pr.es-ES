---
title: Instalar la Herramienta de planeación en Skype Empresarial Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 4/5/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b95b3301-fa1e-4b96-9af4-05b43d39db8d
description: Antes de empezar a diseñar y planear la infraestructura de Skype empresarial Server 2015 con la herramienta de planeación de Skype empresarial Server 2015, primero debe instalar la herramienta de planeación. No es necesario implementar la herramienta de planeación en una estación de trabajo o servidor que forme parte del dominio o de la infraestructura donde se va a instalar Skype empresarial Server 2015. El archivo Léame que acompaña a la herramienta de planificación detalla información importante sobre la instalación y el uso de la herramienta. Se ha duplicado aquí una parte de la información del archivo Léame para mayor claridad.
ms.openlocfilehash: 192eae34bf6cf3fa53be82d8cb4450f960c90314
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279130"
---
# <a name="install-the-planning-tool-in-skype-for-business-server-2015"></a>Instalar la Herramienta de planeación en Skype Empresarial Server 2015

Antes de empezar a diseñar y planear la infraestructura de Skype empresarial Server 2015 con la herramienta de planeación de Skype empresarial Server 2015, primero debe instalar la herramienta de planeación. No es necesario implementar la herramienta de planeación en una estación de trabajo o servidor que forme parte del dominio o de la infraestructura donde se va a instalar Skype empresarial Server 2015. El archivo Léame que acompaña a la herramienta de planificación detalla información importante sobre la instalación y el uso de la herramienta. Se ha duplicado aquí una parte de la información del archivo Léame para mayor claridad.

> [!IMPORTANT]
> La herramienta de Planeación requiere la instalación de un usuario con derechos y permisos de administrador en el equipo en el que se va a instalar la herramienta.

Los sistemas operativos compatibles para la instalación y el funcionamiento de la herramienta de planificación son:

- Windows 10

- Windows 8

- Windows 8,1

- Windows Server 2012

- Windows Server 2012 R2

- Edición de 32 bits de Windows 7

- Edición de 64 bits de Windows 7 usando Windows en Win32 (WOW)

- Windows Server 2008 R2 usando WOW

Además, la herramienta de Planeación requiere Microsoft .NET Framework 4,5.

Después de que se cumplan los requisitos de preinstalación, puede instalar la herramienta de planeación.



## <a name="to-install-the-planning-tool"></a>Para instalar la Herramienta de planeación

1. Inicie sesión en el equipo local como miembro del grupo Administradores.

2. Con el explorador de Windows o una ventana de comandos, busque el directorio en el que ha descargado los archivos de instalación de la herramienta de planeación.

3. Busque el archivo SkypeForBusinessPlanningTool.msi. En el Explorador de Windows, haga doble clic en el archivo. En la ventana de línea de comandos, escriba el nombre del archivo y presione **Entrar** para ejecutarlo.

4. En la página principal del **Asistente para la instalación de la herramienta de planeación de Skype Empresarial Server 2015**, haga clic en **Siguiente**.

5. Lea el **Contrato de licencia para el usuario final**, seleccione **Acepto los términos del contrato de licencia**, si quiere aceptar los términos de uso del contrato de licencia, y haga clic en **Siguiente**.

6. Elija dónde quiere instalar los archivos de la Herramienta de planeación. La ubicación predeterminada es C:\Program Files (x86)\Skype for Business Server 2015\Planning Tool. Si desea cambiar la ubicación de instalación, haga clic en **Cambiar**. En **Cambiar carpeta de destino**, busque o escriba la ubicación donde desea instalar los archivos. Después, haga clic en **Aceptar** y en **Siguiente**.

7. El instalador ya está listo para instalar la herramienta de planeación. Haga clic en **Instalar** para comenzar el proceso de instalación.

8. La instalación se iniciará y se mostrará el progreso de la misma. Una vez completado el proceso de instalación, haga clic en **Finalizar**.

9. La herramienta de planeación está lista para usarse.

## <a name="optional-software"></a>Software opcional
<a name="Optional_Software"> </a>

La herramienta de planeación de Skype empresarial Server 2015 está diseñada para exportar a Microsoft Excel y Microsoft Visio. Si bien estas aplicaciones no son necesarias para el funcionamiento de la herramienta de planeación, pueden agregar valor significativo a la implementación y la documentación del diseño.

### <a name="microsoft-excel"></a>Microsoft Excel

La exportación de su diseño a Microsoft Excel genera un informe con cuatro pestañas en la hoja de cálculo:

- Resumen: muestra información sobre la configuración del sitio, incluidos el número de usuarios, la configuración de capacidad y la información de perfil del servidor.

- Perfil de hardware: muestra un informe de las configuraciones de hardware recomendadas para los servidores especificados en la topología, como la interfaz de CPU, memoria, disco e red. También contempla la cantidad y las especificaciones recomendadas para los componentes de servidor. De igual modo, cada servidor está definido por el sitio para proporcionar una representación completa de los requisitos del servidor por sitio.

- Requisitos de puertos: muestra un informe de todos los puertos que están habilitados y la asociación con el equilibrio de carga del sistema de nombres de dominio (DNS LB) y los equilibradores de carga de hardware (HLB). Este informe es útil para planear las configuraciones de DNS LB y HLB y del firewall.

- Informe Resumen: muestra el resumen general de la configuración necesaria para configurar la red del servidor perimetral.

- Informe de certificados: muestra el nombre del sujeto y los nombres alternativos de asunto necesarios para los certificados necesarios para obtener los servidores perimetrales.

- Informe de Firewall: muestra los puertos de origen y de destino, así como las direcciones IP de las interfaces externas e internas.

- Informe de DNS: muestra el nombre de dominio completo (FQDN) y las direcciones IP/VIP necesarias para cada entrada de DNS que cree.

### <a name="microsoft-visio"></a>Microsoft Visio

La exportación del diseño a Microsoft Visio genera un diagrama para su uso en fines de documentación de la topología y la infraestructura configuradas. El diagrama importado se puede modificar y reorganizar para adaptarlo a sus necesidades de documentación. El típico diagrama de Visio incluirá:

> [!NOTE]
> Si el diseño es lo suficientemente grande para requerir más de tres servidores front-end, se creará una página adicional para el grupo front-end, los servidores front-end, el equipo con SQL Server, las direcciones IP y los FQDN.

- Topología global: Diagrama de sitios configurados de Skype empresarial Server 2015.

- Ficha nombre del sitio: muestra la topología de configuración del sitio con servidor perimetral, firewall, red de telefonía pública conmutada (RTC) con puertas de enlace y la implementación de servidor interno. La implementación interna consta de servidores y grupos de servidores, entre los que se incluyen las secciones front end, los servidores basados en SQL Server, los servicios de dominio de Active Directory, los directores, los servidores de mensajería unificada de Exchange (UM), los servidores de buzón de Exchange y los servidores de Office Web Apps. Servidores de mediación y servidores de chat persistentes.

- Diagrama de red perimetral: diagrama que detalla la configuración del servidor perimetral con las direcciones IP y FQDN asociados. El equilibrio de carga de DNS y los equilibradores de carga de hardware también están incluidos. Además, se muestran los directores y el servidor front-end o el grupo front-end, con el DNS LB o HLB asociado y la dirección IP asignada (la herramienta de planeación admite direcciones IPv4 e IPv6) y FQDN.

## <a name="see-also"></a>Vea también
<a name="Optional_Software"> </a>

[Installing the Planning Tool](https://technet.microsoft.com/library/ebdc9e26-4b22-4b02-85b9-7462bcfe7c93.aspx)
