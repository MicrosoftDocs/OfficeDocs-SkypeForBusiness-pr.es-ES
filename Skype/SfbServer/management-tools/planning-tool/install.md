---
title: Instalar la Herramienta de planeación en Skype Empresarial Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 4/5/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b95b3301-fa1e-4b96-9af4-05b43d39db8d
description: Antes de empezar a diseñar y planear su Skype para infraestructura de Business Server 2015 mediante el uso de la Skype para la herramienta de planeación de Business Server 2015, primero debe instalar la herramienta de planeación. La herramienta de planeación no necesita implementarse en una estación de trabajo o servidor que forma parte de la infraestructura o el dominio donde va a instalar Skype para Business Server 2015. El archivo Léame que acompaña a la herramienta de planeación detalla información importante sobre la instalación y uso de la herramienta. Se ha duplicado aquí una parte de la información del archivo Léame para mayor claridad.
ms.openlocfilehash: 64d510eedc01149e7119e3ec92ea09cd9a6c842a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33915027"
---
# <a name="install-the-planning-tool-in-skype-for-business-server-2015"></a>Instalar la Herramienta de planeación en Skype Empresarial Server 2015

Antes de empezar a diseñar y planear su Skype para infraestructura de Business Server 2015 mediante el uso de la Skype para la herramienta de planeación de Business Server 2015, primero debe instalar la herramienta de planeación. La herramienta de planeación no necesita implementarse en una estación de trabajo o servidor que forma parte de la infraestructura o el dominio donde va a instalar Skype para Business Server 2015. El archivo Léame que acompaña a la herramienta de planeación detalla información importante sobre la instalación y uso de la herramienta. Se ha duplicado aquí una parte de la información del archivo Léame para mayor claridad.

> [!IMPORTANT]
> La herramienta de planeación requiere la instalación por un usuario con derechos de administrador y permisos en el equipo en el que la herramienta se van a instalar.

Los sistemas operativos admitidos para la instalación y el funcionamiento de la herramienta de planeación son:

- Windows 10

- Windows 8

- Windows 8,1

- Windows Server 2012

- Windows Server 2012 R2

- Edición de 32 bits de Windows 7

- Edición de 64 bits de Windows 7 usando Windows en Win32 (WOW)

- Windows Server 2008 R2 usando WOW

Además, la herramienta de planeación requiere Microsoft .NET Framework 4.5.

Después de que se cumplen los requisitos de preinstalación, a continuación, puede instalar la herramienta de planeación.



## <a name="to-install-the-planning-tool"></a>Para instalar la Herramienta de planeación

1. Inicie sesión en el equipo local como miembro del grupo Administradores.

2. Mediante el Explorador de Windows o una ventana de comandos, busque el directorio donde descargó los archivos de instalación de la herramienta de planeación.

3. Busque el archivo SkypeForBusinessPlanningTool.msi. En el Explorador de Windows, haga doble clic en el archivo. En la ventana de línea de comandos, escriba el nombre del archivo y presione **Entrar** para ejecutarlo.

4. En la página principal del **Asistente para la instalación de la herramienta de planeación de Skype Empresarial Server 2015**, haga clic en **Siguiente**.

5. Lea el **Contrato de licencia para el usuario final**, seleccione **Acepto los términos del contrato de licencia**, si quiere aceptar los términos de uso del contrato de licencia, y haga clic en **Siguiente**.

6. Elija dónde quiere instalar los archivos de la Herramienta de planeación. La ubicación predeterminada es C:\Program Files (x86)\Skype for Business Server 2015\Planning Tool. Si desea cambiar la ubicación de instalación, haga clic en **Cambiar**. En **Cambiar carpeta de destino**, busque o escriba la ubicación donde desea instalar los archivos. Después, haga clic en **Aceptar** y en **Siguiente**.

7. El programa de instalación ahora está listo para instalar la herramienta de planeación. Haga clic en **Instalar** para comenzar el proceso de instalación.

8. La instalación se iniciará y se mostrará el progreso de la misma. Una vez completado el proceso de instalación, haga clic en **Finalizar**.

9. La herramienta de planeación está lista para su uso.

## <a name="optional-software"></a>Software opcional
<a name="Optional_Software"> </a>

El Skype para la herramienta de planeación de Business Server 2015 está diseñado para exportar a Microsoft Excel y Microsoft Visio. Mientras que estas aplicaciones no son necesarias para el funcionamiento de la herramienta de planeación, agreguen un valor significativo para la implementación y la documentación de su diseño.

### <a name="microsoft-excel"></a>Microsoft Excel

La exportación de su diseño a Microsoft Excel genera un informe con cuatro pestañas en la hoja de cálculo:

- Resumen: muestra información sobre la configuración del sitio, incluida información de perfil de servidor, la configuración de capacidad y recuento de usuarios.

- Perfil de hardware - muestra un informe en las configuraciones de hardware recomendado para los servidores que se especifican en la topología, incluida la interfaz de red, memoria, disco y CPU. También contempla la cantidad y las especificaciones recomendadas para los componentes de servidor. De igual modo, cada servidor está definido por el sitio para proporcionar una representación completa de los requisitos del servidor por sitio.

- Requisitos de puertos: muestra un informe de todos los puertos que están habilitados y la asociación a (DNS kg) de equilibrio de carga de sistema de nombres de dominio y los equilibradores de carga de hardware (HLB). Este informe es útil para planear las configuraciones de DNS LB y HLB y del firewall.

- Informe de resumen - muestra el resumen general de la configuración que son necesarios para configurar la red del servidor perimetral.

- Informe de certificados - muestra el nombre de sujeto y los nombres alternativos de sujeto que son necesarios para los certificados necesarios para obtener los servidores perimetrales que ejecutan.

- Firewall informe - muestra los puertos de origen y destino y direcciones IP para interfaces externas e internas.

- Informe de DNS - muestra el nombre de dominio completo (FQDN) y las direcciones IP/VIP necesitan para cada entrada DNS que cree.

### <a name="microsoft-visio"></a>Microsoft Visio

La exportación del diseño a Microsoft Visio genera un diagrama para su uso en fines de documentación de la topología y la infraestructura configuradas. El diagrama importado se puede modificar y reorganizar para adaptarlo a sus necesidades de documentación. El típico diagrama de Visio incluirá:

> [!NOTE]
> Si su diseño es lo suficientemente grande como para requerir más de tres servidores Front-End, se creará una página adicional para el grupo de Front-End, servidores Front-End, el equipo que ejecuta SQL Server, las direcciones IP y nombres de dominio completos.

- Topología global: diagrama de Skype configurado para los sitios de Business Server 2015.

- Ficha de nombre de sitio - muestra la topología de configuración de sitios con servidor perimetral, firewall, pública conmutada (RTC) de red con puertas de enlace y la implementación de servidor interno de teléfono. Implementación interna está compuesta por servidores configurados y grupos de los grupos de servidores, incluidos el Front-End, servidores basados en SQL Server, servicios de dominio de Active Directory, directores, servidores de aplicaciones de mensajería unificada de Exchange (UM) servidores, servidores de buzón de correo de Exchange, Office Web, Los servidores de mediación y servidores de Chat persistente.

- Diagrama de red: diagrama que detalla la configuración del servidor perimetral con direcciones IP y los nombres de dominio completos asociados de bordes. El equilibrio de carga de DNS y los equilibradores de carga de hardware también están incluidos. Además, los directores y el grupo de servidores Front-End o de servidor Front-End se muestran, con asociados kg de DNS o HLB y la dirección IP asignada (la herramienta de planeación es compatible con direcciones IPv4 e IPv6) y del FQDN.

## <a name="see-also"></a>Vea también
<a name="Optional_Software"> </a>

[Installing the Planning Tool](https://technet.microsoft.com/library/ebdc9e26-4b22-4b02-85b9-7462bcfe7c93.aspx)
