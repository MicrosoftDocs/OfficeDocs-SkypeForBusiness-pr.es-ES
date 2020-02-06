---
title: Instalar los requisitos previos de Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 'Resumen: Obtenga información sobre los servidores y roles de servidor que debe configurar antes de instalar Skype empresarial Server. Descargue una prueba gratuita de Skype empresarial Server en el centro de evaluación de Microsoft en https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server:.'
ms.openlocfilehash: f8ecb50525a9bb312975bf71b55a5f71c19db205
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41791768"
---
# <a name="install-prerequisites-for-skype-for-business-server"></a>Instalar los requisitos previos de Skype empresarial Server
 
**Resumen:** Obtenga más información sobre los servidores y roles de servidor que debe configurar antes de instalar Skype empresarial Server. Descargue una prueba gratuita de Skype empresarial Server en el [centro de evaluación de Microsoft](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).
  
La instalación de los requisitos previos consiste en configurar Windows Server mediante la instalación de los roles y las características necesarios en cada uno de los servidores de la topología. Los requisitos se basan en el rol que el servidor va a cumplir en la topología. Puede realizar los pasos 1 a 5 en cualquier orden. Sin embargo, debe realizar los pasos 6, 7 y 8 en orden, y después de los pasos 1 a 5, según se indica en el diagrama. La instalación de los requisitos previos es el paso 1 de 8.
  
![Diagrama de información general: requisitos previos de instalación.](../../media/0a85349b-b398-4e04-8901-8f4bd25d8afe.png)
  
## <a name="setup-windows-server"></a>Configurar Windows Server

Skype empresarial Server requiere el sistema operativo Windows Server y un número de requisitos previos para poder instalarlo. Para obtener detalles sobre la planificación de requisitos previos, consulte [requisitos del servidor de Skype empresarial Server](../../../SfBServer2019/plan/system-requirements.md). 
  
> [!TIP]
> Este procedimiento utiliza Windows Server 2012 R2. Es posible que el procedimiento sea un poco diferente si usa una versión de Windows Server distinta. 
  
> [!IMPORTANT]
> Antes de empezar, asegúrese de que Windows Server está actualizado mediante Windows Update. 
  
![Windows Server actualizado.](../../media/a8d57a97-a55e-443b-b304-c534ae9a71b2.png)
  
Vea los pasos del vídeo para **instalar los requisitos previos**:
  
> [!video https://www.microsoft.com/en-us/videoplayer/embed/02447c2a-5b26-432f-aad6-b9b05cc93478?autoplay=false]
  
### <a name="install-required-roles-and-features-for-front-end-servers"></a>Instalar las características y los roles necesarios para los servidores front-end

Puede instalar los roles y las características necesarias con el administrador del servidor. 
    
1. Instale las características de software que se incluyen en los [requisitos del servidor para Skype empresarial Server](../../../SfBServer2019/plan/system-requirements.md). El software necesario debe estar en el servidor que ejecutará Skype empresarial Server.
    
    > [!CAUTION]
    > De forma predeterminada, Windows Server 2012 R2 no instala todos los archivos de origen de las características necesarias. Si el servidor no está conectado a Internet, necesitará insertar el disco de Windows Server 2012 R2 y seleccionar **Especifique una ruta de acceso de origen alternativa** para instalar las características necesarias. Los archivos de origen se encuentran en el directorio sources\sxs. Por ejemplo, si el medio de Windows Server 2012 R2 está en la unidad D, establecería la ruta `d:\sources\sxs`de acceso como. Es importante que disponga de las últimas actualizaciones de Windows Update. Si no se encuentra conectado a Internet, necesitará instalar todas las actualizaciones relevantes de manera manual, así como también todos los requisitos previos de las actualizaciones necesarias. 
  
1. Cuando el cuadro de diálogo indica que se ha completado la instalación, necesitará reiniciar el servidor para completar el proceso.
    
1. Ejecute **Windows Update** nuevamente para comprobar si hay actualizaciones de los roles y los servicios que se instalaron.
    
1. Si va a usar el panel de control de Skype empresarial Server en este servidor, también debe instalar Silverlight. Para instalar Silverlight, consulte [Microsoft Silverlight](https://www.microsoft.com/silverlight/).


> [!IMPORTANT]
> Los servidores que desempeñan roles distintos del de servidor front-end (como el rol de director, chat persistente o servidor perimetral) tienen sus propios requisitos previos. Para obtener más información sobre los requisitos previos exactos requeridos por cada tipo de servidor, consulte [requisitos del servidor de Skype empresarial Server](../../../SfBServer2019/plan/system-requirements.md). 
  

