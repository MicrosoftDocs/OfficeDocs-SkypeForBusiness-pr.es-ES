---
title: Instalación de requisitos previos de Skype empresarial Server
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
description: 'Resumen: Obtenga información sobre los servidores y roles de servidor que debe configurar antes de instalar Skype empresarial Server. Descargue una versión de prueba gratuita de Skype empresarial Server del centro de evaluación de Microsoft https://www.microsoft.com/evalcenter/evaluate-skype-for-business-serveren:.'
ms.openlocfilehash: fedcebe601d21f0e581795c264ed26c6e90716bd
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42018261"
---
# <a name="install-prerequisites-for-skype-for-business-server"></a>Instalación de requisitos previos de Skype empresarial Server
 
**Resumen:** Obtenga información sobre los servidores y las funciones de servidor que debe configurar antes de instalar Skype empresarial Server. Descargue una versión de prueba gratuita de Skype empresarial Server del [centro de evaluación de Microsoft](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).
  
La instalación de los requisitos previos consiste en la configuración de Windows Server mediante la instalación de los roles y las características necesarios en cada uno de los servidores de la topología. Los requisitos se basan en el rol que el servidor va a cumplir en la topología. Puede realizar los pasos del 1 al 5 en cualquier orden. Sin embargo, debe realizar los pasos 6, 7 y 8 en orden, y después de los pasos del 1 al 5, tal y como se describe en el diagrama. La instalación de los requisitos previos es el paso 1 de 8.
  
![Diagrama de información general: instalación de requisitos previos.](../../media/0a85349b-b398-4e04-8901-8f4bd25d8afe.png)
  
## <a name="setup-windows-server"></a>Configurar Windows Server

Skype empresarial Server requiere el sistema operativo Windows Server y una serie de requisitos previos antes de que se pueda instalar. Para obtener más información sobre la planeación de requisitos previos, vea [Server Requirements for Skype for Business Server](../../../SfBServer2019/plan/system-requirements.md). 
  
> [!TIP]
> Este procedimiento usa Windows Server 2012 R2. Si usa una versión diferente de Windows Server, es posible que el procedimiento sea ligeramente diferente. 
  
> [!IMPORTANT]
> Antes de empezar, asegúrese de que Windows Server está actualizado mediante Windows Update. 
  
![Windows Server actualizado.](../../media/a8d57a97-a55e-443b-b304-c534ae9a71b2.png)
  
Vea los pasos del vídeo para **instalar los requisitos previos**:
  
> [!video https://www.microsoft.com/videoplayer/embed/02447c2a-5b26-432f-aad6-b9b05cc93478?autoplay=false]
  
### <a name="install-required-roles-and-features-for-front-end-servers"></a>Instalar los roles y las características necesarios para los servidores front-end

Puede instalar los roles y las características necesarios mediante el administrador del servidor. 
    
1. Instale las características de software necesarias que se indican en [Server Requirements for Skype for Business Server](../../../SfBServer2019/plan/system-requirements.md). El software necesario debe estar en el servidor que va a ejecutar Skype empresarial Server.
    
    > [!CAUTION]
    > Windows Server 2012 R2 no instala de forma predeterminada todos los archivos de origen para las características necesarias. Si el servidor no está conectado a Internet, deberá insertar el medio de Windows Server 2012 R2 y seleccionar **especificar una ruta de acceso de origen alternativa** para instalar las características necesarias. Los archivos de origen se encuentran en el directorio sources\sxs Por ejemplo, si el medio de Windows Server 2012 R2 está en la unidad D, establezca la ruta de `d:\sources\sxs`acceso en. Es importante que tenga las actualizaciones más recientes de Windows Update. Si no está conectado a Internet, tendrá que instalar manualmente todas las actualizaciones relevantes, así como los requisitos previos de las actualizaciones necesarias. 
  
1. Cuando el cuadro de diálogo indique que la instalación ha finalizado, tendrá que reiniciar el servidor para completar el proceso.
    
1. Vuelva a ejecutar **Windows Update** para comprobar si hay actualizaciones de los roles y servicios que se instalaron.
    
1. Si va a usar el panel de control de Skype empresarial Server en este servidor, también debe instalar Silverlight. Para instalar Silverlight, consulte [Microsoft Silverlight](https://www.microsoft.com/silverlight/).


> [!IMPORTANT]
> Los requisitos previos para los servidores que realizan roles que no son servidores front-end, como el rol de Director, chat persistente o Edge, tienen sus propios requisitos previos. Para obtener más información sobre los requisitos previos exactos necesarios para cada tipo de servidor, vea [Server Requirements for Skype for Business Server](../../../SfBServer2019/plan/system-requirements.md). 
  

