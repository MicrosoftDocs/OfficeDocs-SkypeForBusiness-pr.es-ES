---
title: Instalar los archivos para el servidor de mediación en Skype para Business Server
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f0f7dd15-58e1-40fd-aa7e-6db50ceafacd
description: 'Resumen: Obtenga información sobre cómo instalar los archivos para el servidor de mediación en Skype para Business Server.'
ms.openlocfilehash: b3314e5443a7aa881fa849fd3e3b5b639f72664e
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2018
ms.locfileid: "21002484"
---
# <a name="install-the-files-for-mediation-server-in-skype-for-business-server"></a>Instalar los archivos para el servidor de mediación en Skype para Business Server
 
**Resumen:** Obtenga información sobre cómo instalar los archivos para el servidor de mediación en Skype para Business Server.
  
Para completar correctamente este procedimiento, debe haber iniciado sesión en el servidor por lo menos como administrador local y usuario de dominio que pertenezca, como mínimo, al grupo RTCUniversalReadOnlyAdmins.
  
Use los pasos de este tema para ejecutar Skype para el Asistente para la implementación empresarial Server instalar los archivos para el servidor de mediación en un equipo que ha agregado a un grupo de servidores de mediación después de utilizar el generador de topología para definir y publicar el grupo de servidores. Al instalar los archivos de servidor de mediación, también instalar y asignar el certificado requerido por cada equipo en un grupo de servidores de mediación. 
  
> [!NOTE]
> En este tema se da por supuesto que ya ha definido y ha publicado un grupo de servidores de mediación independiente en la topología, tal y como se describe en [implementar un servidor de mediación en el generador de Skype para Business Server](deploy-a-mediation-server.md). 
  
### <a name="to-install-the-files-for-a-stand-alone-mediation-server-pool"></a>Para instalar los archivos de un grupo de servidores de mediación independiente

1. Desde los medios de instalación, haga clic con el botón _ \<medios de instalación de\> _ **\Setup\amd64\Setup.exe**y, a continuación, haga clic en **Ejecutar como administrador**.
    
2. En la página **Ubicación de la instalación**, haga clic en **Aceptar**.
    
3. En la página **Contrato de licencia para el usuario final**, seleccione **Aceptar** y, a continuación, haga clic en **Aceptar**. (Es necesario para poder continuar).
    
4. En la página de **Skype para el Asistente para la implementación de Business Server** , haga clic en **instalar o actualización de Skype para Business Server System**.
    
5. Junto a **Paso 1: Instalar almacén de configuración local**, haga clic en **Ejecutar** y siga las instrucciones que aparecen en pantalla.
    
6. En la página **Configurar réplica local del almacén de administración central**, acepte la opción predeterminada **Recuperar directamente de almacén de administración central**; a continuación, haga clic en **Siguiente**.
    
7. En la página **Ejecutando comandos**, cuando el estado sea **Completado**, haga clic en **Finalizar**.
    
8. Junto a **paso 2: el programa de instalación o quitar Skype para los componentes de servidor empresariales**, haga clic en **Ejecutar**y, a continuación, haga clic en **siguiente**.
    
9. En la página **Ejecutando comandos**, cuando el estado sea **Completado**, haga clic en **Finalizar**.
    
10. Junto a **Paso 3: Solicitar, instalar o asignar certificados**, haga clic en **Ejecutar**. Siga las instrucciones que aparecen en la pantalla y acepte la configuración predeterminada. El servidor de mediación requiere un certificado, por eso el **Paso 3** se debe ejecutar dos veces: una para emitir el certificado requerido y una más para asignarlo.
    
11. Una vez se ha emitido y asignado correctamente el certificado, junto a **Paso 4: Iniciar servicios**, haga clic en **Ejecutar** y siga las instrucciones que aparecen en pantalla.
    
12. Tras completar correctamente el **Paso 4**, reinicie el servidor e inicie sesión en él como miembro del grupo DomainAdmins.
    
13. En el equipo donde se ejecuta Skype para el Panel de Control de servidor empresarial, compruebe en la página de **topología** de Skype para el Panel de Control de servidor empresarial que el estado del servicio del servidor de mediación se muestra como una marca de verificación verde. Si en lugar de ello aparece una X de color rojo, seleccione el servidor de mediación. En el menú **Acción**, haga clic en **Iniciar todos los servicios**. 
    
Si agrega más de un equipo al grupo de servidores de mediación, realice los pasos de este procedimiento en todos los demás equipos en el grupo de servidores de mediación. Si no es necesario instalar archivos para servidor de mediación para los demás equipos, a continuación, siga los procedimientos descritos en [Configure troncos en Skype para Business Server](configure-trunks.md) para configurar las opciones para la conexión del tronco entre este grupo de servidores de servidor de mediación (o mediación todos los Los servidores en un sitio) y su mismo nivel.

