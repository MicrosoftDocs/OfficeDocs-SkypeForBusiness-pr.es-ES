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
description: 'Resumen: Obtenga información sobre cómo instalar las herramientas administrativas necesarias para una instalación de Skype empresarial Server. Descargue una versión de prueba gratuita de Skype empresarial Server del centro de evaluación de Microsoft https://www.microsoft.com/evalcenter/evaluate-skype-for-business-serveren:.'
ms.openlocfilehash: 27cda52612eef1259017250ebcc4669e45165229
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42018271"
---
# <a name="install-administrative-tools-in-skype-for-business-server"></a>Instalar herramientas administrativas en Skype empresarial Server
 
**Resumen:** Obtenga información sobre cómo instalar las herramientas administrativas necesarias para una instalación de Skype empresarial Server. Descargue una versión de prueba gratuita de Skype empresarial Server del centro de evaluación de Microsoft [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)en:.
  
Las herramientas administrativas incluyen el generador de topologías y el panel de control. Las herramientas administrativas deben instalarse en al menos un servidor de la topología o una estación de trabajo de administración de 64 bits que ejecute una versión de sistema operativo de Windows compatible con Skype empresarial Server. Puede realizar los pasos del 1 al 5 en cualquier orden. Sin embargo, debe realizar los pasos 6, 7 y 8 en orden, y después de los pasos del 1 al 5, tal y como se describe en el diagrama. La instalación de las herramientas administrativas es el paso 3 de 8.
  
![Diagrama de información general](../../media/d856afe8-4758-432f-bc45-e1956016419a.png)
  
## <a name="install-skype-for-business-server-administrative-tools"></a>Instalar las herramientas administrativas de Skype empresarial Server

Los medios de instalación de Skype empresarial Server proporcionan una experiencia flexible. La primera vez que se ejecuta Setup. exe, las únicas herramientas instaladas son el Asistente para la implementación de Skype empresarial Server y el shell de administración de Skype empresarial Server. Mediante el uso de estas dos herramientas, conocidas como componentes principales, puede continuar con el proceso de instalación, pero no proporcionan funciones principales para el entorno general de Skype empresarial Server. El Asistente para la implementación se inicia automáticamente después de instalar los componentes principales. La sección del Asistente para la implementación titulada **instalar herramientas administrativas** instala el generador de topologías de Skype empresarial Server y el panel de control de Skype empresarial Server.
  
> [!IMPORTANT]
> Todos los entornos de Skype empresarial Server deben tener al menos un servidor con las herramientas administrativas instaladas. 
  
Vea los pasos del vídeo para **instalar herramientas administrativas**:
  
> [!video https://www.microsoft.com/videoplayer/embed/99a5c436-963b-4eed-b423-651568c87cb1?autoplay=false]
  
### <a name="install-skype-for-business-server-administrative-tools-from-the-deployment-wizard"></a>Instalar las herramientas administrativas de Skype empresarial Server desde el Asistente para la implementación

1. Inserte los medios de instalación de Skype empresarial Server. Si el programa de instalación no se inicia automáticamente, haga doble clic en **setup**.
    
2. El medio de instalación requiere que se ejecute Microsoft Visual C++. Aparecerá un cuadro de diálogo preguntándole si quiere instalarlo. Haga clic en **Sí**.
    
3. Mediante el uso de la configuración inteligente, una nueva característica de Skype empresarial Server, puede conectarse a Internet para comprobar si hay actualizaciones durante el proceso de instalación. Esto proporciona una mejor experiencia asegurándose de que tiene las actualizaciones más recientes del producto durante la instalación. Haga clic en **Instalar** para comenzar el proceso de instalación.
    
4. Revise atentamente el contrato de licencia y, si está de acuerdo, seleccione Acepto **los términos del contrato de licencia**y haga clic en **Aceptar**.
    
5. Los componentes principales de Skype empresarial Server se instalarán en el servidor. 
    
    Los componentes principales constan de lo siguiente, tal como se muestra en la figura.
    
    ![Componentes principales de la pantalla de aplicaciones.](../../media/0da1d983-4c4b-4b23-a196-c3bdba4857c6.png)
  
   - **Asistente para la implementación de Skype empresarial Server** Un programa de implementación que proporciona un panel de inicio para la instalación de los diversos componentes de Skype empresarial Server.
    
   - **Shell de administración de Skype empresarial Server** Un programa de PowerShell preconfigurado que permite la administración de Skype empresarial Server.
    
     Una vez completada la instalación de los componentes principales, se iniciará automáticamente el Asistente para la implementación de Skype empresarial Server, como se muestra en la figura. 
    
     ![Asistente para la implementación de Skype empresarial Server](../../media/310c3437-83f9-48fa-a1e1-9fd09009fe31.png)
  
6. Además de los componentes principales, también tendrá que instalar el generador de topologías de Skype empresarial Server y el panel de control de Skype empresarial Server en al menos un servidor del entorno. Haga clic en **instalar herramientas administrativas** en el Asistente para la implementación.
    
7. Haga clic en **Siguiente** para comenzar la instalación.
    
8. Una vez finalizada la instalación, haga clic en **Finalizar**. Las herramientas administrativas se agregan ahora al servidor, como se muestra en la figura.
    
    ![Herramientas administrativas de Skype empresarial Server](../../media/760873dd-9c87-4efb-bf98-7162d876fd18.png)
  
   - **Generador de topologías de Skype empresarial Server** Un programa que se usa para crear, implementar y administrar topologías.
    
   - **Panel de control de Skype empresarial Server** Un programa usado para administrar la instalación.
    

