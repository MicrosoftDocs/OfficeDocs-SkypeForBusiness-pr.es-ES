---
title: Instalar los archivos para el servidor de mediación en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 'Resumen: Aprenda a instalar los archivos para el servidor de mediación en Skype empresarial Server.'
ms.openlocfilehash: 4dc4c9971b74bf27d0f516ed70484646b666a845
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41767123"
---
# <a name="install-the-files-for-mediation-server-in-skype-for-business-server"></a>Instalar los archivos para el servidor de mediación en Skype empresarial Server
 
**Resumen:** Obtenga información sobre cómo instalar los archivos para mediar Server en Skype empresarial Server.
  
Para completar correctamente este procedimiento, debe haber iniciado sesión en el servidor por lo menos como administrador local y usuario de dominio que pertenezca, como mínimo, al grupo RTCUniversalReadOnlyAdmins.
  
Siga los pasos que se indican en este tema para ejecutar el Asistente para la implementación de Skype empresarial Server para instalar los archivos de Media Server en un equipo que haya agregado a un grupo de servidores de mediación después de haber usado el generador de topología para definir y publicar el grupo. Al instalar el servidor de mediación de archivos, también puede instalar y asignar el certificado requerido por cada equipo de un grupo de servidores de mediación. 
  
> [!NOTE]
> En este tema se supone que ya ha definido y publicado un grupo de servidores de mediación independiente en su topología, tal como se describe en [implementar un servidor de mediación en el generador de topologías de Skype empresarial Server](deploy-a-mediation-server.md). 
  
### <a name="to-install-the-files-for-a-stand-alone-mediation-server-pool"></a>Para instalar los archivos de un grupo de servidores de mediación independiente

1. Desde el medio de instalación, haga clic con el botón secundario en _ \<\> medios de instalación_ **\Setup\amd64\Setup.exe**y, después, haga clic en **Ejecutar como administrador**.
    
2. En la página **Ubicación de la instalación**, haga clic en **Aceptar**.
    
3. En la página **Contrato de licencia para el usuario final**, seleccione **Aceptar** y, a continuación, haga clic en **Aceptar**. (Es necesario para poder continuar).
    
4. En la página Asistente para la **implementación de Skype empresarial Server** , haga clic en **instalar o actualizar el sistema de Skype empresarial Server**.
    
5. Junto a **Paso 1: Instalar almacén de configuración local**, haga clic en **Ejecutar** y siga las instrucciones que aparecen en pantalla.
    
6. En la página **Configurar réplica local del almacén de administración central**, acepte la opción predeterminada **Recuperar directamente de almacén de administración central**; a continuación, haga clic en **Siguiente**.
    
7. En la página **Ejecutando comandos**, cuando el estado sea **Completado**, haga clic en **Finalizar**.
    
8. Junto al **paso 2: configurar o quitar componentes de Skype empresarial Server**, haga clic en **Ejecutar**y, a continuación, haga clic en **siguiente**.
    
9. En la página **Ejecutando comandos**, cuando el estado sea **Completado**, haga clic en **Finalizar**.
    
10. Junto a **Paso 3: Solicitar, instalar o asignar certificados**, haga clic en **Ejecutar**. Siga las instrucciones que aparecen en la pantalla y acepte la configuración predeterminada. El servidor de mediación requiere un certificado, por eso el **Paso 3** se debe ejecutar dos veces: una para emitir el certificado requerido y una más para asignarlo.
    
11. Una vez se ha emitido y asignado correctamente el certificado, junto a **Paso 4: Iniciar servicios**, haga clic en **Ejecutar** y siga las instrucciones que aparecen en pantalla.
    
12. Tras completar correctamente el **Paso 4**, reinicie el servidor e inicie sesión en él como miembro del grupo DomainAdmins.
    
13. En el equipo en el que esté ejecutando el panel de control de Skype empresarial Server, compruebe en la página **topología** del panel de control de Skype empresarial Server que el estado del servicio del servidor de mediación se muestra como una marca de verificación verde. Si en lugar de ello aparece una X de color rojo, seleccione el servidor de mediación. En el menú **Acción**, haga clic en **Iniciar todos los servicios**. 
    
Si ha agregado más de un equipo al grupo de servidores de mediación, realice los pasos de este procedimiento en todos los demás equipos del grupo de servidores de mediación. Si no necesita instalar archivos para el servidor de mediación para otros equipos, siga los procedimientos que se describen en [configurar troncos en Skype empresarial Server](configure-trunks.md) para establecer la configuración de la conexión troncal entre este grupo de servidores de mediación (o todos los servidores de mediación de un sitio) y su par.

