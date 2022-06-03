---
title: Instalación de herramientas administrativas en Skype Empresarial Server
ms.reviewer: ''
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
ms.custom: ''
ms.assetid: 52ee7da4-59ba-499a-a105-d93fa9941334
description: 'Resumen: obtenga información sobre cómo instalar las herramientas administrativas necesarias para la instalación de Skype Empresarial Server.'
ms.openlocfilehash: e18ad5953eb063cdb91ea2927ad03ed1057c840a
ms.sourcegitcommit: e99471689ff60f9ab1095bc075f8b4c5569c9634
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2022
ms.locfileid: "65860531"
---
# <a name="install-administrative-tools-in-skype-for-business-server"></a>Instalación de herramientas administrativas en Skype Empresarial Server
 
**Resumen:** Obtenga información sobre cómo instalar las herramientas administrativas necesarias para la instalación de Skype Empresarial Server.
  
Las herramientas administrativas incluyen el Generador de topologías y el Panel de control. Las herramientas administrativas deben instalarse en al menos un servidor de la topología o en una estación de trabajo de administración de 64 bits que ejecute una versión Windows del sistema operativo que sea compatible con Skype Empresarial Server. Puede realizar los pasos del 1 al 5 en cualquier orden. Sin embargo, debe realizar los pasos 6, 7 y 8 en orden, y después de los pasos del 1 al 5, como se describe en el diagrama. La instalación de las herramientas administrativas es el paso 3 del 8.
  
![Diagrama de información general.](../../media/d856afe8-4758-432f-bc45-e1956016419a.png)
  
## <a name="install-skype-for-business-server-administrative-tools"></a>Instalar Skype Empresarial Server herramientas administrativas

Los medios de instalación para Skype Empresarial Server proporcionan una experiencia flexible. Al ejecutar por primera vez Setup.exe, las únicas herramientas instaladas son el Asistente para la implementación de Skype Empresarial Server y el Shell de administración de Skype Empresarial Server. Con estas dos herramientas, conocidas como componentes principales, puede continuar con el proceso de instalación, pero no proporcionan funcionalidad principal para el entorno de Skype Empresarial Server general. El Asistente para implementación se inicia automáticamente después de instalar los componentes principales. La sección del Asistente para implementación titulada **Instalar herramientas administrativas** instala Skype Empresarial Server Generador de topologías y Skype Empresarial Server Panel de control.
  
> [!IMPORTANT]
> Cada entorno Skype Empresarial Server debe tener al menos un servidor con las herramientas administrativas instaladas. 
  
Vea los pasos de vídeo para **Instalar herramientas administrativas**:
  
> [!video https://www.microsoft.com/videoplayer/embed/99a5c436-963b-4eed-b423-651568c87cb1?autoplay=false]
  
### <a name="install-skype-for-business-server-administrative-tools-from-the-deployment-wizard"></a>Instalar Skype Empresarial Server herramientas administrativas desde el Asistente para implementación

1. Inserte el medio de instalación Skype Empresarial Server. Si la instalación no se inicia automáticamente, haga doble clic en **Configurar**.
    
2. El medio de instalación requiere Microsoft Visual C++ para ejecutarse. Aparecerá un cuadro de diálogo que le preguntará si desea instalarlo. Haga clic en **Sí**.
    
3. Mediante la instalación inteligente, una nueva característica de Skype Empresarial Server, puede conectarse a Internet para comprobar si hay actualizaciones durante el proceso de instalación. Esto proporciona una mejor experiencia asegurándose de que tiene las actualizaciones más recientes del producto durante la instalación. Haga clic en **Instalar** para comenzar el proceso de instalación.
    
4. Revise cuidadosamente el Contrato de licencia y, si está de acuerdo, seleccione **Acepto los términos del contrato de licencia** y haga clic en **Aceptar**.
    
5. Los componentes principales de Skype Empresarial Server se instalarán en el servidor. 
    
    Los componentes principales constan de lo siguiente, como se muestra en la ilustración.
    
    ![Pantalla Componentes principales en aplicaciones.](../../media/0da1d983-4c4b-4b23-a196-c3bdba4857c6.png)
  
   - **Skype Empresarial Server Asistente para implementación** Un programa de implementación que proporciona un panel de inicio para instalar los distintos componentes de Skype Empresarial Server.
    
   - **Skype Empresarial Server Shell de administración** Un programa de PowerShell preconfigurado que permite la administración de Skype Empresarial Server.
    
     Una vez completada la instalación de los componentes principales, el Asistente para la implementación de Skype Empresarial Server se iniciará automáticamente, como se muestra en la ilustración. 
    
     ![Asistente para la implementación de Skype Empresarial Server.](../../media/310c3437-83f9-48fa-a1e1-9fd09009fe31.png)
  
6. Además de los componentes principales, también tendrá que instalar Skype Empresarial Server Generador de topologías y Skype Empresarial Server Panel de control en al menos un servidor del entorno. Haga clic en **Instalar herramientas administrativas** en el Asistente para implementación.
    
7. Haga clic en **Siguiente** para comenzar la instalación.
    
8. Una vez completada la instalación, haga clic en **Finalizar**. Las herramientas administrativas ahora se agregan al servidor, como se muestra en la ilustración.
    
    ![Skype Empresarial Server Herramientas administrativas.](../../media/760873dd-9c87-4efb-bf98-7162d876fd18.png)
  
   - **Skype Empresarial Server Generador de topologías** Programa usado para compilar, implementar y administrar topologías.
    
   - **Skype Empresarial Server Panel de control** Programa utilizado para administrar la instalación.
    

