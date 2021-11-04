---
title: Instalar los archivos del servidor de mediación en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
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
ms.assetid: f0f7dd15-58e1-40fd-aa7e-6db50ceafacd
description: 'Resumen: obtenga información sobre cómo instalar los archivos del servidor de mediación en Skype Empresarial Server.'
ms.openlocfilehash: 8dcc6862b55a4620030d03ed442a24e22ccde54b
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2021
ms.locfileid: "60769628"
---
# <a name="install-the-files-for-mediation-server-in-skype-for-business-server"></a>Instalar los archivos del servidor de mediación en Skype Empresarial Server
 
**Resumen:** Obtenga información sobre cómo instalar los archivos del servidor de mediación en Skype Empresarial Server.
  
Para completar correctamente este procedimiento, debe iniciar sesión en el servidor, como mínimo, como administrador local y como usuario de dominio que tenga pertenencia al menos al grupo RTCUniversalReadOnlyAdmins.
  
Siga los pasos descritos en este tema para ejecutar el Asistente para la implementación de Skype Empresarial Server para instalar los archivos del servidor de mediación en un equipo que agregó a un grupo de servidores de mediación después de usar el Generador de topologías para definir y publicar el grupo. Al instalar archivos servidor de mediación, también se instala y asigna el certificado requerido por cada equipo en un grupo de servidores de mediación. 
  
> [!NOTE]
> En este tema se supone que ya ha definido y publicado un grupo de servidores de mediación independiente en la topología, tal como se describe en [Deploy a Mediation Server in Topology Builder in Skype Empresarial Server](deploy-a-mediation-server.md). 
  
### <a name="to-install-the-files-for-a-stand-alone-mediation-server-pool"></a>Para instalar los archivos de un grupo de servidores de mediación independiente

1. En el medio de instalación, haga clic con el botón\Setup\amd64\Setup.exey, a continuación, haga  _\<installation media\>_ **** clic en Ejecutar **como administrador**.
    
2. En la **página Ubicación de** instalación, haga clic en **Aceptar**.
    
3. En la **página Contrato de licencia de usuario** final, haga clic en **Acepto** y, a continuación, haga clic en **Aceptar**. (Necesario para continuar).
    
4. En la **página asistente Skype Empresarial Server implementación,** haga clic **en Instalar o actualizar Skype Empresarial Server sistema**.
    
5. Junto al **paso 1: Instalar el almacén de configuración local,** haga clic **en Ejecutar** y, a continuación, siga las instrucciones que aparecen en la pantalla.
    
6. En la página Configurar réplica local del almacén de administración **central,** acepte el valor predeterminado Recuperar directamente desde el Almacén **de administración central** y, a continuación, haga clic en **Siguiente**.
    
7. En la **página Ejecutar comandos,** cuando el estado de la tarea se muestra como **Completado,** haga clic en **Finalizar**.
    
8. Junto al **paso 2: Configurar** o quitar componentes Skype Empresarial Server , haga clic **en Ejecutar** y, a continuación, haga clic en **Siguiente**.
    
9. En la **página Ejecutar comandos,** cuando el estado de la tarea se muestra como **Completado,** haga clic en **Finalizar**.
    
10. Junto al **paso 3: Solicitar, instalar o** asignar certificados , haga clic en **Ejecutar**. Siga las instrucciones de la pantalla, aceptando la configuración predeterminada. El servidor de mediación requiere un certificado, por lo que ejecutará el paso **3** dos veces: una para emitir el certificado necesario y otra para asignarlo.
    
11. Cuando el certificado se haya emitido y asignado correctamente, junto a **Paso 4: Iniciar** servicios , haga clic en **Ejecutar** y, a continuación, siga las instrucciones de la pantalla.
    
12. Cuando **el paso 4 se** haya completado correctamente, reinicie el servidor e inicie sesión en el servidor como miembro del grupo DomainAdmins.
    
13. En el equipo donde ejecuta Skype Empresarial Server Panel de control, compruebe en la página Topología del Panel de control de Skype Empresarial Server que el estado del servicio del servidor de mediación se muestra como una marca de verificación verde.  Si en su lugar aparece una X roja, seleccione el servidor de mediación. En el **menú Acción,** haga clic **en Iniciar todos los servicios**. 
    
Si agregó más de un equipo al grupo de servidores de mediación, realice los pasos descritos en este procedimiento en todos los demás equipos del grupo de servidores de mediación. Si no necesita instalar archivos para el servidor de mediación para otros equipos, siga los procedimientos descritos en Configurar [troncos](configure-trunks.md) en Skype Empresarial Server para configurar la conexión de tronco entre este grupo de servidores de mediación (o todos los servidores de mediación de un sitio) y su mismo nivel.

