---
title: Instalar la Herramienta de planeación en Skype Empresarial Server 2015
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
description: Antes de empezar a diseñar y planear la infraestructura de Skype Empresarial Server 2015 mediante la Herramienta de planeación de Skype Empresarial Server 2015, primero debe instalar la Herramienta de planeación. No es necesario implementar la Herramienta de planeación en una estación de trabajo o servidor que forme parte del dominio o la infraestructura donde planea instalar Skype Empresarial Server 2015. El archivo Léame que acompaña a la Herramienta de planeación detalla información importante sobre la instalación y el uso de la herramienta. Alguna de la información del archivo Léame también aparece aquí por motivos de claridad.
ms.openlocfilehash: 902249e042694a37594c6dc0b753b0c1388c0729
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834730"
---
# <a name="install-the-planning-tool-in-skype-for-business-server-2015"></a>Instalar la Herramienta de planeación en Skype Empresarial Server 2015

Antes de empezar a diseñar y planear la infraestructura de Skype Empresarial Server 2015 mediante la Herramienta de planeación de Skype Empresarial Server 2015, primero debe instalar la Herramienta de planeación. No es necesario implementar la Herramienta de planeación en una estación de trabajo o servidor que forme parte del dominio o la infraestructura donde planea instalar Skype Empresarial Server 2015. El archivo Léame que acompaña a la Herramienta de planeación detalla información importante sobre la instalación y el uso de la herramienta. Alguna de la información del archivo Léame también aparece aquí por motivos de claridad.

> [!IMPORTANT]
> La Herramienta de planeación requiere la instalación por parte de un usuario con derechos y permisos de administrador en el equipo en el que se va a instalar la herramienta.

Los sistemas operativos admitidos para la instalación y el funcionamiento de la Herramienta de planeación son:

- Windows 10

- Windows 8

- Windows 8.1

- Windows Server 2012

- Windows Server 2012 R2

- Edición de 32 bits de Windows 7

- Edición de 64 bits de Windows 7 usando Windows en Win32 (WOW)

- Windows Server 2008 R2 usando WOW

Además, la Herramienta de planeación requiere Microsoft .NET Framework 4.5.

Una vez que se cumplen los requisitos de preinstalación, puede instalar la Herramienta de planeación.



## <a name="to-install-the-planning-tool"></a>Para instalar la Herramienta de planeación

1. Inicie sesión en el equipo local como miembro del grupo Administradores.

2. Con el Explorador de Windows o una ventana de comandos, busque el directorio donde descargó los archivos de instalación de la Herramienta de planeación.

3. Busque el SkypeForBusinessPlanningTool.msi. En el Explorador de Windows, haga doble clic en el archivo. En la ventana de comandos, escriba el nombre del archivo y, a continuación, presione **ENTRAR** para ejecutar el archivo.

4. En la página principal de **Skype Empresarial Server 2015,** Asistente para la configuración de la herramienta de planeación, haga clic **en Siguiente.**

5. Lea el **Contrato de licencia para el usuario final**, seleccione **Acepto los términos del contrato de licencia**, si quiere aceptar los términos de uso del contrato de licencia, y haga clic en **Siguiente**.

6. Elija donde quiere instalar los archivos de la Herramienta de planeación. La ubicación predeterminada es C:\Archivos de programa (x86)\Skype Empresarial Server 2015\Planning Tool. Si desea cambiar la ubicación de instalación, haga clic en **Cambiar**. En **Cambiar carpeta de destino**, busque o escriba la ubicación donde desea instalar los archivos; a continuación, haga clic en **Aceptar** y en **Siguiente**.

7. El instalador ya está listo para instalar la Herramienta de planeación. Haga clic en **Instalar** para comenzar el proceso de instalación.

8. La instalación se iniciará y se mostrará el progreso de la misma. Una vez completado el proceso de instalación, haga clic en **Finalizar**.

9. La Herramienta de planeación está lista para usarse.

## <a name="optional-software"></a>Software opcional
<a name="Optional_Software"> </a>

La Herramienta de planeación de Skype Empresarial Server 2015 está diseñada para exportar a Microsoft Excel y Microsoft Visio. Aunque estas aplicaciones no son necesarias para el funcionamiento de la Herramienta de planeación, sí agregan un valor significativo a la implementación y la documentación del diseño.

### <a name="microsoft-excel"></a>Microsoft Excel

Exportar el diseño a Microsoft Excel crea un informe que muestra siete pestañas en la hoja de cálculo:

- Resumen: muestra información sobre la configuración del sitio, incluido el recuento de usuarios, la configuración de capacidad y la información de perfil de servidor.

- Perfil de hardware: muestra un informe sobre las configuraciones de hardware recomendadas para los servidores especificados en la topología, incluida la CPU, la memoria, el disco y la interfaz de red. También se incluyen la cantidad y las especificaciones recomendadas para los componentes del servidor. Además, cada servidor se define por sitio para proporcionar una representación completa de los requisitos del servidor por sitio.

- Requisitos de puertos: muestra un informe de todos los puertos habilitados y la asociación con el equilibrio de carga del sistema de nombres de dominio (DNS LB) y los equilibradores de carga de hardware (HLB). Debe usar este informe para planear el firewall y las configuraciones de DNS LB y HLB.

- Informe de resumen: muestra el resumen general de la configuración necesaria para configurar la red del servidor perimetral.

- Informe de certificados: muestra el nombre de sujeto y los nombres alternativos de sujeto necesarios para los certificados necesarios para ejecutar los servidores perimetrales.

- Informe de firewall: muestra los puertos de origen y de destino y las direcciones IP para las interfaces externas e internas.

- Informe dns: muestra el nombre de dominio completo (FQDN) y las direcciones IP/VIP necesarias para cada entrada DNS que cree.

### <a name="microsoft-visio"></a>Microsoft Visio

Al exportar el diseño a Microsoft Visio, se crea un diagrama para usarlo en los fines de la documentación de la topología y la infraestructura configuradas. El diagrama importado se puede editar y reorganizar para satisfacer sus necesidades de documentación. El diagrama típico de Visio incluirá:

> [!NOTE]
> Si el diseño es lo suficientemente grande como para requerir más de tres servidores front-end, se creará una página adicional para el grupo de servidores front-end, los servidores front-end, el equipo que ejecuta SQL Server, las direcciones IP y los FQDN.

- Topología global: diagrama de sitios configurados de Skype Empresarial Server 2015.

- Pestaña Nombre del sitio: muestra la topología de configuración del sitio con el servidor perimetral, el firewall, la red telefónica conmutada (RTC) con puertas de enlace y la implementación del servidor interno. La implementación interna consta de servidores y grupos configurados, incluidos los grupos de servidores front-end, servidores basados en SQL Server, servicios de dominio de Active Directory, directores, servidores de mensajería unificada de Exchange, servidores de buzones de Exchange, servidores de Office Web Apps, servidores de mediación y servidores de chat persistente.

- Diagrama de red perimetral: diagrama que detalla la configuración del servidor perimetral con direcciones IP y FQDN asociados. También se incluyen equilibradores de carga de hardware y equilibrio de carga de DNS. Además, se muestran los directores y el servidor front-end o el grupo de servidores front-end, con la LB o HLB de DNS asociado y la dirección IP asignada (la Herramienta de planeación admite direcciones IPv4 e IPv6) y FQDN.

## <a name="see-also"></a>Vea también
<a name="Optional_Software"> </a>

[Instalación de la herramienta de planeación](https://technet.microsoft.com/library/ebdc9e26-4b22-4b02-85b9-7462bcfe7c93.aspx)
