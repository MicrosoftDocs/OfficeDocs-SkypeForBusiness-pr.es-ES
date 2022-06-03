---
title: Instalación de requisitos previos para Skype Empresarial Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/7/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 2ef91a1e-2899-44c8-8e2c-527cb9114a0a
description: 'Resumen: obtenga información sobre los servidores y roles de servidor que debe configurar antes de instalar Skype Empresarial Server.'
ms.openlocfilehash: d946b694ea527236b8ce6f4b7b562df9fa025011
ms.sourcegitcommit: e99471689ff60f9ab1095bc075f8b4c5569c9634
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2022
ms.locfileid: "65860741"
---
# <a name="install-prerequisites-for-skype-for-business-server"></a>Instalación de requisitos previos para Skype Empresarial Server
 
**Resumen:** Obtenga información sobre los servidores y roles de servidor que debe configurar antes de instalar Skype Empresarial Server.
  
La instalación de requisitos previos consiste en configurar Windows Server mediante la instalación de los roles y características necesarios en cada uno de los servidores de la topología. Los requisitos se basan en el rol que el servidor cumplirá en la topología. Puede realizar los pasos del 1 al 5 en cualquier orden. Sin embargo, debe realizar los pasos 6, 7 y 8 en orden, y después de los pasos del 1 al 5, como se describe en el diagrama. La instalación de los requisitos previos es el paso 1 del 8.
  
![Diagrama de información general: requisitos previos de instalación.](../../media/0a85349b-b398-4e04-8901-8f4bd25d8afe.png)
  
## <a name="setup-windows-server"></a>Instalación de Windows Server

Skype Empresarial Server requiere el sistema operativo Windows Server y una serie de requisitos previos para poder instalarlo. Para obtener más información sobre cómo planear los requisitos previos, consulte [Requisitos del servidor para Skype Empresarial Server](../../../SfBServer2019/plan/system-requirements.md). 
  
> [!TIP]
> Este procedimiento usa Windows Server 2012 R2. Si usa una versión diferente de Windows Server, el procedimiento podría ser ligeramente diferente. 
  
> [!IMPORTANT]
> Antes de empezar, asegúrese de que Windows Server esté actualizado mediante Windows Update. 
  
![Windows Server actualizado.](../../media/a8d57a97-a55e-443b-b304-c534ae9a71b2.png)
  
Vea los pasos de vídeo para **instalar los requisitos previos**:
  
> [!video https://www.microsoft.com/videoplayer/embed/02447c2a-5b26-432f-aad6-b9b05cc93478?autoplay=false]
  
### <a name="install-required-roles-and-features-for-front-end-servers"></a>Instalación de roles y características necesarios para servidores front-end

Puede instalar los roles y características necesarios mediante Administrador del servidor. 
    
1. Instale las características de software de requisitos previos que aparecen en [Requisitos del servidor para Skype Empresarial Server](../../../SfBServer2019/plan/system-requirements.md). El software necesario debe estar en el servidor que ejecutará Skype Empresarial Server.
    
    > [!CAUTION]
    > Windows Server 2012 R2 no instala todos los archivos de origen para las características necesarias de forma predeterminada. Si el servidor no está conectado a Internet, deberá insertar el medio de Windows Server 2012 R2 y seleccionar **Especificar una ruta de acceso de origen alternativa** para instalar las características necesarias. Los archivos de origen se encuentran en el directorio sources\sxs. Por ejemplo, si el medio de Windows Server 2012 R2 está en la unidad D, establecería la ruta de acceso en `d:\sources\sxs`. Es importante que tenga las actualizaciones más recientes de Windows Update. Si no está conectado a Internet, deberá instalar manualmente todas las actualizaciones pertinentes, así como los requisitos previos para las actualizaciones necesarias. 
  
1. Cuando el cuadro de diálogo indica que la instalación se ha completado, tendrá que reiniciar el servidor para completar el proceso.
    
1. Vuelva a ejecutar **Windows Update** para comprobar si hay actualizaciones en los roles y servicios que se instalaron.
    
1. Si va a usar Skype Empresarial Server Panel de control en este servidor, también debe instalar Silverlight. Para instalar Silverlight, consulte [Microsoft Silverlight](https://www.microsoft.com/silverlight/).


> [!IMPORTANT]
> Los requisitos previos para los servidores que realizan roles distintos del servidor front-end, como el rol de director, chat persistente o perimetral, tienen sus propios requisitos previos. Para obtener más información sobre los requisitos previos exactos que requiere cada tipo de servidor, consulte Requisitos del servidor [para Skype Empresarial Server](../../../SfBServer2019/plan/system-requirements.md). 
  

