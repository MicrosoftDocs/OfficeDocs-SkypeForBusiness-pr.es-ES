---
title: Instalar herramientas administrativas en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: 'Resumen: obtenga información sobre cómo instalar las herramientas administrativas necesarias para una instalación de Skype Empresarial Server. Descargue una prueba gratuita de Skype Empresarial Server desde el Centro de evaluación de Microsoft en: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server .'
ms.openlocfilehash: ab3e64ae5d330c5b24eff7c23172b1141ff75527
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812110"
---
# <a name="install-administrative-tools-in-skype-for-business-server"></a>Instalar herramientas administrativas en Skype Empresarial Server
 
**Resumen:** Obtenga información sobre cómo instalar las herramientas administrativas necesarias para una instalación de Skype Empresarial Server. Descargue una prueba gratuita de Skype Empresarial Server desde el Centro de evaluación de Microsoft en: [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server) .
  
Las herramientas administrativas incluyen el Generador de topologías y el Panel de control. Las herramientas administrativas deben instalarse en al menos un servidor de la topología o en una estación de trabajo de administración de 64 bits que ejecute una versión del sistema operativo Windows compatible con Skype Empresarial Server. Puede realizar los pasos del 1 al 5 en cualquier orden. Sin embargo, debe realizar los pasos 6, 7 y 8 en orden y después de los pasos 1 a 5, tal como se indica en el diagrama. La instalación de las herramientas administrativas es el paso 3 de 8.
  
![Diagrama de información general](../../media/d856afe8-4758-432f-bc45-e1956016419a.png)
  
## <a name="install-skype-for-business-server-administrative-tools"></a>Instalar herramientas administrativas de Skype Empresarial Server

Los medios de instalación de Skype Empresarial Server proporcionan una experiencia flexible. La primera vez que Setup.exe, las únicas herramientas instaladas son el Asistente para la implementación de Skype Empresarial Server y el Shell de administración de Skype Empresarial Server. Con estas dos herramientas, conocidas como componentes principales, puede continuar con el proceso de instalación, pero no proporcionan funcionalidad principal para el entorno general de Skype Empresarial Server. El Asistente para la implementación se inicia automáticamente después de instalar los componentes principales. La sección del Asistente para la implementación titulada **Instalar herramientas** administrativas instala el Generador de topologías de Skype Empresarial Server y el Panel de control de Skype Empresarial Server.
  
> [!IMPORTANT]
> Todos los entornos de Skype Empresarial Server deben tener al menos un servidor con las herramientas administrativas instaladas. 
  
Vea los pasos de vídeo para **instalar herramientas administrativas:**
  
> [!video https://www.microsoft.com/videoplayer/embed/99a5c436-963b-4eed-b423-651568c87cb1?autoplay=false]
  
### <a name="install-skype-for-business-server-administrative-tools-from-the-deployment-wizard"></a>Instalar las herramientas administrativas de Skype Empresarial Server desde el Asistente para la implementación

1. Inserte los medios de instalación de Skype Empresarial Server. Si la configuración no se inicia automáticamente, haga doble clic en **El programa de instalación.**
    
2. El medio de instalación requiere que se ejecute Microsoft Visual C++. Aparecerá un cuadro de diálogo que le preguntará si desea instalarlo. Haga clic en **Sí**.
    
3. Con la configuración inteligente, una nueva característica de Skype Empresarial Server, puede conectarse a Internet para buscar actualizaciones durante el proceso de instalación. Esto proporciona una mejor experiencia al asegurarte de que tienes las actualizaciones más recientes del producto durante la instalación. Haga clic en **Instalar** para comenzar el proceso de instalación.
    
4. Revise cuidadosamente el Contrato de licencia y, si está de acuerdo, seleccione **Acepto** los términos del contrato de licencia y haga clic en **Aceptar.**
    
5. Los componentes principales de Skype Empresarial Server se instalarán en el servidor. 
    
    Los componentes principales constan de lo siguiente, como se muestra en la ilustración.
    
    ![Componentes principales en la pantalla Aplicaciones.](../../media/0da1d983-4c4b-4b23-a196-c3bdba4857c6.png)
  
   - **Asistente para la implementación de Skype Empresarial Server** Un programa de implementación que proporciona un panel de inicio para instalar los distintos componentes de Skype Empresarial Server.
    
   - **Shell de administración de Skype Empresarial Server** Un programa de PowerShell preconfigurado que permite la administración de Skype Empresarial Server.
    
     Una vez completada la instalación de los componentes principales, el Asistente para la implementación de Skype Empresarial Server se iniciará automáticamente, como se muestra en la figura. 
    
     ![Asistente para la implementación de Skype Empresarial Server](../../media/310c3437-83f9-48fa-a1e1-9fd09009fe31.png)
  
6. Además de los componentes principales, también tendrá que instalar el Generador de topologías de Skype Empresarial Server y el Panel de control de Skype Empresarial Server en al menos un servidor del entorno. Haga **clic en Instalar herramientas administrativas** en el Asistente para la implementación.
    
7. Haga clic en **Siguiente** para comenzar la instalación.
    
8. Una vez completada la instalación, haga clic **en Finalizar.** Las herramientas administrativas ahora se agregan al servidor, como se muestra en la ilustración.
    
    ![Herramientas administrativas de Skype Empresarial Server](../../media/760873dd-9c87-4efb-bf98-7162d876fd18.png)
  
   - **Generador de topologías de Skype Empresarial Server** Un programa que se usa para crear, implementar y administrar topologías.
    
   - **Panel de control de Skype Empresarial Server** Un programa usado para administrar la instalación.
    

