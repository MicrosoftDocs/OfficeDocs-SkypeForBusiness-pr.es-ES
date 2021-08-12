---
title: Requisitos previos y configuración de la Skype para la herramienta de rendimiento y esfuerzo de Busines
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
description: Requisitos o requisitos previos para la Skype Empresarial Server 2015 Stress and Performance Tool. Cómo instalar o configurar la Herramienta de esfuerzo y rendimiento.
ms.openlocfilehash: 947cc43f68fc4d3140f664fbeb554096fcbb5cfb8c13d7354bc937af93812e93
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54333152"
---
# <a name="prerequisites-and-setup-for-the-skype-for-busines-stress-and-performance-tool"></a>Requisitos previos y configuración de la Skype para la herramienta de rendimiento y esfuerzo de Busines
 
Requisitos o requisitos previos para la Skype Empresarial Server 2015 Stress and Performance Tool. Cómo instalar o configurar la Herramienta de esfuerzo y rendimiento.
  
Tenemos las siguientes secciones de requisitos de configuración de hardware, software y sistema que deberá conocer antes de ejecutar la Herramienta de esfuerzo y rendimiento:
  
- [Requisitos de hardware de cliente](prerequisites-and-setup.md#ClientHardwareReqs)
    
- [Requisitos de software de cliente](prerequisites-and-setup.md#ClientSoftwareReqs)
    
- [Requisitos de configuración](prerequisites-and-setup.md#ConfigReqs)
    
Además, también tenemos una sección a continuación para instalar la [herramienta de Skype Empresarial Server 2015 Stress and Performance Tool](prerequisites-and-setup.md#Installing)
  
## <a name="client-hardware-requirements"></a>Requisitos de hardware de cliente
<a name="ClientHardwareReqs"> </a>

Al ejecutar la Herramienta de esfuerzo y rendimiento en la implementación de Skype Empresarial Server 2015, necesitará, como mínimo, que se cumplen estos requisitos de hardware para cada 4500 usuarios de la prueba:
  
- Adaptador de red de 1 gigabit
    
- 8 GB de RAM
    
- 2 CPU de doble núcleo
    
## <a name="client-software-requirements"></a>Requisitos de software de cliente
<a name="ClientSoftwareReqs"> </a>

Los sistemas operativos admitidos para la Herramienta de esfuerzo y rendimiento son:
  
- Windows Server 2012
    
- Windows Server 2008 (64 bits)
    
Además, los equipos deben cumplir los siguientes requisitos de software:
  
- Necesitará microsoft .NET 4.5 Framework instalado. [Descargue .Net 4.5 Framework aquí.](https://www.microsoft.com/download/details.aspx?id=30653)
    
- Necesitarás la característica Experiencia de escritorio habilitada en Windows.
    
- Necesitarás que Microsoft Visual C++ 2013 (x64) instalado. [Descargue Visual C++ 2013 aquí](https://www.microsoft.com/download/details.aspx?id=40784)
    
- Necesitará implementar correctamente Skype Empresarial Server 2015.
    
## <a name="configuration-requirements"></a>Requisitos de configuración
<a name="ConfigReqs"> </a>

Necesitarás realizar estas configuraciones adicionales para ejecutar correctamente la Herramienta de esfuerzo y rendimiento:
  
- Debe iniciar sesión en el servidor como miembro del grupo dominio o administrador local.
    
- No puede instalar la herramienta de creación de usuarios de Skype Empresarial Server 2015 (UserProvisioningTool.exe) en ningún servidor front-end o servidor Standard Edition donde residirán las cuentas de usuario.
    
- Cuando la herramienta de creación de usuarios se ejecuta varias veces, cada usuario habilitado para las comunicaciones unificadas de Microsoft debe tener un número de teléfono único.
    
- El tamaño del archivo de página debe estar administrado por sistemas o, de lo contrario, debe ser al menos 1,5 veces la cantidad de RAM en el sistema del equipo.
    
## <a name="installing-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Instalación de la Skype Empresarial Server de esfuerzo y rendimiento de 2015
<a name="Installing"> </a>

La instalación no puede ser más sencilla. Debe ejecutar el archivo del instalador de **Windows,CapacityPlanningTool.msi**, en cada equipo cliente que va a usar para simular el tráfico de usuarios y en un servidor front-end en cada grupo donde creará usuarios y contactos.
  
Para descargar el .msi, junto con los scripts de ejemplo mencionados en nuestros otros artículos, vaya al vínculo Centro de descarga: [Skype Empresarial Server 2015, Herramienta](https://www.microsoft.com/download/details.aspx?id=50367)de esfuerzo y rendimiento .
  

