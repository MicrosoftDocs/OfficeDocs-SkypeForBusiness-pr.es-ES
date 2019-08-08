---
title: Implementar un grupo de servidores piloto
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Uno de los primeros pasos necesarios para la migración a Skype empresarial Server 2019 es implementar un grupo piloto. El grupo piloto es donde se prueba la coexistencia de Skype empresarial Server 2019 con la implementación heredada. La coexistencia es un estado temporal que dura hasta que ha movido todos los usuarios y los grupos a Skype empresarial Server 2019.
ms.openlocfilehash: dc0e5b984aaa9ed931f3937b253fbe40aef9b051
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2019
ms.locfileid: "36238384"
---
# <a name="deploy-skype-for-business-server-2019-pilot-pool"></a>Implementar el grupo piloto de Skype empresarial Server 2019

Uno de los primeros pasos necesarios para la migración a Skype empresarial Server 2019 es implementar un grupo piloto. El grupo piloto es donde se prueba la coexistencia de Skype empresarial Server 2019 con la implementación heredada. La coexistencia es un estado temporal que dura hasta que ha movido todos los usuarios y los grupos a Skype empresarial Server 2019. 
  
Al implementar un grupo piloto, se usa el Asistente para definir el nuevo grupo frontal. Debe implementar las mismas características y cargas de trabajo en su grupo piloto de Skype empresarial Server 2019 que tiene en su grupo heredado. Si ha implementado el servidor de archivado, Monitoring Server o System Center Operations Manager para archivar o supervisar el entorno heredado, y desea continuar el archivado o la supervisión durante la migración, también debe implementar estas características en su entorno piloto. La versión que ha implementado para archivar o controlar el entorno heredado no capturará datos en su entorno de Skype empresarial Server 2019. 
  
> [!NOTE]
> El procedimiento siguiente describe las características y la configuración que debe tener en cuenta como parte del proceso general de implementación del grupo piloto. Esta sección solo resalta los puntos clave que debe considerar como parte de la implementación de un grupo piloto. <!-- For detailed steps, refer to the 
 [Deploying Skype for Business Server 2019](../deployment/deploying-lync-server-2013/deploying-lync-server-2013.md) deployment guide.  -->
  
### <a name="to-deploy-a-skype-for-business-server-2019-pilot-pool"></a>Para implementar un grupo de pruebas piloto de Skype empresarial Server 2019

1. Inicie sesión en el equipo donde se encuentre instalado el Generador de topologías como miembro del grupo Administradores del dominio y el grupo RTCUniversalServerAdmins.
    
2. Expanda el árbol hasta llegar **a Skype empresarial Server 2019** > **Enterprise Edition pools front end**.
    
3. Haga clic con el botón secundario en las **agrupaciones front-end Enterprise Edition** y seleccione **nuevo grupo de servidores front-end**.
  
4. Escriba el nombre de dominio completo (FQDN) del grupo. Cuando define el grupo piloto, puede optar por implementar un grupo de servidores front-end Enterprise Edition o un servidor Standard Edition. Skype empresarial Server 2019 no requiere que las características de su grupo piloto coincidan con lo que se ha implementado en su grupo heredado.
    
    > [!CAUTION]
    > El FQDN de grupo o servidor que defina para el grupo piloto debe ser único. No puede coincidir con el nombre del grupo heredado actualmente implementado o de cualquier otro servidor implementado actualmente. 
  
5. En la página **seleccionar características** , seleccione las casillas de las características que desee en este grupo de servidores front-end. Por ejemplo, si va a implementar solo la mensajería instantánea (mi) y las características de presencia, debe activar la casilla conferencias para permitir la mensajería instantánea entre usuarios, pero no puede seleccionar la comprobación de conferencia de acceso telefónico local (RTC), telefonía IP empresarial o control de admisión de llamadas , porque representan las características de conferencia de voz, vídeo y colaboración. <!-- For additional information on selecting features, see 
 [Define and configure a Front End pool or Standard Edition server in Skype for Business Server 2019](../deployment/deploying-lync-server-2013/define-and-configure-a-front-end-pool-or-standard-edition-server.md) in the Deployment documentation.  -->
  
6. En la página **Seleccionar roles de servidor** de la presentación, le recomendamos que elija Collocate el servidor de mediación en Skype empresarial Server 2019. Al combinar una topología heredada con Skype empresarial Server 2019, le pedimos que primero Collocate el servidor de mediación heredado. Después de combinar las topologías y configurar el servidor de mediación de Skype empresarial Server 2019, puede decidir si desea mantener el servidor de mediación o cambiarlo a un servidor independiente cuando mueva la función de servidor de mediación a Skype empresarial Server 2019 más adelante en el proceso de implementación. 
   
7. En la página **asociar roles de servidor con este grupo de servidores front-end** , durante la implementación de un grupo piloto, *no* elija la opción **habilitar un grupo perimetral para que lo use el componente multimedia de este grupo de servidores front-end** . Esta es una característica que habilitará y se conectará en línea en una fase posterior de la migración. Mantener esta configuración desactivada por ahora. 
  
8. En la página **seleccionar un servidor de Office Web Apps** , haga clic en **nuevo**y especifique el FQDN del servidor de aplicaciones.
  
9. En la página **definir el archivado del almacén SQL Server** , al definir el almacén de SQL Server para el archivado y la supervisión de Skype empresarial Server, seleccione la instancia de SQL Server creada anteriormente para Skype empresarial Server 2019. 
  
10. Para publicar su topología, haga clic con el botón secundario en el nodo **de Skype empresarial Server** y, a continuación, haga clic en **publicar topología**.
  
11. Cuando el proceso de publicación haya finalizado, haga clic en **Finalizar**.

12. Antes de pasar a la sección siguiente denominada "comprobar coexistencia de grupo piloto con grupo de servidores heredados", debe instalar el nuevo grupo piloto front end de Skype empresarial que acabamos de definir en la topología publicada, siga los procedimientos descritos aquí [instalar Skype para Servidor empresarial en servidores de la topología](https://docs.microsoft.com/skypeforbusiness/deploy/install/install-skype-for-business-server)

13. Una vez completado el paso anterior, vaya a la siguiente sección para comprobar la coexistencia del grupo piloto con el grupo heredado.
    
<!-- To install a local copy of the configuration store and start the required services, see 
[Setting up Front End Servers and Front End pools for Skype for Business Server 2019](../deployment/deploying-lync-server-2013/setting-up-front-end-servers-and-front-end-pools.md) in the Deployment documentation.  -->
  

