---
title: Instalar requisitos previos para Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/7/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 2ef91a1e-2899-44c8-8e2c-527cb9114a0a
description: 'Resumen: obtenga información sobre los servidores y los roles de servidor que debe configurar antes de instalar Skype Empresarial Server. Descargue una versión de prueba Skype Empresarial Server desde el Centro de evaluación de Microsoft en: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server .'
ms.openlocfilehash: 5d44a95be8c05b8a171b7bd72b9aaeaf19ff8fbc67247388e89cfea16dc6e21a
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54280305"
---
# <a name="install-prerequisites-for-skype-for-business-server"></a>Instalar requisitos previos para Skype Empresarial Server
 
**Resumen:** Obtenga información sobre los servidores y los roles de servidor que debe configurar antes de instalar Skype Empresarial Server. Descargue una prueba gratuita de Skype Empresarial Server desde el [Centro de evaluación de Microsoft](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).
  
La instalación de requisitos previos consiste en configurar Windows Server instalando los roles y características necesarios en cada uno de los servidores de la topología. Los requisitos se basan en el rol que el servidor cumplirá en la topología. Puede realizar los pasos del 1 al 5 en cualquier orden. Sin embargo, debe realizar los pasos 6, 7 y 8 en orden y después de los pasos del 1 al 5, tal como se describe en el diagrama. La instalación de requisitos previos es el paso 1 de 8.
  
![Diagrama de información general: requisitos previos de instalación.](../../media/0a85349b-b398-4e04-8901-8f4bd25d8afe.png)
  
## <a name="setup-windows-server"></a>Configurar Windows server

Skype Empresarial Server requiere el Windows operativo del servidor y una serie de requisitos previos antes de poder instalarse. Para obtener información detallada sobre la planeación de requisitos previos, vea [Requisitos del](../../../SfBServer2019/plan/system-requirements.md)servidor para Skype Empresarial Server . 
  
> [!TIP]
> Este procedimiento usa Windows Server 2012 R2. Si usa una versión diferente de Windows Server, el procedimiento puede ser ligeramente diferente. 
  
> [!IMPORTANT]
> Antes de empezar, asegúrese de que Windows Server esté actualizado mediante Windows Update. 
  
![Windows Servidor actualizado.](../../media/a8d57a97-a55e-443b-b304-c534ae9a71b2.png)
  
Vea los pasos de vídeo para **los requisitos previos de instalación:**
  
> [!video https://www.microsoft.com/videoplayer/embed/02447c2a-5b26-432f-aad6-b9b05cc93478?autoplay=false]
  
### <a name="install-required-roles-and-features-for-front-end-servers"></a>Instalar funciones y características necesarias para servidores front-end

Puede instalar las funciones y características necesarias con el Administrador de servidores. 
    
1. Instale las características de software de requisitos previos enumeradas [en Requisitos del servidor para Skype Empresarial Server](../../../SfBServer2019/plan/system-requirements.md). El software necesario debe estar en el servidor que se ejecutará Skype Empresarial Server.
    
    > [!CAUTION]
    > Windows Server 2012 R2 no instala todos los archivos de origen para las características necesarias de forma predeterminada. Si el servidor no está conectado a Internet, deberá insertar el medio  Windows Server 2012 R2 y seleccionar Especificar una ruta de origen alternativa para instalar las características necesarias. Los archivos de origen se encuentran en el directorio sources\sxs. Por ejemplo, si el Windows Server 2012 de R2 está en la unidad D, se establecería la ruta de acceso en `d:\sources\sxs` . Es importante que tenga las actualizaciones más recientes de Windows Update. Si no está conectado a Internet, deberá instalar manualmente todas las actualizaciones relevantes, así como los requisitos previos de las actualizaciones necesarias. 
  
1. Cuando el cuadro de diálogo indica que la instalación se ha completado, deberá reiniciar el servidor para completar el proceso.
    
1. Ejecute **Windows update de** nuevo para comprobar si hay actualizaciones de los roles y servicios que se instalaron.
    
1. Si va a usar el Panel Skype Empresarial Server control en este servidor, también debe instalar Silverlight. Para instalar Silverlight, vea [Microsoft Silverlight](https://www.microsoft.com/silverlight/).


> [!IMPORTANT]
> Los requisitos previos para que los servidores que realicen roles distintos del servidor front-end, como el rol director, el chat persistente o el servidor perimetral, tienen sus propios requisitos previos. Para obtener información detallada sobre los requisitos previos exactos requeridos por cada tipo de servidor, vea [Requisitos del servidor para Skype Empresarial Server](../../../SfBServer2019/plan/system-requirements.md). 
  

