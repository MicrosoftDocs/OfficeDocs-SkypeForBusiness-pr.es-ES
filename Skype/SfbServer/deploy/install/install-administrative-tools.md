---
title: Instalar herramientas administrativas en Skype Empresarial Server
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 7/14/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.collection:
  - IT_Skype16
  - Strat_SB_Admin
ms.custom: null
ms.assetid: 52ee7da4-59ba-499a-a105-d93fa9941334
description: 'Resumen: obtenga información sobre cómo instalar las herramientas administrativas necesarias para una instalación de Skype Empresarial Server. Descargue una prueba gratuita de Skype Empresarial Server desde el Centro de evaluación de Microsoft en: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server.'
---

# <a name="install-administrative-tools-in-skype-for-business-server"></a>Instalar herramientas administrativas en Skype Empresarial Server
 
**Resumen:** Obtenga información sobre cómo instalar las herramientas administrativas necesarias para una instalación de Skype Empresarial Server. Descargue una prueba gratuita de Skype Empresarial Server desde el Centro de evaluación de Microsoft en: [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).
  
Las herramientas administrativas incluyen el Generador de topologías y el Panel de control. Las herramientas administrativas deben instalarse en al menos un servidor de la topología o en una estación de trabajo de administración de 64 bits que ejecute una versión del sistema operativo Windows compatible con Skype Empresarial Server. Puede realizar los pasos del 1 al 5 en cualquier orden. Sin embargo, debe realizar los pasos 6, 7 y 8 en orden y después de los pasos del 1 al 5, tal como se describe en el diagrama. Instalar las herramientas administrativas es el paso 3 de 8.
  
![Diagrama de información general.](../../media/d856afe8-4758-432f-bc45-e1956016419a.png)
  
## <a name="install-skype-for-business-server-administrative-tools"></a>Instalar Skype Empresarial Server administrativas

El medio de instalación para Skype Empresarial Server proporciona una experiencia flexible. Cuando se ejecuta por primera Setup.exe, las únicas herramientas instaladas son el Asistente Skype Empresarial Server implementación y el Shell Skype Empresarial Server administración. Con estas dos herramientas, conocidas como componentes principales, puede continuar con el proceso de instalación, pero no proporcionan funcionalidad principal para el entorno Skype Empresarial Server general. El Asistente para la implementación se inicia automáticamente después de instalar los componentes principales. La sección del Asistente para implementación titulada **Instalar herramientas** administrativas se instala Skype Empresarial Server Generador de topologías y Skype Empresarial Server Panel de control.
  
> [!IMPORTANT]
> Cada Skype Empresarial Server debe tener al menos un servidor con las herramientas administrativas instaladas. 
  
Vea los pasos de vídeo de **Instalar herramientas administrativas**:
  
> [!video https://www.microsoft.com/videoplayer/embed/99a5c436-963b-4eed-b423-651568c87cb1?autoplay=false]
  
### <a name="install-skype-for-business-server-administrative-tools-from-the-deployment-wizard"></a>Instalar Skype Empresarial Server administrativas desde el Asistente para implementación

1. Inserte el Skype Empresarial Server de instalación. Si la configuración no se inicia automáticamente, haga doble clic en **Configurar**.
    
2. El medio de instalación Microsoft Visual C++ para ejecutarse. Aparecerá un cuadro de diálogo que le preguntará si desea instalarlo. Haga clic en **Sí**.
    
3. Al usar El programa de instalación inteligente, una nueva característica de Skype Empresarial Server, puede conectarse a Internet para buscar actualizaciones durante el proceso de instalación. Esto proporciona una mejor experiencia al asegurarse de que tiene las actualizaciones más recientes del producto durante la instalación. Haga clic en **Instalar** para comenzar el proceso de instalación.
    
4. Revise detenidamente el Contrato de licencia y, si está de acuerdo, seleccione **Acepto** los términos del contrato de licencia y haga clic en **Aceptar**.
    
5. Los Skype Empresarial Server componentes principales se instalarán en el servidor. 
    
    Los componentes principales constan de lo siguiente, como se muestra en la figura.
    
    ![Pantalla Componentes principales en aplicaciones.](../../media/0da1d983-4c4b-4b23-a196-c3bdba4857c6.png)
  
   - **Skype Empresarial Server de implementación** un programa de implementación que proporciona un controlador de inicio para instalar los distintos componentes de Skype Empresarial Server.
    
   - **Skype Empresarial Server Shell de administración** Un programa de PowerShell preconfigurado que permite la administración de Skype Empresarial Server.
    
     Una vez completada la instalación de los componentes principales, el Asistente Skype Empresarial Server implementación se iniciará automáticamente, como se muestra en la figura. 
    
     ![Skype Empresarial Server de implementación.](../../media/310c3437-83f9-48fa-a1e1-9fd09009fe31.png)
  
6. Además de los componentes principales, también tendrá que instalar Skype Empresarial Server Generador de topologías y Skype Empresarial Server panel de control en al menos un servidor del entorno. Haga **clic en Instalar herramientas administrativas** en el Asistente para implementación.
    
7. Haga clic en **Siguiente** para comenzar la instalación.
    
8. Una vez completada la instalación, haga clic **en Finalizar**. Las herramientas administrativas ahora se agregan al servidor, como se muestra en la figura.
    
    ![Skype Empresarial Server administrativas.](../../media/760873dd-9c87-4efb-bf98-7162d876fd18.png)
  
   - **Skype Empresarial Server generador de topologías** Un programa usado para crear, implementar y administrar topologías.
    
   - **Skype Empresarial Server Panel de control** Un programa usado para administrar la instalación.
    

