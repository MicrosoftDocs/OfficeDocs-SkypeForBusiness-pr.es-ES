---
title: Comprobar la topología en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/14/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a4f4bad1-fc59-47ce-a3ea-b1b893769db6
description: 'Resumen: Aprenda a comprobar la topología de Skype empresarial Server y los servidores de Active Directory que funcionan de la forma esperada. Descargue una prueba gratuita de Skype empresarial Server en el centro de evaluación de Microsoft en https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server:.'
ms.openlocfilehash: 6c7d7a67cab2cbd383ee26eb64f478985bcc4b27
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2019
ms.locfileid: "36245239"
---
# <a name="verify-the-topology-in-skype-for-business-server"></a>Comprobar la topología en Skype empresarial Server
 
**Resumen:** Obtenga información sobre cómo comprobar si la topología de Skype empresarial Server y los servidores de Active Directory funcionan de la forma esperada. Descargue una prueba gratuita de Skype empresarial Server en el [centro de evaluación de Microsoft](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).
  
Una vez publicada la topología y los componentes del sistema de Skype empresarial Server instalados en cada uno de los servidores de la topología, estará listo para comprobar que la topología funciona de la forma esperada. Esto incluye comprobar que la configuración se propagó a todos los servidores de Active Directory para que todo el dominio sepa que Skype empresarial está disponible en el dominio. Puede realizar los pasos 1 a 5 en cualquier orden. Sin embargo, debe realizar los pasos 6, 7 y 8 en orden, y después de los pasos 1 a 5, según se indica en el diagrama. Comprobar la topología es el paso 8 de 8.
  
![Diagrama de información general.](../../media/c8698b53-1282-4978-a9a6-ca3f7a778f60.png)
  
## <a name="test-the-front-end-pool-deployment"></a>Probar la implementación del grupo de servidores front-end

El paso final es probar el grupo de servidores front-end y confirmar que los clientes de Skype empresarial pueden comunicarse entre sí. 
  
### <a name="add-users-and-verify-client-connectivity"></a>Agregar usuarios y comprobar la conectividad del cliente

1. Use equipos y usuarios de Active Directory para agregar el objeto de usuario de Active Directory del rol de administrador de la implementación de Skype empresarial Server (en la que está instalado el panel de control de Skype empresarial Server) al grupo **CSAdministrator** .
    
    > [!IMPORTANT]
    > Si no agrega los usuarios y grupos adecuados al grupo CsAdministors, recibirá un error cuando abra el panel de control de Skype empresarial Server que dice "no autorizado: acceso denegado debido a un error de autorización de control de acceso basado en roles (RBAC). ." 
  
2. Si actualmente el objeto de usuario ha iniciado sesión, cierre sesión y, luego, vuelva a iniciarla para registrar la nueva asignación de grupo.
    
    > [!NOTE]
    > La cuenta de usuario no puede ser el administrador local de ningún servidor que ejecute Skype empresarial Server. 
  
3. Use la cuenta administrativa para iniciar sesión en el equipo en el que está instalado el panel de control de Skype empresarial Server.
    
4. Inicie el panel de control de Skype empresarial Server y, si se le solicita, proporcione las credenciales. El panel de control de Skype empresarial Server muestra información de implementación.
    
5. En la barra de navegación izquierda, haga clic en **topología**y, a continuación, confirme que el estado del servicio muestra un equipo con una flecha verde y que una marca de verificación verde para el estado de replicación está junto a cada rol de servidor de Skype empresarial que se ha implementado y se ha puesto en conexión. 
    
6. En la barra de navegación izquierda, haga clic en **Usuarios** y, luego, haga clic en **Habilitar usuarios**. 
    
7. En la página **nuevo usuario de Skype empresarial Server** , haga clic en **Agregar**.
    
8. Para definir parámetros de búsqueda de los objetos que quiera encontrar, en la página **Seleccionar de Active Directory**, seleccione **Buscar** y, si lo desea, haga clic en **Agregar filtro**. También puede seleccionar **Búsqueda LDAP** y especificar una expresión de LDAP para filtrar o limitar los objetos que se devolverán. Una vez establecidas las opciones de búsqueda, haga clic en **Buscar**.
    
9. En el panel de resultados de la búsqueda, seleccione los usuarios que desea agregar y, luego, haga clic en **Aceptar**.
    
10. En la **nueva página de usuario de Skype empresarial Server** , los usuarios que seleccionó aparecerán en la pantalla **usuarios** . In the **Assign users to a pool** list, select the server where the users should reside.
    
    Aquí presentamos una lista de opciones que puede usar para configurar los objetos.
    
    - **Generar el URI del SIP del usuario**
    
    - **Telefonía**
    
    - **URI de línea**
    
    - **Directiva de conferencia**
    
    - **Directiva de versión de cliente**
    
    - **Directiva de PIN**
    
    - **Directiva de acceso externo**
    
    - **Directiva de archivado**
    
    - **Directiva de ubicación**
    
    - **Directiva de cliente**
    
    Para probar la funcionalidad básica, seleccione la opción que prefiera para la configuración de **URI de SIP del usuario** (el resto de opciones de configuración use la configuración predeterminada) y, a continuación, haga clic en **Habilitar**, como se muestra en la ilustración.
    
     ![Habilita a los usuarios del Panel de control.](../../media/7ee8717d-9a1f-4864-8f45-71071c88878f.png)
  
11. Se muestra una página de resumen con una marca de verificación en la columna **Habilitado** para indicar que los usuarios están configurados. En la columna **Dirección SIP** figura la dirección que se necesita para configurar el inicio de sesión del usuario.
    
     ![Usuarios añadidos al Panel de control del servidor de Skype Empresarial.](../../media/8960548a-8d6d-44c5-bc01-6f9fb11b7588.png)
  
12. Es preciso que un usuario inicie sesión en un equipo integrado en el dominio y que otro usuario lo haga en otro equipo del dominio.
    
13. Instale el cliente de Skype empresarial en cada uno de los dos equipos cliente y, a continuación, compruebe que ambos usuarios pueden iniciar sesión en Skype empresarial Server y que pueden enviarse mensajes instantáneos entre sí.
    

