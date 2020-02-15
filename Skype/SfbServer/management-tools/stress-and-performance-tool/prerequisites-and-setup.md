---
title: Requisitos previos y configuración de la herramienta stress and performance de Skype empresarial
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
ms.date: 12/20/2018
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 948c176c-75ce-418d-891a-a68427d61e40
description: Requisitos o requisitos previos para la herramienta de esfuerzo y rendimiento de Skype empresarial Server 2015. Cómo instalar o configurar la herramienta stress and performance.
ms.openlocfilehash: 9389feedb21948604b1ea68319c5fc068a561679
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2020
ms.locfileid: "42005985"
---
# <a name="prerequisites-and-setup-for-the-skype-for-busines-stress-and-performance-tool"></a>Requisitos previos y configuración de la herramienta stress and performance de Skype empresarial
 
Requisitos o requisitos previos para la herramienta de esfuerzo y rendimiento de Skype empresarial Server 2015. Cómo instalar o configurar la herramienta stress and performance.
  
Tenemos las siguientes secciones de requisitos de configuración de hardware, software y sistema que debe conocer antes de ejecutar la herramienta stress and Performance:
  
- [Requisitos de hardware del cliente](prerequisites-and-setup.md#ClientHardwareReqs)
    
- [Requisitos de software del cliente](prerequisites-and-setup.md#ClientSoftwareReqs)
    
- [Requisitos de configuración](prerequisites-and-setup.md#ConfigReqs)
    
Además, también tenemos una sección a continuación para [instalar la herramienta de esfuerzo y rendimiento de Skype empresarial Server 2015](prerequisites-and-setup.md#Installing)
  
## <a name="client-hardware-requirements"></a>Requisitos de hardware del cliente
<a name="ClientHardwareReqs"> </a>

Al ejecutar la herramienta stress and performance en su implementación de Skype empresarial Server 2015, tendrá que cumplir, como mínimo, estos requisitos de hardware para cada 4500 usuarios de la prueba:
  
- adaptador de red de 1 Gigabit
    
- 8 GB de RAM
    
- 2 CPUs de doble núcleo
    
## <a name="client-software-requirements"></a>Requisitos de software del cliente
<a name="ClientSoftwareReqs"> </a>

Los sistemas operativos compatibles con la herramienta stress and Performance son los siguientes:
  
- Windows Server 2012
    
- Windows Server 2008 (64 bits)
    
Además, los equipos deben cumplir con los siguientes requisitos de software:
  
- Necesitará Microsoft .NET 4,5 Framework instalado. [Descargue .net 4,5 Framework aquí.](https://www.microsoft.com/download/details.aspx?id=30653)
    
- Necesitará la característica experiencia de escritorio habilitada en Windows.
    
- Necesitará Microsoft Visual C++ 2013 (x64) instalado. [Descargue Visual C++ 2013 aquí](https://www.microsoft.com/download/details.aspx?id=40784)
    
- Necesitará que Skype empresarial Server 2015 se haya implementado correctamente.
    
## <a name="configuration-requirements"></a>Requisitos de configuración
<a name="ConfigReqs"> </a>

Necesitará estas configuraciones adicionales para ejecutar la herramienta stress and Performance correctamente:
  
- Debe iniciar sesión en el servidor como miembro del grupo del administrador local o del dominio.
    
- No puede instalar la herramienta de creación de usuarios de Skype empresarial Server 2015 (UserProvisioningTool. exe) en cualquier servidor front-end o servidor Standard Edition en el que residirán las cuentas de usuario.
    
- Cuando la herramienta de creación de usuarios se ejecuta varias veces, cada usuario que esté habilitado para las comunicaciones unificadas de Microsoft debe tener un número de teléfono único.
    
- El tamaño del archivo de paginación se debe administrar con los sistemas o, de lo contrario, debe ser al menos 1,5 veces la cantidad de RAM del sistema del equipo.
    
## <a name="installing-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Instalación de la herramienta de esfuerzo y rendimiento de Skype empresarial Server 2015
<a name="Installing"> </a>

La instalación no puede ser más sencilla. Tiene que ejecutar el archivo de Windows Installer, **CapacityPlanningTool. msi**, en cada equipo cliente que vaya a usar para simular el tráfico de usuarios y en un servidor front-end en cada grupo de servidores en el que creará usuarios y contactos.
  
Para descargar el. msi, junto con los scripts de ejemplo mencionados en nuestros otros artículos, vaya al vínculo centro de descarga: [Skype for Business Server 2015, herramienta stress and Performance](https://www.microsoft.com/download/details.aspx?id=50367).
  

