---
title: Implementar un grupo de servidores piloto
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Uno de los primeros pasos necesarios para la migración a Skype empresarial Server 2019 es implementar un grupo piloto. El grupo piloto es donde se prueba la coexistencia de Skype empresarial Server 2019 con la implementación heredada. La coexistencia es un estado temporal que dura hasta que haya movido todos los usuarios y grupos a Skype empresarial Server 2019.
ms.openlocfilehash: 46d8b6fd6cefa2894f67a1c24732ace01ca65785
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752862"
---
# <a name="deploy-skype-for-business-server-2019-pilot-pool"></a>Implementar el grupo piloto de Skype empresarial Server 2019

Uno de los primeros pasos necesarios para la migración a Skype empresarial Server 2019 es implementar un grupo piloto. El grupo piloto es donde se prueba la coexistencia de Skype empresarial Server 2019 con la implementación heredada. La coexistencia es un estado temporal que dura hasta que haya movido todos los usuarios y grupos a Skype empresarial Server 2019. 
  
Cuando se implementa un grupo piloto, se utiliza el Asistente para definir nuevo grupo de servidores front-end. Debe implementar las mismas características y cargas de trabajo en su grupo piloto de Skype empresarial Server 2019 que tiene en el grupo heredado. Si ha implementado el servidor de archivado, el servidor de supervisión o System Center Operations Manager para archivar o supervisar el entorno heredado, y desea continuar el archivado o la supervisión durante la migración, también debe implementar estas características en el entorno piloto. La versión que ha implementado para archivar o supervisar el entorno heredado no capturará datos en su entorno de Skype empresarial Server 2019. 
  
> [!NOTE]
> El siguiente procedimiento trata las funciones y configuración que se deben tener en cuenta como parte del proceso de implementación del grupo piloto. Esta sección solo subraya puntos clave que se deberían tener en cuenta como parte de la implementación de grupo piloto. <!-- For detailed steps, refer to the 
 [Deploying Skype for Business Server 2019](../deployment/deploying-lync-server-2013/deploying-lync-server-2013.md) deployment guide.  -->
  
### <a name="to-deploy-a-skype-for-business-server-2019-pilot-pool"></a>Para implementar un grupo piloto de Skype empresarial Server 2019

1. Inicie sesión en el equipo en el que Topology Builder esté instalado como miembro del grupo Admins. del dominio y el grupo RTCUniversalServerAdmins.
    
2. Expanda el árbol hasta llegar **a**los  >  **grupos de servidores front-end**de Skype empresarial Server 2019 Enterprise Edition.
    
3. Haga clic con el botón secundario en **grupos de servidores front-end Enterprise Edition** y seleccione **nuevo grupo de servidores front-end**.
  
4. Especifique el nombre de dominio completo (FQDN) del grupo de servidores. Al definir el grupo piloto, puede optar por implementar un grupo de servidores front-end Enterprise Edition o un servidor Standard Edition. Skype empresarial Server 2019 no requiere que las características del grupo piloto coinciden con lo que se ha implementado en el grupo heredado.
    
    > [!CAUTION]
    > El FQDN de grupo o servidor que defina para el grupo piloto debe ser único. No puede coincidir con el nombre del grupo heredado actualmente implementado o con otros servidores implementados actualmente. 
  
5. En la página **Seleccionar características**, active las casillas de las características que desee en este grupo de servidores front-end. Por ejemplo, si va a implementar sólo las características de mensajería instantánea (mi) y presencia, active la casilla Conferencia para permitir la mensajería instantánea de varios participantes, pero no seleccione las casillas Conferencia de acceso telefónico local (RTC), telefonía IP empresarial o control de admisión de llamadas, ya que representan características de conferencia de voz, vídeo y colaboración. <!-- For additional information on selecting features, see 
 [Define and configure a Front End pool or Standard Edition server in Skype for Business Server 2019](../deployment/deploying-lync-server-2013/define-and-configure-a-front-end-pool-or-standard-edition-server.md) in the Deployment documentation.  -->
  
6. En la página **Seleccionar roles de servidor combinados** , le recomendamos que decida combinar el servidor de mediación en Skype empresarial Server 2019. Al combinar una topología heredada con Skype empresarial Server 2019, es necesario que primero combinar el servidor de mediación heredado. Después de combinar las topologías y configurar el servidor de mediación de Skype empresarial Server 2019, puede decidir si desea mantener el servidor de mediación combinado o cambiarlo a un servidor independiente cuando mueva el rol de servidor de mediación a Skype empresarial Server 2019 más adelante en el proceso de implementación. 
   
7. En la página **asociar roles de servidor con este grupo de servidores front-end** , durante la implementación del grupo piloto, *no* elija la opción **habilitar un grupo de servidores perimetrales para que lo use el componente de medios de este grupo de servidores front-end** . Esta característica se habilitará y se pondrá en línea en una fase posterior de la migración. No seleccione esta opción por el momento. 
  
8. En la página **Seleccionar un servidor de aplicaciones web para Office**, haga clic en **Nuevo** y especifique el FQDN del servidor de aplicaciones.
  
9. En la página **definir el almacén de SQL Server de archivado** , al definir el almacén de SQL Server para el archivado y la supervisión de Skype empresarial Server, seleccione la instancia de SQL Server creada anteriormente para Skype empresarial Server 2019. 
  
10. Para publicar la topología, haga clic con el botón secundario en el nodo **Skype empresarial Server** y, a continuación, haga clic en **publicar topología**.
  
11. Una vez completado el proceso de publicación, haga clic en **Finalizar**.

12. Antes de pasar a la siguiente sección denominada "verificar coexistencia de grupo piloto con grupo heredado", debe instalar el nuevo grupo piloto front-end de Skype empresarial Server que acabamos de definir en la topología publicada, siga los procedimientos descritos aquí [instalar Skype empresarial Server en los servidores de la topología](https://docs.microsoft.com/skypeforbusiness/deploy/install/install-skype-for-business-server) .

13. Una vez completado el paso anterior, vaya a la siguiente sección para comprobar la coexistencia del grupo piloto con el grupo de servidores heredados.
    
<!-- To install a local copy of the configuration store and start the required services, see 
[Setting up Front End Servers and Front End pools for Skype for Business Server 2019](../deployment/deploying-lync-server-2013/setting-up-front-end-servers-and-front-end-pools.md) in the Deployment documentation.  -->
  

