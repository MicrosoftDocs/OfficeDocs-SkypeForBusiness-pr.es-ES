---
title: Instalar los archivos del servidor de mediación en Skype Empresarial Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: f0f7dd15-58e1-40fd-aa7e-6db50ceafacd
description: 'Resumen: Conozca cómo instalar los archivos para el servidor de mediación en Skype para Business Server 2015.'
ms.openlocfilehash: 8b7b68142c180ee1b06963afbb1b7a9ca6d4319c
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="install-the-files-for-mediation-server-in-skype-for-business-server-2015"></a>Instalar los archivos del servidor de mediación en Skype Empresarial Server 2015
 
**Resumen:** Aprenda a instalar los archivos de servidor de mediación en Skype para Business Server 2015.
  
Para completar correctamente este procedimiento, debe haber iniciado sesión en el servidor por lo menos como administrador local y usuario de dominio que pertenezca, como mínimo, al grupo RTCUniversalReadOnlyAdmins.
  
Utilice los pasos en este tema para ejecutar Skype para el Asistente para implementación de Business Server instalar los archivos de servidor de mediación en un equipo que haya agregado a un grupo de servidores de mediación después de haber utilizado el generador de topología para definir y publicar el grupo. Al instalar los archivos del servidor de mediación, también instalar y asignar el certificado requerido por cada equipo en un grupo de servidores de mediación. 
  
> [!NOTE]
> En este tema se supone que ya ha definido y publicado un conjunto de servidor de mediación de independiente de la topología, como se describe en [implementar un servidor de mediación en el generador de topología en Skype para Business Server 2015](deploy-a-mediation-server.md). 
  
### <a name="to-install-the-files-for-a-stand-alone-mediation-server-pool"></a>Para instalar los archivos de un grupo de servidores de mediación independiente

1. Desde el medio de instalación, haga clic en _ \<medios de instalación de\> _ **\Setup\amd64\Setup.exe**y, a continuación, haga clic en **Ejecutar como administrador**.
    
2. En la página **Ubicación de la instalación**, haga clic en **Aceptar**.
    
3. En la página **Contrato de licencia para el usuario final**, seleccione **Aceptar** y, a continuación, haga clic en **Aceptar**. (Es necesario para poder continuar).
    
4. En la página de **Skype para el Asistente para implementación de Business Server** , haga clic en **instalación o actualización de Skype para el sistema de servidor empresarial**.
    
5. Junto a **Paso 1: Instalar almacén de configuración local**, haga clic en **Ejecutar** y siga las instrucciones que aparecen en pantalla.
    
6. En la página **Configurar réplica local del almacén de administración central**, acepte la opción predeterminada **Recuperar directamente de almacén de administración central**; a continuación, haga clic en **Siguiente**.
    
7. En la página **Ejecutando comandos**, cuando el estado sea **Completado**, haga clic en **Finalizar**.
    
8. Junto a **paso 2: instalación o quitar Skype para los componentes de servidor empresariales**, haga clic en **Ejecutar**y, a continuación, haga clic en **siguiente**.
    
9. En la página **Ejecutando comandos**, cuando el estado sea **Completado**, haga clic en **Finalizar**.
    
10. Junto a **Paso 3: Solicitar, instalar o asignar certificados**, haga clic en **Ejecutar**. Siga las instrucciones que aparecen en la pantalla y acepte la configuración predeterminada. El servidor de mediación requiere un certificado, por eso el **Paso 3** se debe ejecutar dos veces: una para emitir el certificado requerido y una más para asignarlo.
    
11. Una vez se ha emitido y asignado correctamente el certificado, junto a **Paso 4: Iniciar servicios**, haga clic en **Ejecutar** y siga las instrucciones que aparecen en pantalla.
    
12. Tras completar correctamente el **Paso 4**, reinicie el servidor e inicie sesión en él como miembro del grupo DomainAdmins.
    
13. En el equipo donde se ejecuta Skype para Business Server Control Panel, compruebe en la página de la **topología** de Skype para el Panel de Control de servidor empresariales que el estado del servicio del servidor de mediación se muestra como una marca de verificación verde. Si en lugar de ello aparece una X de color rojo, seleccione el servidor de mediación. En el menú **Acción**, haga clic en **Iniciar todos los servicios**. 
    
Si agrega más de un equipo al grupo de servidores de mediación, realice los pasos de este procedimiento en todos los demás equipos del grupo de servidor de mediación. Si no necesita instalar archivos para servidor de mediación para otros equipos, a continuación, siga los procedimientos de [configurar los troncos en Skype para Business Server 2015](configure-trunks.md) para configurar la conexión de troncal entre este grupo de servidores de mediación (o todos Servidores de mediación en un sitio) y su interlocutor.

