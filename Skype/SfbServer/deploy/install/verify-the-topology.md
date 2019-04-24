---
title: Comprobar la topología de Skype para Business Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 7/14/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a4f4bad1-fc59-47ce-a3ea-b1b893769db6
description: 'Resumen: Obtenga información sobre cómo comprobar la Skype para la topología de servidor empresarial y los servidores de Active Directory funcionan según lo previsto. Descargue una versión de prueba gratuita de Skype para Business Server desde el Evaluation de Microsoft center en: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server.'
ms.openlocfilehash: 03dfb45c03aa104cc5a9b265a37c347380590877
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32210798"
---
# <a name="verify-the-topology-in-skype-for-business-server"></a>Comprobar la topología de Skype para Business Server
 
**Resumen:** Obtenga información sobre cómo comprobar la Skype para la topología de servidor empresarial y los servidores de Active Directory funcionan según lo previsto. Descargue una versión de prueba gratuita de Skype para Business Server desde el [Centro de evaluación de Microsoft](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).
  
Una vez que tenga la topología publicada y el Skype para los componentes del sistema de Business Server instalado en cada uno de los servidores de la topología, está listo para comprobar que la topología funciona según lo previsto. Esto incluye la comprobación de que la configuración se propaga a todos los servidores de Active Directory para que todo el dominio sepa que Skype para la empresa está disponible en el dominio. Se pueden realizar los pasos del 1 al 5 en cualquier orden. Sin embargo, debe realizar los pasos 6, 7 y 8 en orden y después de los pasos del 1 al 5, tal como se indica en el diagrama. Comprobar la topología es el paso 8 de 8.
  
![Diagrama de información general.](../../media/c8698b53-1282-4978-a9a6-ca3f7a778f60.png)
  
## <a name="test-the-front-end-pool-deployment"></a>Probar la implementación del grupo de servidores front-end

Es el paso final probar el grupo de servidores Front-End y confirme que Skype para los clientes empresariales puede comunicarse entre sí. 
  
### <a name="add-users-and-verify-client-connectivity"></a>Agregar usuarios y comprobar la conectividad del cliente

1. Use usuarios y equipos de Active Directory para agregar el objeto de usuario de Active Directory de la función de administrador para la Skype para la implementación de Business Server (en el que está instalado Skype para el Panel de Control de servidor empresarial) al grupo **CSAdministrator** .
    
    > [!IMPORTANT]
    > Si no agrega los usuarios y grupos al grupo CsAdministors, recibirá un error cuando se abre Skype para el Panel de Control de servidor empresarial que lee, "no autorizado: acceso denegado debido a un error de autorización de acceso basado en roles (RBAC) de control ." 
  
2. Si actualmente el objeto de usuario ha iniciado sesión, cierre sesión y, luego, vuelva a iniciarla para registrar la nueva asignación de grupo.
    
    > [!NOTE]
    > La cuenta de usuario no puede ser el administrador local de cualquier servidor que ejecute Skype para Business Server. 
  
3. Use la cuenta administrativa para iniciar sesión en el equipo donde está instalado Skype para el Panel de Control de servidor empresarial.
    
4. Inicie Skype para el Panel de Control de servidor empresarial y, a continuación, proporcione las credenciales, si se le solicita. Skype para el Panel de Control de servidor empresarial muestra información sobre la implementación.
    
5. En la barra de navegación izquierda, haga clic en **topología**y, a continuación, confirme que el estado del servicio muestra un equipo con una flecha verde y que es una marca de verificación verde para el estado de la replicación junto a cada Skype para el rol de servidor de negocio que se ha implementado y poner en línea. 
    
6. En la barra de navegación izquierda, haga clic en **Usuarios** y, luego, haga clic en **Habilitar usuarios**. 
    
7. En la página **Nuevo Skype para usuarios del servidor de empresa** , haga clic en **Agregar**.
    
8. Para definir parámetros de búsqueda de los objetos que quiera encontrar, en la página **Seleccionar de Active Directory**, seleccione **Buscar** y, si lo desea, haga clic en **Agregar filtro**. También puede seleccionar **Búsqueda LDAP** y especificar una expresión de LDAP para filtrar o limitar los objetos que se devolverán. Una vez establecidas las opciones de búsqueda, haga clic en **Buscar**.
    
9. En el panel de resultados de la búsqueda, seleccione los usuarios que desea agregar y, luego, haga clic en **Aceptar**.
    
10. En la página **Nuevo Skype para usuarios del servidor de empresa** , los usuarios seleccionados se encuentran en la visualización de **los usuarios** . In the **Assign users to a pool** list, select the server where the users should reside.
    
    Aquí presentamos una lista de opciones que puede usar para configurar los objetos.
    
    - **Generar el URI de SIP del usuario**
    
    - **Telefonía**
    
    - **URI de línea**
    
    - **Directiva de conferencia**
    
    - **Directiva de versión de cliente**
    
    - **Directiva de PIN**
    
    - **Directiva de acceso externo**
    
    - **Directiva de archivado**
    
    - **Directiva de ubicación**
    
    - **Directiva de cliente**
    
    Para probar la funcionalidad básica, seleccione la opción que prefiera para la configuración de **URI de SIP del usuario de generar** (las demás opciones en las configuraciones de uso predeterminado) y, a continuación, haga clic en **Habilitar**, tal como se muestra en la ilustración.
    
     ![Habilita a los usuarios del Panel de control.](../../media/7ee8717d-9a1f-4864-8f45-71071c88878f.png)
  
11. Se muestra una página de resumen con una marca de verificación en la columna **Habilitado** para indicar que los usuarios están configurados. En la columna **Dirección SIP** figura la dirección que se necesita para configurar el inicio de sesión del usuario.
    
     ![Usuarios añadidos al Panel de control del servidor de Skype Empresarial.](../../media/8960548a-8d6d-44c5-bc01-6f9fb11b7588.png)
  
12. Es preciso que un usuario inicie sesión en un equipo integrado en el dominio y que otro usuario lo haga en otro equipo del dominio.
    
13. Instalar Skype para clientes empresariales en cada uno de los dos equipos cliente y, a continuación, compruebe que los dos usuarios pueden iniciar sesión en Skype para Business Server y pueden enviar mensajes instantáneos a los otros.
    

