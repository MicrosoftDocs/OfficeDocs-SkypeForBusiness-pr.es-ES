---
title: Instalar la herramienta de planeación en Skype Empresarial Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 4/5/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b95b3301-fa1e-4b96-9af4-05b43d39db8d
description: Antes de empezar a diseñar y planear la infraestructura de Skype Empresarial Server 2015 mediante la Herramienta de planeación de Skype Empresarial Server 2015, primero debe instalar la herramienta de planeación. La herramienta de planeación no necesita implementarse en una estación de trabajo o servidor que forme parte del dominio o la infraestructura donde tiene previsto instalar Skype Empresarial Server 2015. El archivo Léame que acompaña a la herramienta de planeación detalla información importante sobre la instalación y el uso de la herramienta. Alguna de la información del archivo Léame también aparece aquí por motivos de claridad.
ms.openlocfilehash: 29a3bd35191cf326cafd1f4ad4f14fab50e47ea3
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51122384"
---
# <a name="install-the-planning-tool-in-skype-for-business-server-2015"></a>Instalar la herramienta de planeación en Skype Empresarial Server 2015

Antes de empezar a diseñar y planear la infraestructura de Skype Empresarial Server 2015 mediante la Herramienta de planeación de Skype Empresarial Server 2015, primero debe instalar la herramienta de planeación. La herramienta de planeación no necesita implementarse en una estación de trabajo o servidor que forme parte del dominio o la infraestructura donde tiene previsto instalar Skype Empresarial Server 2015. El archivo Léame que acompaña a la herramienta de planeación detalla información importante sobre la instalación y el uso de la herramienta. Alguna de la información del archivo Léame también aparece aquí por motivos de claridad.

> [!IMPORTANT]
> La herramienta de planeación requiere la instalación de un usuario con derechos de administrador y permisos en el equipo en el que se va a instalar la herramienta.

Los sistemas operativos compatibles para la instalación y el funcionamiento de la herramienta de planeación son:

- Windows 10

- Windows 8

- Windows 8.1

- Windows Server 2012

- Windows Server 2012 R2

- Edición de 32 bits de Windows 7

- Edición de 64 bits de Windows 7 usando Windows en Win32 (WOW)

- Windows Server 2008 R2 usando WOW

Además, la herramienta de planeación requiere Microsoft .NET Framework 4.5.

Una vez que se cumplen los requisitos de preinstalación, puede instalar la herramienta de planeación.



## <a name="to-install-the-planning-tool"></a>Para instalar la Herramienta de planeación

1. Inicie sesión en el equipo local como miembro del grupo Administradores.

2. Con el Explorador de Windows o una ventana de comandos, busque el directorio donde descargó los archivos de instalación de la herramienta de planeación.

3. Busque el SkypeForBusinessPlanningTool.msi. En el Explorador de Windows, haga doble clic en el archivo. En la ventana de comandos, escriba el nombre del archivo y, a continuación, presione **ENTRAR** para ejecutar el archivo.

4. En la página de bienvenida de **Skype Empresarial Server 2015, Asistente** para la configuración de herramientas de planeación, haga clic en **Siguiente**.

5. Lea el **Contrato de licencia para el usuario final**, seleccione **Acepto los términos del contrato de licencia**, si quiere aceptar los términos de uso del contrato de licencia, y haga clic en **Siguiente**.

6. Elija donde quiere instalar los archivos de la Herramienta de planeación. La ubicación predeterminada es C:\Archivos de programa (x86)\Skype Empresarial Server 2015\Planning Tool. Si desea cambiar la ubicación de instalación, haga clic en **Cambiar**. En **Cambiar carpeta de destino**, busque o escriba la ubicación donde desea instalar los archivos; a continuación, haga clic en **Aceptar** y en **Siguiente**.

7. El instalador ya está listo para instalar la herramienta de planeación. Haga clic en **Instalar** para comenzar el proceso de instalación.

8. La instalación se iniciará y se mostrará el progreso de la misma. Una vez completado el proceso de instalación, haga clic en **Finalizar**.

9. La herramienta de planeación está lista para su uso.

## <a name="optional-software"></a>Software opcional
<a name="Optional_Software"> </a>

La herramienta de planeación de Skype Empresarial Server 2015 está diseñada para exportar a Microsoft Excel y Microsoft Visio. Aunque estas aplicaciones no son necesarias para el funcionamiento de la herramienta de planeación, sí agregan un valor significativo a la implementación y documentación del diseño.

### <a name="microsoft-excel"></a>Microsoft Excel

Al exportar el diseño a Microsoft Excel, se crea un informe que muestra siete pestañas en la hoja de cálculo:

- Resumen: muestra información sobre la configuración del sitio, incluido el recuento de usuarios, la configuración de capacidad y la información de perfil de servidor.

- Perfil de hardware: muestra un informe sobre las configuraciones de hardware recomendadas para los servidores especificados en la topología, incluida la CPU, la memoria, el disco y la interfaz de red. También se incluyen la cantidad y las especificaciones recomendadas para los componentes del servidor. Además, cada servidor se define por sitio para proporcionar una representación completa de los requisitos del servidor por sitio.

- Requisitos de puertos: muestra un informe de todos los puertos habilitados y la asociación al equilibrio de carga del sistema de nombres de dominio (DNS LB) y a los equilibradores de carga de hardware (HLB). Debe usar este informe para planear el firewall y las configuraciones de DNS LB y HLB.

- Informe de resumen: muestra el resumen general de la configuración necesaria para configurar la red del servidor perimetral.

- Informe de certificados: muestra el nombre del sujeto y los nombres alternativos de sujeto necesarios para los certificados necesarios para que se ejecuten los servidores perimetrales.

- Informe de firewall: muestra los puertos de origen y de destino y las direcciones IP para las interfaces externas e internas.

- Informe DNS: muestra el nombre de dominio completo (FQDN) y las direcciones IP/VIP necesarias para cada entrada DNS que cree.

### <a name="microsoft-visio"></a>Microsoft Visio

Al exportar el diseño a Microsoft Visio, se crea un diagrama para usarlo en los fines de documentación de la infraestructura y la topología configuradas. El diagrama importado se puede editar y reorganizar para satisfacer sus necesidades de documentación. El diagrama típico de Visio incluirá:

> [!NOTE]
> Si el diseño es lo suficientemente grande como para requerir más de tres servidores front-end, se creará una página adicional para el grupo de servidores front-end, los servidores front-end, el equipo que ejecuta SQL Server, direcciones IP y FQDN.

- Topología global: diagrama de sitios configurados de Skype Empresarial Server 2015.

- Pestaña Nombre del sitio: muestra la topología de configuración del sitio con servidor perimetral, firewall, red telefónica conmutada (RTC) con puertas de enlace e implementación del servidor interno. La implementación interna consta de servidores y grupos configurados, incluidos los grupos de servidores front-end, los servidores basados en SQL Server, los servicios de dominio de Active Directory, los directores, los servidores de mensajería unificada (MU) de Exchange, los servidores de buzones de Exchange, los servidores de Office Web Apps, los servidores de mediación y los servidores de chat persistente.

- Diagrama de red perimetral: diagrama que detalla la configuración del servidor perimetral con direcciones IP y FQDN asociados. También se incluyen equilibradores de carga dns y equilibradores de carga de hardware. Además, se muestran directores y el servidor front-end o grupo de servidores front-end, con DNS LB o HLB asociados y la dirección IP asignada (la Herramienta de planeación admite direcciones IPv4 e IPv6) y FQDN.

## <a name="see-also"></a>Ver también
<a name="Optional_Software"> </a>

[Instalación de la herramienta de planeación](/previous-versions/office/lync-server-2013/lync-server-2013-installing-the-planning-tool)