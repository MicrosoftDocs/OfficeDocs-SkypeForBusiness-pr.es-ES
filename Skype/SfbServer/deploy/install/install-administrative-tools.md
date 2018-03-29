---
title: Instalar herramientas administrativas en Skype Empresarial Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 7/14/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 52ee7da4-59ba-499a-a105-d93fa9941334
description: 'Resumen: Conozca cómo instalar las herramientas administrativas necesarias para una instalación de Skype para Business Server 2015. Descargue una prueba gratuita de Skype para Business Server 2015 desde el centro de Evaluation de Microsoft en: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server.'
ms.openlocfilehash: e54dfd4b29f3947b58517007949922a5c1230d51
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="install-administrative-tools-in-skype-for-business-server-2015"></a>Instalar herramientas administrativas en Skype Empresarial Server 2015
 
**Resumen:** Obtenga información acerca de cómo instalar las herramientas administrativas necesarias para una instalación de Skype para Business Server 2015. Descargue una prueba gratuita de Skype para Business Server 2015 desde el centro de Evaluation de Microsoft en: [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).
  
Las herramientas administrativas incluyen el generador de topología y el Panel de Control. Las herramientas administrativas deben instalarse en al menos un servidor en la topología o en una estación de trabajo de administración de 64 bits que ejecuta una versión de sistema operativo de Windows que es compatible con Skype para Business Server. Puede realizar los pasos 1 a 5 en cualquier orden. Sin embargo, debe realizar los pasos 6, 7 y 8 en orden y después los pasos del 1 al 5, tal como se indica en el diagrama. Instalar las herramientas administrativas es el paso 3 de 8.
  
![Diagrama de información general](../../media/d856afe8-4758-432f-bc45-e1956016419a.png)
  
## <a name="install-skype-for-business-server-2015-administrative-tools"></a>Instalar Skype para herramientas administrativas Business Server 2015

Los medios de instalación de Skype para Business Server 2015 proporcionan una experiencia flexible. Cuando ejecuta Setup.exe por primera vez, las únicas herramientas instaladas son el Skype para el Asistente para implementación de Business Server y el Skype para el Shell de administración de servidor empresarial. Mediante el uso de estas dos herramientas, conocidas como componentes principales, puede continuar con el proceso de instalación, pero no proporcionan la funcionalidad principal para el Skype para el entorno de servidor empresarial general. El Asistente para la implementación se inicia automáticamente después de instalar los componentes principales. La sección del Asistente de implementación titulado **Instalar herramientas administrativas** instala Skype para el generador de topología de servidor empresarial y Skype para Business Server Control Panel.
  
> [!IMPORTANT]
> Cada Skype para entorno Business Server debe tener al menos un servidor con las herramientas administrativas instaladas. 
  
Vea los pasos del vídeo para **Instalar herramientas administrativas**:
  
![Su explorador no admite vídeo. Instale Microsoft Silverlight, Adobe Flash Player o Internet Explorer 9.](../../media/MSN_Video_Widget.gif)
  
### <a name="install-skype-for-business-server-2015-administrative-tools-from-the-deployment-wizard"></a>Instalar Skype para Business Server 2015 herramientas administrativas desde el Asistente para implementación

1. Inserte el Skype para los medios de instalación de Business Server 2015. Si la configuración no empieza automáticamente, haga doble clic en **Configuración**.
    
2. La ejecución del disco de instalación necesita Microsoft Visual C++. Aparecerá un cuadro de diálogo preguntándole si quiere instalarlo. Haga clic en **Sí**.
    
3. De forma inteligente, una nueva característica de Skype para Business Server 2015, puede conectarse a Internet para buscar actualizaciones durante el proceso de instalación. Esto proporciona una mejor experiencia, ya que se asegura de que dispone de las actualizaciones más recientes del producto en el momento de la instalación. Haga clic en **Instalar** para empezar la instalación.
    
4. Revise cuidadosamente el contrato de licencia y, si está de acuerdo, elija **Acepto los términos del Contrato de licencia** y haga clic en **Aceptar**.
    
5. El Skype para componentes de núcleo de 2015 Business Server se instalará en el servidor. 
    
    Estos componentes incluyen lo siguiente, como se muestra en la figura.
    
    ![Componentes principales de la pantalla Aplicaciones.](../../media/0da1d983-4c4b-4b23-a196-c3bdba4857c6.png)
  
  - **Skype para el Asistente de implementación de Business Server 2015** Programa de implementación que proporciona una plataforma de lanzamiento para instalar los diferentes componentes de Skype para Business Server 2015.
    
  - **Skype para el Shell de administración de negocio servidor 2015** Un programa de PowerShell preconfigurado que permite administración de Skype para Business Server 2015.
    
    Una vez finalizada la instalación de los componentes principales, se iniciará automáticamente el Skype para el Asistente para implementación de Business Server 2015, como se muestra en la figura. 
    
    ![Asistente de implementación del servidor de Skype Empresarial 2015](../../media/310c3437-83f9-48fa-a1e1-9fd09009fe31.png)
  
6. Además de los componentes principales, también necesitará instalar Skype para el generador de topología de Business Server 2015 y Skype para Panel de Control de Business Server 2015 en al menos un servidor en el entorno. Haga clic en **Instalar herramientas administrativas** en el Asistente para la implementación.
    
7. Haga clic en **Siguiente** para empezar la instalación.
    
8. Una vez que se completa la instalación, haga clic en **Finalizar**. Ahora, como se ve en la figura, se agregan las herramientas administrativas en el servidor.
    
    ![Herramientas administrativas del servidor de Skype Empresarial 2015](../../media/760873dd-9c87-4efb-bf98-7162d876fd18.png)
  
   - **Skype para el generador de topología Business Server 2015** Un programa utilizado para generar, implementar y administrar topologías.
    
   - **Skype para Panel de Control de Business Server 2015** Un programa que se utiliza para administrar la instalación.
    

