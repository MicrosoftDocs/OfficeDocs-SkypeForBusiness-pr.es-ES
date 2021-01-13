---
title: Requisitos previos y configuración de la Herramienta de esfuerzo y rendimiento de Skype Empresarial
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: Requisitos o requisitos previos para la Herramienta de esfuerzo y rendimiento de Skype Empresarial Server 2015. Cómo instalar o configurar la Herramienta de esfuerzo y rendimiento.
ms.openlocfilehash: a58eb5e291878bea74365cd1b9519983c7a77a84
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814960"
---
# <a name="prerequisites-and-setup-for-the-skype-for-busines-stress-and-performance-tool"></a>Requisitos previos y configuración de la Herramienta de esfuerzo y rendimiento de Skype Empresarial
 
Requisitos o requisitos previos para la Herramienta de esfuerzo y rendimiento de Skype Empresarial Server 2015. Cómo instalar o configurar la Herramienta de esfuerzo y rendimiento.
  
Tenemos las siguientes secciones de requisitos de configuración de hardware, software y sistema que deberá conocer antes de ejecutar la Herramienta de esfuerzo y rendimiento:
  
- [Requisitos de hardware de cliente](prerequisites-and-setup.md#ClientHardwareReqs)
    
- [Requisitos de software de cliente](prerequisites-and-setup.md#ClientSoftwareReqs)
    
- [Requisitos de configuración](prerequisites-and-setup.md#ConfigReqs)
    
Además, también tenemos una sección a continuación para instalar la Herramienta de esfuerzo y rendimiento de [Skype Empresarial Server 2015](prerequisites-and-setup.md#Installing)
  
## <a name="client-hardware-requirements"></a>Requisitos de hardware de cliente
<a name="ClientHardwareReqs"> </a>

Al ejecutar la Herramienta de esfuerzo y rendimiento en su implementación de Skype Empresarial Server 2015, necesitará, como mínimo, que se cumplen estos requisitos de hardware por cada 4500 usuarios en su prueba:
  
- Adaptador de red de 1 gigabit
    
- 8 GB de RAM
    
- 2 CPU de doble núcleo
    
## <a name="client-software-requirements"></a>Requisitos de software de cliente
<a name="ClientSoftwareReqs"> </a>

Los sistemas operativos compatibles con la herramienta Stress and Performance son:
  
- Windows Server 2012
    
- Windows Server 2008 (64 bits)
    
Además, los equipos deben cumplir los siguientes requisitos de software:
  
- Necesitará microsoft .NET 4.5 Framework instalado. [Descargue .Net 4.5 Framework aquí.](https://www.microsoft.com/download/details.aspx?id=30653)
    
- Necesitarás la característica Experiencia de escritorio habilitada en Windows.
    
- Necesitarás que Microsoft Visual C++ 2013 (x64) esté instalado. [Descarga Visual C++ 2013 aquí](https://www.microsoft.com/download/details.aspx?id=40784)
    
- Necesitará que Skype Empresarial Server 2015 se implemente correctamente.
    
## <a name="configuration-requirements"></a>Requisitos de configuración
<a name="ConfigReqs"> </a>

Necesitará realizar estas configuraciones adicionales para ejecutar correctamente la herramienta Stress and Performance:
  
- Debe iniciar sesión en el servidor como miembro del grupo De dominio o Administrador local.
    
- No puede instalar la herramienta de creación de usuarios de Skype Empresarial Server 2015 (UserProvisioningTool.exe) en ningún servidor front-end o servidor Standard Edition donde residirán las cuentas de usuario.
    
- Cuando la herramienta de creación de usuarios se ejecuta varias veces, cada usuario habilitado para las comunicaciones unificadas de Microsoft debe tener un número de teléfono único.
    
- El tamaño del archivo de página debe ser administrado por sistemas o, de lo contrario, debe ser al menos 1,5 veces la cantidad de RAM en el sistema del equipo.
    
## <a name="installing-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Instalación de la Herramienta de esfuerzo y rendimiento de Skype Empresarial Server 2015
<a name="Installing"> </a>

La instalación no pudo ser más sencilla. Debe ejecutar el archivo de Windows Installer, **CapacityPlanningTool.msi**, en cada equipo cliente que vaya a usar para simular el tráfico de usuarios y en un servidor front-end en cada grupo de servidores donde creará usuarios y contactos.
  
To download the .msi, along with the sample scripts mentioned in our other articles, go to the Download Center link: [Skype for Business Server 2015, Stress and Performance Tool](https://www.microsoft.com/download/details.aspx?id=50367).
  

