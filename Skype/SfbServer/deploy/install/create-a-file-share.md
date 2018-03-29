---
title: Crear un recurso compartido de archivos en Skype Empresarial Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 053076b0-441c-44d9-8dbc-7a36d8ecafe4
description: 'Resumen: Conozca cómo crear un recurso compartido de archivos de Windows Server como parte de la instalación de Skype para Business Server 2015. Descargue una prueba gratuita de Skype para Business Server 2015 desde el centro de Evaluation de Microsoft en: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server.'
ms.openlocfilehash: 697325cbe7616ca82734895e1af4922aeb580068
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="create-a-file-share-in-skype-for-business-server-2015"></a>Crear un recurso compartido de archivos en Skype Empresarial Server 2015
 
**Resumen:** Aprenda a crear un recurso compartido de archivos de Windows Server como parte de la instalación de Skype para Business Server 2015. Descargue una prueba gratuita de Skype para Business Server 2015 desde el centro de Evaluation de Microsoft en:[https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).
  
Skype para Business Server requiere un recurso compartido de archivos para que los equipos de toda la topología pueden intercambiar archivos. Crear un recurso compartido de archivo es el paso 2 de 8 en el proceso de instalación de Skype para Business Server 2015. Puede realizar los pasos 1 a 5 en cualquier orden. Sin embargo, debe realizar los pasos 6, 7 y 8 en orden y después los pasos del 1 al 5 como se indica en el diagrama. Para planear los detalles sobre el recurso compartido de archivos, consulte [los requisitos ambientales para Skype para Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md).
  
![Diagrama de información general](../../media/e69de059-3040-45ab-9379-1932f9fbb37f.png)
  
## <a name="create-a-basic-file-share"></a>Crear un recurso compartido de archivos básico

Esta sección le guiará a través de la creación de un archivo compartido básico de Windows Server. Un archivo compartido básico de Windows Server es compatible con Skype para Business Server. Sin embargo, no explícitamente proporciona alta disponibilidad. Para un entorno de alta disponibilidad, se recomienda un recurso compartido de archivos de sistema de archivos distribuido (DFS). Para obtener más información acerca de un recurso compartido de archivos de alta disponibilidad y DFS, vea [Planear la alta disponibilidad y recuperación ante desastres en Skype para Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).
  
> [!NOTE]
> Se han realizado importantes avances en Windows Server 2012 R2 a fin de proporcionar soluciones de recursos compartidos de archivos similares a la red de área de almacenamiento (SAN) con la plataforma de Windows Server. Cuando se la compara con un dispositivo basado en SAN tradicional, una solución de almacenamiento de Windows Server 2012 R2 puede reducir los costes a la mitad con un impacto muy mínimo en el rendimiento. Para obtener más información acerca de las opciones de recurso compartido de archivo en Windows Server 2012 R2, consulte el documento descargable [Almacenamiento de R2 de Windows Server 2012](https://download.microsoft.com/download/9/4/A/94A15682-02D6-47AD-B209-79D6E2758A24/Windows_Server_2012_R2_Storage_White_Paper.pdf). 
  
Vea los pasos del vídeo para **crear un recurso compartido de archivos**:
  
![Su explorador no admite vídeo. Instale Microsoft Silverlight, Adobe Flash Player o Internet Explorer 9.](../../media/MSN_Video_Widget.gif)
  
### <a name="create-a-basic-file-share"></a>Crear un recurso compartido de archivos básico

1. Inicie sesión en el equipo que hospedará el recurso compartido de archivos.
    
2. Haga clic con el botón secundario en la carpeta que desea compartir y seleccione **Propiedades**.
    
3. Seleccione la pestaña **Uso compartido** y haga clic en **Uso compartido avanzado**.
    
4. Haga clic en **Compartir esta carpeta**.
    
5. Haga clic en **Permisos**.
    
6. Agregue el grupo **Administradores** local del servidor que aloja el recurso compartido de archivos, conceda derechos **Permitir: Control total, Cambiar y Leer** y, a continuación, haga clic en **Aceptar**.
    
7. Haga clic en **Aceptar** nuevamente y tome nota de la ruta de acceso a la red.
    
8. Haga clic en **Listo** para cerrar el asistente.
    
     ![Pestaña Uso compartido para compartir una carpeta.](../../media/78fe8441-dead-43ed-9a04-3c7c8c657c15.png)
  

