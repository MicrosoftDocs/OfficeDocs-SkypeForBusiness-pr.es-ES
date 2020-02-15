---
title: Crear un recurso compartido de archivos en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 12/20/2018
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
ms.assetid: 053076b0-441c-44d9-8dbc-7a36d8ecafe4
description: 'Resumen: Obtenga información sobre cómo crear un recurso compartido de archivos de Windows Server como parte de la instalación de Skype empresarial Server. Descargue una versión de prueba gratuita de Skype empresarial Server del centro de evaluación de Microsoft https://www.microsoft.com/evalcenter/evaluate-skype-for-business-serveren:.'
ms.openlocfilehash: 74c2c8ddedfb6c2a751822fec51636dddd7747dc
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42028301"
---
# <a name="create-a-file-share-in-skype-for-business-server"></a>Crear un recurso compartido de archivos en Skype empresarial Server
 
**Resumen:** Obtenga información sobre cómo crear un recurso compartido de archivos de Windows Server como parte de la instalación de Skype empresarial Server. Descargue una versión de prueba gratuita de Skype empresarial Server del centro de evaluación de Microsoft[https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)en:.
  
Skype empresarial Server requiere un recurso compartido de archivos para que los equipos de toda la topología puedan intercambiar archivos. La creación de un recurso compartido de archivos es el paso 2 de 8 en el proceso de instalación de Skype empresarial Server. Puede realizar los pasos del 1 al 5 en cualquier orden. Sin embargo, debe realizar los pasos 6, 7 y 8 en orden, y después de los pasos 1 a 5, tal como se describe en el diagrama. Para obtener información sobre la planeación de recursos compartidos de archivos, consulte [Environmental Requirements for Skype for Business Server](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) o [Server Requirements for Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md).
  
![Diagrama de información general](../../media/e69de059-3040-45ab-9379-1932f9fbb37f.png)
  
## <a name="create-a-basic-file-share"></a>Crear un recurso compartido de archivos básico

En esta sección se explica cómo crear un recurso compartido de archivos básico de Windows Server. Skype empresarial Server admite un recurso compartido de archivos básico de Windows Server. Sin embargo, no proporciona de forma explícita alta disponibilidad. Para un entorno de alta disponibilidad, se recomienda un recurso compartido de archivos del sistema de archivos distribuido (DFS). Para obtener más información acerca de un recurso compartido de archivos y DFS de alta disponibilidad, consulte [Plan for High Availability and Disaster Recovery in Skype for Business Server](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).
  
> [!NOTE]
> Windows Server 2012 R2 ha realizado grandes saltos en el suministro de soluciones de recursos compartidos de archivos de red de área de almacenamiento (SAN) mediante la plataforma de Windows Server. En comparación con un dispositivo tradicional basado en SAN, una solución de almacenamiento de Windows Server 2012 R2 puede reducir los costos a la mitad con un impacto muy mínimo en el rendimiento. Para obtener más información acerca de las opciones de recursos compartidos de archivos en Windows Server 2012 R2, consulte el documento descargable en el [almacenamiento de Windows server 2012 R2](https://download.microsoft.com/download/9/4/A/94A15682-02D6-47AD-B209-79D6E2758A24/Windows_Server_2012_R2_Storage_White_Paper.pdf). 
  
Vea los pasos del vídeo para **crear un recurso compartido de archivos**:
  
> [!video https://www.microsoft.com/videoplayer/embed/dbef31be-e899-4a32-a1ca-370053284f56?autoplay=false]
  
### <a name="create-a-basic-file-share"></a>Crear un recurso compartido de archivos básico

1. Inicie sesión en el equipo en el que se va a hospedar el recurso compartido de archivos.
    
2. Haga clic con el botón secundario en la carpeta que vaya a compartir y seleccione **propiedades**.
    
3. Seleccione la pestaña **uso compartido** y haga clic en **uso compartido avanzado**.
    
4. Haga clic en **compartir esta carpeta**.
    
5. Haga clic en **Permisos**.
    
6. Agregue el grupo de **administradores** locales del servidor que hospeda el recurso compartido de archivos, concédale los derechos **permitir: control total, cambiar y leer** y, a continuación, haga clic en **Aceptar**.
    
7. Vuelva a hacer clic en **Aceptar** y tome nota de la ruta de acceso de la red.
    
8. Haga clic en **listo** para cerrar el asistente.
    
     ![Ficha compartir para compartir una carpeta.](../../media/78fe8441-dead-43ed-9a04-3c7c8c657c15.png)
  
> [!NOTE]
>Si el almacén de archivos está hospedado en un recurso compartido DFS, se recibirá la siguiente ADVERTENCIA:

ADVERTENCIA: no se puede tener acceso a los\\<domain>\<permisos de recurso compartido para "compartir>".

>Se espera si no es un administrador en el servidor de archivos o si se trata de un recurso compartido de sistema de archivos distribuido (DFS). Si los permisos de recurso compartido ya se han configurado, se puede omitir esta advertencia. Si es un nuevo recurso compartido, consulte la documentación para obtener más información sobre cómo configurar manualmente los permisos de uso compartido.

>Debido a la incapacidad de tener acceso a los permisos de uso compartido en un recurso compartido DFS, Skype empresarial Server no podrá establecer de forma explícita grupos en el recurso compartido de archivos. Para asegurarse de que los componentes de Skype empresarial Server puedan acceder al recurso compartido de archivos con los permisos adecuados, asegúrese de que se agregan los siguientes grupos de RTC con los permisos de uso compartido de nivel de lectura y de modificación, además de los administradores locales con el recurso compartido de control total los.
* RTCHSUniversalServices
* RTCComponentUniversalServices
* RTCUniversalServerAdmins
