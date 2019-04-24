---
title: Instalar los requisitos previos de Skype para Business Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 2ef91a1e-2899-44c8-8e2c-527cb9114a0a
description: 'Resumen: Obtenga información sobre los servidores y roles de servidor que debe configurar antes de instalar Skype para Business Server. Descargue una versión de prueba gratuita de Skype para Business Server desde el Evaluation de Microsoft center en: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server.'
ms.openlocfilehash: 0efa8a7fb06c1577d1b55fe42bfe88ca238e485e
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32210483"
---
# <a name="install-prerequisites-for-skype-for-business-server"></a>Instalar los requisitos previos de Skype para Business Server
 
**Resumen:** Obtenga información acerca de los servidores y roles de servidor que debe configurar antes de instalar Skype para Business Server. Descargue una versión de prueba gratuita de Skype para Business Server desde el [Centro de evaluación de Microsoft](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).
  
Instalación de requisitos previos se compone de la configuración de Windows Server mediante la instalación de las características y los roles necesarios en cada uno de los servidores de la topología. Los requisitos se basan en la función que se va a cumplir con el servidor en la topología. Se pueden realizar los pasos del 1 al 5 en cualquier orden. Sin embargo, debe realizar los pasos 6, 7 y 8 en orden y después de los pasos del 1 al 5, tal como se indica en el diagrama. Instalación de requisitos previos es el paso 1 de 8.
  
![Diagrama de información general: requisitos previos de instalación.](../../media/0a85349b-b398-4e04-8901-8f4bd25d8afe.png)
  
## <a name="setup-windows-server"></a>Configurar Windows Server

Skype para Business Server requiere el sistema operativo Windows Server y un número de requisitos previos antes de que se puede instalar. Para obtener información detallada acerca de cómo planear los requisitos previos, vea [requisitos de servidor para Skype para Business Server](../../../SfBServer2019/plan/system-requirements.md). 
  
> [!TIP]
> Este procedimiento utiliza Windows Server 2012 R2. Es posible que el procedimiento sea un poco diferente si usa una versión de Windows Server distinta. 
  
> [!IMPORTANT]
> Antes de empezar, asegúrese de que el servidor de Windows está actualizado mediante el uso de Windows Update. 
  
![Windows Server actualizado.](../../media/a8d57a97-a55e-443b-b304-c534ae9a71b2.png)
  
Vea los pasos del vídeo para **instalar los requisitos previos**:
  
> [!video https://www.microsoft.com/en-us/videoplayer/embed/02447c2a-5b26-432f-aad6-b9b05cc93478?autoplay=false]
  
### <a name="install-required-roles-and-features-for-front-end-servers"></a>Instalar las características y los roles necesarios para los servidores front-end

Puede instalar los roles necesarios y las características de con el administrador del servidor. 
    
1. Instalar las características de software necesario como requisito previo que aparecen en los [requisitos de servidor para Skype para Business Server](../../../SfBServer2019/plan/system-requirements.md). Debe ser el software necesario en el servidor que ejecutará Skype para Business Server.
    
    > [!CAUTION]
    > De forma predeterminada, Windows Server 2012 R2 no instala todos los archivos de origen de las características necesarias. Si el servidor no está conectado a Internet, necesitará insertar el disco de Windows Server 2012 R2 y seleccionar **Especifique una ruta de acceso de origen alternativa** para instalar las características necesarias. Los archivos de origen se encuentran en el directorio sources\sxs. Por ejemplo, si los medios de Windows Server 2012 R2 se encuentra en la unidad D, establecería la ruta de acceso `d:\sources\sxs`. Es importante que disponga de las últimas actualizaciones de Windows Update. Si no se encuentra conectado a Internet, necesitará instalar todas las actualizaciones relevantes de manera manual, así como también todos los requisitos previos de las actualizaciones necesarias. 
  
1. Cuando el cuadro de diálogo indica que se ha completado la instalación, necesitará reiniciar el servidor para completar el proceso.
    
1. Ejecute **Windows Update** nuevamente para comprobar si hay actualizaciones de los roles y los servicios que se instalaron.
    
1. Si va a usar Skype para el Panel de Control de servidor empresarial en este servidor, a continuación, también debe instalar Silverlight. Para instalar Silverlight, vea [Microsoft Silverlight](https://www.microsoft.com/silverlight/).


> [!IMPORTANT]
> Los servidores que desempeñan roles distintos del de servidor front-end (como el rol de director, chat persistente o servidor perimetral) tienen sus propios requisitos previos. Para obtener información detallada sobre los requisitos previos exactos necesarios para cada tipo de servidor, vea [requisitos de servidor para Skype para Business Server](../../../SfBServer2019/plan/system-requirements.md). 
  

