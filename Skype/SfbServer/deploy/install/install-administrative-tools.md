---
title: Instalar herramientas administrativas en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/14/2018
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
ms.assetid: 52ee7da4-59ba-499a-a105-d93fa9941334
description: 'Resumen: Aprenda a instalar las herramientas administrativas necesarias para una instalación de Skype empresarial Server. Descargue una prueba gratuita de Skype empresarial Server en el centro de evaluación de Microsoft en https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server:.'
ms.openlocfilehash: 3abf2eb35a4593f25db75e175f3cd30fdf49e21b
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41790178"
---
# <a name="install-administrative-tools-in-skype-for-business-server"></a>Instalar herramientas administrativas en Skype empresarial Server
 
**Resumen:** Obtenga información sobre cómo instalar las herramientas administrativas necesarias para una instalación de Skype empresarial Server. Descargue una prueba gratuita de Skype empresarial Server en el centro de evaluación de Microsoft en [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server):.
  
Las herramientas administrativas incluyen Topology Builder y el panel de control. Las herramientas administrativas deben instalarse en al menos un servidor de la topología o una estación de trabajo de administración de 64 bits que ejecute una versión de Windows del sistema operativo compatible con Skype empresarial Server. Puede realizar los pasos 1 a 5 en cualquier orden. Sin embargo, debe realizar los pasos 6, 7 y 8 en orden, y después de los pasos 1 a 5, según se indica en el diagrama. Instalar las herramientas administrativas es el paso 3 de 8.
  
![Diagrama de información general](../../media/d856afe8-4758-432f-bc45-e1956016419a.png)
  
## <a name="install-skype-for-business-server-administrative-tools"></a>Instalar las herramientas administrativas de Skype empresarial Server

Los medios de instalación de Skype empresarial Server proporcionan una experiencia flexible. La primera vez que ejecute setup. exe, las únicas herramientas instaladas serán el Asistente para la implementación de Skype empresarial Server y el shell de administración de Skype empresarial Server. Al usar estas dos herramientas, conocidas como componentes básicos, puede continuar con el proceso de instalación, pero no proporcionan la funcionalidad principal para el entorno general de Skype empresarial Server. El Asistente para la implementación se inicia automáticamente después de instalar los componentes principales. La sección del asistente de implementación titulada **instalar herramientas administrativas** instala el generador de topologías de Skype empresarial Server y el panel de control de Skype empresarial Server.
  
> [!IMPORTANT]
> Cada entorno de Skype empresarial Server debe tener al menos un servidor con las herramientas administrativas instaladas. 
  
Vea los pasos del vídeo para **Instalar herramientas administrativas**:
  
> [!video https://www.microsoft.com/en-us/videoplayer/embed/99a5c436-963b-4eed-b423-651568c87cb1?autoplay=false]
  
### <a name="install-skype-for-business-server-administrative-tools-from-the-deployment-wizard"></a>Instalar las herramientas administrativas de Skype empresarial Server desde el Asistente para la implementación

1. Inserte los medios de instalación de Skype empresarial Server. Si la configuración no empieza automáticamente, haga doble clic en **Configuración**.
    
2. La ejecución del disco de instalación necesita Microsoft Visual C++. Aparecerá un cuadro de diálogo preguntándole si quiere instalarlo. Haga clic en **Sí**.
    
3. Al usar la configuración inteligente, una nueva característica de Skype empresarial Server, puede conectarse a Internet para comprobar si hay actualizaciones durante el proceso de instalación. Esto proporciona una mejor experiencia, ya que se asegura de que dispone de las actualizaciones más recientes del producto en el momento de la instalación. Haga clic en **Instalar** para empezar la instalación.
    
4. Revise cuidadosamente el contrato de licencia y, si está de acuerdo, elija **Acepto los términos del Contrato de licencia** y haga clic en **Aceptar**.
    
5. Los componentes principales de Skype empresarial Server se instalarán en el servidor. 
    
    Estos componentes incluyen lo siguiente, como se muestra en la figura.
    
    ![Componentes principales de la pantalla Aplicaciones.](../../media/0da1d983-4c4b-4b23-a196-c3bdba4857c6.png)
  
   - **Asistente para la implementación de Skype empresarial Server** Un programa de implementación que proporciona un Launch Pad para instalar los distintos componentes de Skype empresarial Server.
    
   - **Shell de administración de Skype empresarial Server** Un programa de PowerShell preconfigurado que permite la administración de Skype empresarial Server.
    
     Una vez completada la instalación de los componentes principales, el Asistente para la implementación de Skype empresarial Server se iniciará automáticamente, tal como se muestra en la ilustración. 
    
     ![Asistente para la implementación de Skype Empresarial Server](../../media/310c3437-83f9-48fa-a1e1-9fd09009fe31.png)
  
6. Además de los componentes principales, también tendrá que instalar el generador de topologías de Skype empresarial Server y el panel de control de Skype empresarial Server en al menos un servidor del entorno. Haga clic en **Instalar herramientas administrativas** en el Asistente para la implementación.
    
7. Haga clic en **Siguiente** para empezar la instalación.
    
8. Una vez que se completa la instalación, haga clic en **Finalizar**. Ahora, como se ve en la figura, se agregan las herramientas administrativas en el servidor.
    
    ![Herramientas administrativas de Skype empresarial Server](../../media/760873dd-9c87-4efb-bf98-7162d876fd18.png)
  
   - **Generador de topologías de Skype empresarial Server** Un programa que se usa para generar, implementar y administrar topologías.
    
   - **Panel de control de Skype empresarial Server** Un programa que se usa para administrar la instalación.
    

