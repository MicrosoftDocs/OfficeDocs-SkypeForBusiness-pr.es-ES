---
title: Requisitos previos y configuración de la herramienta Stress and Performance de Skype Empresarial
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
ms.date: 12/20/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 948c176c-75ce-418d-891a-a68427d61e40
description: Requisitos o requisitos previos de la herramienta Stress and Performance de Skype Empresarial Server 2015. Cómo se instala o se configura la herramienta Stress and Performance.
ms.openlocfilehash: 840891a7a356866755e89a7ef63e23fb62bfa12f
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30895093"
---
# <a name="prerequisites-and-setup-for-the-skype-for-busines-stress-and-performance-tool"></a>Requisitos previos y configuración de la herramienta Stress and Performance de Skype Empresarial
 
Requisitos o requisitos previos de la herramienta Stress and Performance de Skype Empresarial Server 2015. Cómo se instala o se configura la herramienta Stress and Performance.
  
Antes de ejecutar la herramienta Stress and Performance, debe tener en cuenta las siguientes secciones de requisitos de hardware, software y configuración del sistema:
  
- [Requisitos de hardware del cliente](prerequisites-and-setup.md#ClientHardwareReqs)
    
- [Requisitos de software del cliente](prerequisites-and-setup.md#ClientSoftwareReqs)
    
- [Requisitos de configuración](prerequisites-and-setup.md#ConfigReqs)
    
Además, a continuación se incluye una sección sobre la [Instalación de la herramienta Stress and Performance de Skype Empresarial Server 2015](prerequisites-and-setup.md#Installing)
  
## <a name="client-hardware-requirements"></a>Requisitos de hardware del cliente
<a name="ClientHardwareReqs"> </a>

Cuando se disponga a ejecutar la herramienta Stress and Performance en su implementación de Skype Empresarial Server 2015, tendrá que cumplir, al menos, estos requisitos de hardware por cada 4.500 usuarios que haya en la prueba:
  
- Adaptador de red de 1 gigabit
    
- 8 GB de memoria RAM
    
- 2 CPU de doble núcleo
    
## <a name="client-software-requirements"></a>Requisitos de software del cliente
<a name="ClientSoftwareReqs"> </a>

Los sistemas operativos compatibles con la herramienta Stress and Performance son los siguientes:
  
- Windows Server 2012
    
- Windows Server 2008 (64 bits)
    
Además, los equipos deben cumplir los siguientes requisitos de software:
  
- Tendrá que tener instalado Microsoft .NET 4.5 Framework. [Descargar la 4.5 de .net Framework aquí.](https://www.microsoft.com/en-us/download/details.aspx?id=30653)
    
- Deberá tener habilitada la característica Experiencia de escritorio en Windows.
    
- Tendrá que tener instalado Microsoft Visual C++ 2013 (x64). [Descargar aquí 2013 de Visual C++](https://www.microsoft.com/en-us/download/details.aspx?id=40784)
    
- Va a necesitar que Skype Empresarial Server 2015 esté correctamente implementado.
    
## <a name="configuration-requirements"></a>Requisitos de configuración
<a name="ConfigReqs"> </a>

Para que la herramienta Stress and Performance se ejecute correctamente, necesitará aplicar estas configuraciones adicionales:
  
- Tiene que iniciar sesión en el servidor como miembro del grupo del administrador local o de dominio.
    
- No se puede instalar la herramienta de creación de usuarios de Skype Empresarial Server 2015 (UserProvisioningTool.exe) en un servidor front-end o un servidor Standard Edition en el que residirán las cuentas de usuario.
    
- Cuando la herramienta de creación de usuarios se ejecuta varias veces, cada uno de los usuarios que está habilitado para Microsoft Unified Communications deberá tener un número de teléfono exclusivo.
    
- El tamaño del archivo de paginación lo debe administrar el sistema; de lo contrario, tendría que tener al menos 1,5 veces la cantidad de RAM del sistema del equipo.
    
## <a name="installing-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Instalación de la herramienta Stress and Performance de Skype Empresarial Server 2015
<a name="Installing"> </a>

La instalación no podía ser más sencilla. Tiene que ejecutar el archivo de Windows Installer, **CapacityPlanningTool.msi**, en cada equipo cliente que vaya a usar para simular el tráfico de usuarios y en el servidor front-end de cada grupo donde vaya a crear usuarios y contactos.
  
Para descargar el archivo .msi, junto con las secuencias de comandos de ejemplo que se mencionan en nuestros otros artículos, vaya al vínculo Centro de descarga: [Skype para Business Server 2015, Stress and Performance Tool](https://www.microsoft.com/download/details.aspx?id=50367).
  

