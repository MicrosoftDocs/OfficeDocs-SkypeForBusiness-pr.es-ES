---
title: Instalar herramientas administrativas en Skype Empresarial Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 7/14/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 52ee7da4-59ba-499a-a105-d93fa9941334
description: 'Resumen: Obtenga información sobre cómo instalar las herramientas administrativas necesarias para una instalación de Skype para Business Server 2015. Descargue una versión de prueba gratuita de Skype para Business Server 2015 desde el Evaluation de Microsoft center en: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server.'
ms.openlocfilehash: 104919e66ea16777582d28617c78853ba6f2f1e3
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="install-administrative-tools-in-skype-for-business-server-2015"></a>Instalar herramientas administrativas en Skype Empresarial Server 2015
 
**Resumen:** Obtenga información sobre cómo instalar las herramientas administrativas necesarias para una instalación de Skype para Business Server 2015. Descargue una versión de prueba gratuita de Skype para Business Server 2015 desde el Evaluation de Microsoft center en: [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).
  
Las herramientas administrativas de incluyen el generador de topología y en el Panel de Control. Las herramientas administrativas de deben instalarse en al menos un servidor en la topología o en una estación de trabajo de administración de 64 bits que ejecuta una versión de sistema operativo de Windows que es compatible con Skype para Business Server. Se pueden realizar los pasos del 1 al 5 en cualquier orden. Sin embargo, debe realizar los pasos 6, 7 y 8 en orden y después de los pasos del 1 al 5, tal como se indica en el diagrama. Instalar las herramientas administrativas es el paso 3 de 8.
  
![Diagrama de información general](../../media/d856afe8-4758-432f-bc45-e1956016419a.png)
  
## <a name="install-skype-for-business-server-2015-administrative-tools"></a>Instalar Skype para las herramientas administrativas de Business Server 2015

Los medios de instalación de Skype para Business Server 2015 proporcionan una experiencia flexible. Cuando ejecuta Setup.exe por primera vez, instaladas las herramientas de sólo son el Skype para el Asistente para la implementación de servidor de negocio y la Skype para Shell de administración de servidor empresarial. Mediante el uso de estas dos herramientas, conocidas como los componentes principales, puede continuar con el proceso de instalación, pero no proporcionan la funcionalidad principal para el Skype general para el entorno de servidor empresarial. El Asistente para la implementación se inicia automáticamente después de instalar los componentes principales. La sección del Asistente para la implementación titulada **Instalar las herramientas administrativas** instala Skype para Business Server Topology Builder y Skype para el Panel de Control de servidor empresarial.
  
> [!IMPORTANT]
> Cada Skype para entorno Business Server debe tener al menos un servidor con las herramientas administrativas instaladas. 
  
Vea los pasos del vídeo para **Instalar herramientas administrativas**:
  
> [!video https://www.microsoft.com/en-us/videoplayer/embed/99a5c436-963b-4eed-b423-651568c87cb1?autoplay=false]
  
### <a name="install-skype-for-business-server-2015-administrative-tools-from-the-deployment-wizard"></a>Instalar Skype para Business Server 2015 herramientas administrativas desde el Asistente para la implementación

1. Inserte el Skype para los medios de instalación de Business Server 2015. Si la configuración no empieza automáticamente, haga doble clic en **Configuración**.
    
2. La ejecución del disco de instalación necesita Microsoft Visual C++. Aparecerá un cuadro de diálogo preguntándole si quiere instalarlo. Haga clic en **Sí**.
    
3. Mediante el uso del programa de instalación inteligente, una nueva característica de Skype para Business Server 2015, puede conectarse a Internet para comprobar las actualizaciones durante el proceso de instalación. Esto proporciona una mejor experiencia, ya que se asegura de que dispone de las actualizaciones más recientes del producto en el momento de la instalación. Haga clic en **Instalar** para empezar la instalación.
    
4. Revise cuidadosamente el contrato de licencia y, si está de acuerdo, elija **Acepto los términos del Contrato de licencia** y haga clic en **Aceptar**.
    
5. El Skype para los componentes principales de Business Server 2015 se instalará en el servidor. 
    
    Estos componentes incluyen lo siguiente, como se muestra en la figura.
    
    ![Componentes principales de la pantalla Aplicaciones.](../../media/0da1d983-4c4b-4b23-a196-c3bdba4857c6.png)
  
  - **Skype para Business Server 2015 Asistente para la implementación** Un programa de implementación que proporciona un panel de inicio para la instalación de los diversos componentes de Skype para Business Server 2015.
    
  - **Skype para Shell de administración de Business Server 2015** Un programa de PowerShell preconfigurado que permite la administración de Skype para Business Server 2015.
    
    Una vez finalizada la instalación de los componentes principales, se iniciará automáticamente la Skype para el Asistente para la implementación de Business Server 2015, tal como se muestra en la ilustración. 
    
    ![Asistente de implementación del servidor de Skype Empresarial 2015](../../media/310c3437-83f9-48fa-a1e1-9fd09009fe31.png)
  
6. Además de los componentes principales, también tendrá que instalar Skype para Business Server 2015 Topology Builder y Skype para el Panel de Control de Business Server 2015 en al menos un servidor en el entorno. Haga clic en **Instalar herramientas administrativas** en el Asistente para la implementación.
    
7. Haga clic en **Siguiente** para empezar la instalación.
    
8. Una vez que se completa la instalación, haga clic en **Finalizar**. Ahora, como se ve en la figura, se agregan las herramientas administrativas en el servidor.
    
    ![Herramientas administrativas del servidor de Skype Empresarial 2015](../../media/760873dd-9c87-4efb-bf98-7162d876fd18.png)
  
   - **Skype para Business Server 2015 Topology Builder** Un programa que se utiliza para crear, implementar y administrar las topologías.
    
   - **Skype para el Panel de Control de Business Server 2015** Un programa que se utiliza para la instalación.
    

