---
title: Crear un recurso compartido de archivos en Skype para Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 12/20/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 053076b0-441c-44d9-8dbc-7a36d8ecafe4
description: 'Resumen: Obtenga información sobre cómo crear un recurso compartido de archivos de Windows Server como parte de la instalación de Skype para Business Server. Descargue una versión de prueba gratuita de Skype para Business Server desde el Evaluation de Microsoft center en: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server.'
ms.openlocfilehash: 36b965e829e3bd02e884f55127e202d1c27eff50
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33891960"
---
# <a name="create-a-file-share-in-skype-for-business-server"></a>Crear un recurso compartido de archivos en Skype para Business Server
 
**Resumen:** Obtenga información sobre cómo crear un recurso compartido de archivos de Windows Server como parte de la instalación de Skype para Business Server. Descargue una versión de prueba gratuita de Skype para Business Server desde el Evaluation de Microsoft center en:[https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).
  
Skype para Business Server requiere un recurso compartido de archivos para que los equipos en toda la topología pueden intercambiar archivos. Creación de un recurso compartido de archivos es el paso 2 de 8 en el proceso de instalación de Skype para Business Server. Se pueden realizar los pasos del 1 al 5 en cualquier orden. Sin embargo, debe realizar los pasos 6, 7 y 8 en orden y después de los pasos del 1 al 5 tal como se indica en el diagrama. Para la planeación de obtener información detallada sobre el recurso compartido de archivos, vea [requisitos de entorno para Skype para Business Server](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) o [requisitos de servidor para Skype para Business Server 2019](../../../SfBServer2019/plan/system-requirements.md).
  
![Diagrama de información general](../../media/e69de059-3040-45ab-9379-1932f9fbb37f.png)
  
## <a name="create-a-basic-file-share"></a>Crear un recurso compartido de archivos básico

En esta sección le guiará a través de la creación de un recurso compartido básico de Windows Server. Un recurso compartido de Windows Server básico es compatible con Skype para Business Server. Sin embargo, no explícitamente proporciona una alta disponibilidad. Para un entorno de alta disponibilidad, se recomienda un recurso compartido de archivos de sistema de archivos distribuido (DFS). Para obtener más información acerca de un recurso compartido de archivos de alta disponibilidad y DFS, consulte [Plan de alta disponibilidad y recuperación ante desastres en Skype para Business Server](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).
  
> [!NOTE]
> Se han realizado importantes avances en Windows Server 2012 R2 a fin de proporcionar soluciones de recursos compartidos de archivos similares a la red de área de almacenamiento (SAN) con la plataforma de Windows Server. Cuando se la compara con un dispositivo basado en SAN tradicional, una solución de almacenamiento de Windows Server 2012 R2 puede reducir los costes a la mitad con un impacto muy mínimo en el rendimiento. Para obtener más información acerca de las opciones del recurso compartido de archivo en Windows Server 2012 R2, vea el [Almacenamiento de Windows Server 2012 R2](https://download.microsoft.com/download/9/4/A/94A15682-02D6-47AD-B209-79D6E2758A24/Windows_Server_2012_R2_Storage_White_Paper.pdf)notas del producto descargables. 
  
Vea los pasos del vídeo para **crear un recurso compartido de archivos**:
  
> [!video https://www.microsoft.com/en-us/videoplayer/embed/dbef31be-e899-4a32-a1ca-370053284f56?autoplay=false]
  
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
  
> [!NOTE]
>Si el almacén de archivos está hospedado en un DFS compartir, se recibirá la advertencia siguiente:

Advertencia: No se puede tener acceso a los permisos de recurso compartido para "\\<domain>\<share>".

>Esto se espera si no es un administrador en el servidor de archivos, o si se trata de un recurso compartido de sistema de archivos distribuido (DFS). Si ya se han configurado los permisos de recurso compartido, puede ignorar esta advertencia. Si es un nuevo recurso compartido, consulte la documentación para obtener información detallada acerca de la configuración manualmente los permisos de recurso compartido.

>Debido a la imposibilidad de tener acceso a los permisos de recurso compartido en un recurso compartido de DFS, Skype para Business Server no podrá establecer explícitamente grupos en el recurso compartido de archivos. Para asegurarse de Skype para los componentes de Business Server puede tener acceso a recurso compartido de archivos con los permisos adecuados, asegúrese de que se agregan los siguientes grupos RTC con permisos de nivel de recurso compartido de cambio además de los administradores locales con permisos de recurso compartido Control total.

RTCHSUniversalServices RTCComponentUniversalServices RTCUniversalServerAdmins
