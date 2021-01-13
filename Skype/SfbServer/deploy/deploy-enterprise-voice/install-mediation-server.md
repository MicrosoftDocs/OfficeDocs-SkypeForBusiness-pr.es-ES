---
title: Instalar los archivos para el servidor de mediación en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
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
ms.assetid: f0f7dd15-58e1-40fd-aa7e-6db50ceafacd
description: 'Resumen: obtenga información sobre cómo instalar los archivos del servidor de mediación en Skype Empresarial Server.'
ms.openlocfilehash: 80f25d9fab37555d5b4e9dc3d610c5c9037c934d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830800"
---
# <a name="install-the-files-for-mediation-server-in-skype-for-business-server"></a>Instalar los archivos para el servidor de mediación en Skype Empresarial Server
 
**Resumen:** Obtenga información sobre cómo instalar los archivos para el servidor de mediación en Skype Empresarial Server.
  
Para completar correctamente este procedimiento, debe haber iniciado sesión, como mínimo, en el servidor como administrador local y usuario de dominio que sea miembro del grupo RTCUniversalReadOnlyAdmins como mínimo.
  
Siga los pasos de este tema para ejecutar el Asistente para la implementación de Skype Empresarial Server para instalar los archivos del servidor de mediación en un equipo que agregó a un grupo de servidores de mediación después de haber usado el Generador de topologías para definir y publicar el grupo. Al instalar el servidor de mediación de archivos, también se instala y asigna el certificado requerido por cada equipo de un grupo de servidores de mediación. 
  
> [!NOTE]
> En este tema se supone que ya ha definido y publicado un grupo de servidores de mediación independiente en su topología, tal como se describe en Implementar un servidor de mediación en el Generador de topologías en [Skype Empresarial Server.](deploy-a-mediation-server.md) 
  
### <a name="to-install-the-files-for-a-stand-alone-mediation-server-pool"></a>Para instalar los archivos de un grupo de servidores de mediación independiente

1. En el medio de instalación, haga clic con el botón\Setup\amd64\Setup.exey, a continuación, haga clic _\<installation media\>_ **** en Ejecutar **como administrador.**
    
2. En la página **Ubicación de** instalación, haga clic en **Aceptar.**
    
3. En la **página Contrato de licencia para** el usuario final, haga clic en **Aceptar** y, a continuación, haga clic **en Aceptar.** (Necesario para continuar).
    
4. En la página Asistente para la implementación de **Skype Empresarial Server,** haga clic en **Instalar o actualizar el sistema de Skype Empresarial Server.**
    
5. Junto al **paso 1: Instalar almacén de configuración local,** haga clic en **Ejecutar** y, a continuación, siga las instrucciones en pantalla.
    
6. En la página Configurar réplica local del almacén de administración **central,** acepte el valor predeterminado **Recuperar** directamente desde el Almacén de administración central y, a continuación, haga clic en **Siguiente**.
    
7. En la **página Ejecutar comandos,** cuando el estado de la tarea se muestra como **Completado**, haga clic **en Finalizar**.
    
8. Next to **Step 2: Setup or Remove Skype for Business Server Components**, click **Run**, and then click **Next**.
    
9. En la **página Ejecutar comandos,** cuando el estado de la tarea se muestra como **Completado**, haga clic **en Finalizar**.
    
10. Junto al **paso 3: Solicitar, instalar o asignar certificados,** haga clic en **Ejecutar**. Sigue las instrucciones que aparecen en pantalla y acepta la configuración predeterminada. El servidor de mediación requiere un certificado, por lo que ejecutará el paso **3** dos veces: una vez para emitir el certificado necesario y una vez más para asignarlo.
    
11. Cuando el certificado se haya emitido y asignado correctamente, junto al paso **4:** Iniciar servicios, haga clic en Ejecutar y, a continuación, siga las instrucciones en pantalla.
    
12. Cuando **el paso 4 se** haya completado correctamente, reinicie el servidor e inicie sesión en el servidor como miembro del grupo DomainAdmins.
    
13. En el equipo donde ejecuta el Panel de control  de Skype Empresarial Server, compruebe en la página Topología del Panel de control de Skype Empresarial Server que el estado del servicio del servidor de mediación se muestra como una marca de verificación verde. Si en su lugar aparece una X roja, seleccione el servidor de mediación. En el menú **Acción,** haga clic **en Iniciar todos los servicios.** 
    
Si agregó más de un equipo al grupo de servidores de mediación, realice los pasos de este procedimiento en todos los demás equipos del grupo de servidores de mediación. Si no necesita instalar archivos para el servidor de mediación para otros equipos, siga los procedimientos descritos en [Configurar troncos](configure-trunks.md) en Skype Empresarial Server para configurar las opciones de conexión troncal entre este grupo de servidores de mediación (o todos los servidores de mediación de un sitio) y su sistema del mismo nivel.

