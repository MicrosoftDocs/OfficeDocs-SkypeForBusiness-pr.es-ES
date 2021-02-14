---
title: Crear un recurso compartido de archivos en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: 'Resumen: obtenga información sobre cómo crear un recurso compartido de archivos de Windows Server como parte de la instalación de Skype Empresarial Server. Descargue una prueba gratuita de Skype Empresarial Server desde el Centro de evaluación de Microsoft en: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server .'
ms.openlocfilehash: 63ed4c54154698336bea7adb87db4e81d5fd35b4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812240"
---
# <a name="create-a-file-share-in-skype-for-business-server"></a>Crear un recurso compartido de archivos en Skype Empresarial Server
 
**Resumen:** Obtenga información sobre cómo crear un recurso compartido de archivos de Windows Server como parte de la instalación de Skype Empresarial Server. Descargue una prueba gratuita de Skype Empresarial Server desde el Centro de evaluación de Microsoft en: [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server) .
  
Skype Empresarial Server requiere un recurso compartido de archivos para que los equipos de toda la topología puedan intercambiar archivos. La creación de un recurso compartido de archivos es el paso 2 de 8 en el proceso de instalación de Skype Empresarial Server. Puede realizar los pasos del 1 al 5 en cualquier orden. Sin embargo, debe realizar los pasos 6, 7 y 8 en orden y después de los pasos del 1 al 5, tal como se indica en el diagrama. Para obtener más información sobre la planeación del recurso compartido de archivos, consulte Requisitos del entorno [para Skype Empresarial Server](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) o requisitos de servidor para Skype Empresarial Server [2019.](../../../SfBServer2019/plan/system-requirements.md)
  
![Diagrama de información general](../../media/e69de059-3040-45ab-9379-1932f9fbb37f.png)
  
## <a name="create-a-basic-file-share"></a>Crear un recurso compartido de archivos básico

Esta sección te guiará a través de la creación de un recurso compartido de archivos básico de Windows Server. Skype Empresarial Server admite un recurso compartido de archivos básico de Windows Server. Sin embargo, no proporciona explícitamente alta disponibilidad. Para un entorno de alta disponibilidad, se recomienda un recurso compartido de archivos del Sistema de archivos distribuido (DFS). Para obtener más información acerca de un recurso compartido de archivos de alta disponibilidad y DFS, consulte [Plan for high availability and disaster recovery in Skype for Business Server](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).
  
> [!NOTE]
> Windows Server 2012 R2 ha realizado importantes avances al proporcionar soluciones de recursos compartidos de archivos como la Red de área de almacenamiento (SAN) con la plataforma Windows Server. En comparación con un dispositivo tradicional basado en SAN, una solución de almacenamiento de Windows Server 2012 R2 puede reducir los costos a la mitad con un impacto muy mínimo en el rendimiento. Para obtener más información acerca de las opciones de recurso compartido de archivos en Windows Server 2012 R2, vea las white paper descargables de Almacenamiento de [Windows Server 2012 R2.](https://download.microsoft.com/download/9/4/A/94A15682-02D6-47AD-B209-79D6E2758A24/Windows_Server_2012_R2_Storage_White_Paper.pdf) 
  
Vea los pasos de vídeo para **crear un recurso compartido de archivos:**
  
> [!video https://www.microsoft.com/videoplayer/embed/dbef31be-e899-4a32-a1ca-370053284f56?autoplay=false]
  
### <a name="create-a-basic-file-share"></a>Crear un recurso compartido de archivos básico

1. Inicie sesión en el equipo que hospedará el recurso compartido de archivos.
    
2. Haga clic con el botón secundario en la carpeta que desea compartir y seleccione **Propiedades.**
    
3. Seleccione la **pestaña Uso** compartido y haga clic en Uso **compartido avanzado.**
    
4. Haga **clic en Compartir esta carpeta.**
    
5. Haga clic en **Permisos**.
    
6. Agregue el grupo **de administradores** locales del servidor que hospeda el recurso compartido de archivos, conceda los derechos **Permitir: Control total,** Cambiar y Leer y, a continuación, haga clic en **Aceptar.**
    
7. Vuelva **a hacer clic** en Aceptar y tome nota de la ruta de red.
    
8. Haga **clic en Listo** para cerrar el asistente.
    
     ![Pestaña De uso compartido para compartir una carpeta.](../../media/78fe8441-dead-43ed-9a04-3c7c8c657c15.png)
  
> [!NOTE]
>Si el almacén de archivos está hospedado en un recurso compartido DFS, se recibirá la siguiente advertencia:

Advertencia: no se puede tener acceso a los permisos de uso compartido para " \\ <domain> \<share> ".

>Esto se espera si no es un administrador en el servidor de archivos o si se trata de un recurso compartido del Sistema de archivos distribuido (DFS). Si los permisos de recurso compartido ya se han configurado, esta advertencia puede omitirse. Si es un recurso compartido nuevo, consulte la documentación para obtener más información sobre cómo configurar manualmente los permisos de recurso compartido.

>Debido a la incapacidad de acceder a los permisos de recurso compartido en un recurso compartido DFS, Skype Empresarial Server no podrá establecer grupos explícitamente en el recurso compartido de archivos. Para asegurarse de que los componentes de Skype Empresarial Server puedan tener acceso al recurso compartido de archivos con los permisos adecuados, asegúrese de que se agregan los siguientes grupos RTC con permisos de recurso compartido de nivel de lectura y cambio, además de los permisos de recurso compartido administradores locales con control total.
* RTCHSUniversalServices
* RTCComponentUniversalServices
* RTCUniversalServerAdmins
