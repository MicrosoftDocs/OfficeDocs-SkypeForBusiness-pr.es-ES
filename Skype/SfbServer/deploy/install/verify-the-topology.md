---
title: Compruebe la topología en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 7/14/2018
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
ms.assetid: a4f4bad1-fc59-47ce-a3ea-b1b893769db6
description: 'Summary: Learn how to verify the Skype Empresarial Server topology and Active Directory servers are working as expected. Descargue una versión de prueba Skype Empresarial Server desde el Centro de evaluación de Microsoft en: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server .'
ms.openlocfilehash: 743741fd18766116ed923a2af632f33c88343ef5957a84165edc7702b3b6593f
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54294777"
---
# <a name="verify-the-topology-in-skype-for-business-server"></a>Compruebe la topología en Skype Empresarial Server
 
**Resumen:** Obtenga información sobre cómo comprobar que la topología Skype Empresarial Server y los servidores de Active Directory funcionan según lo esperado. Descargue una prueba gratuita de Skype Empresarial Server desde el [Centro de evaluación de Microsoft](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).
  
Después de publicar la topología y de instalar los componentes del sistema Skype Empresarial Server en cada uno de los servidores de la topología, estará listo para comprobar que la topología funciona según lo esperado. Esto incluye comprobar que la configuración se ha propagado a todos los servidores de Active Directory para que todo el dominio sepa Skype Empresarial está disponible en el dominio. Puede realizar los pasos del 1 al 5 en cualquier orden. Sin embargo, debe realizar los pasos 6, 7 y 8 en orden y después de los pasos del 1 al 5, tal como se describe en el diagrama. Comprobar la topología es el paso 8 de 8.
  
![Diagrama de información general.](../../media/c8698b53-1282-4978-a9a6-ca3f7a778f60.png)
  
## <a name="test-the-front-end-pool-deployment"></a>Probar la implementación del grupo de servidores front-end

El último paso es probar el grupo de servidores front-end y confirmar que Skype Empresarial clientes pueden comunicarse entre sí. 
  
### <a name="add-users-and-verify-client-connectivity"></a>Agregar usuarios y comprobar la conectividad del cliente

1. Use Equipos y usuarios de Active Directory para agregar el objeto de usuario de Active Directory del rol de administrador para la implementación de Skype Empresarial Server (en la que está instalado el Panel de control Skype Empresarial Server) al grupo **CSAdministrator.**
    
    > [!IMPORTANT]
    > Si no agrega los usuarios y grupos adecuados al grupo CsAdministors, recibirá un error al abrir un Panel de control de Skype Empresarial Server que dice" Unauthorized: Access is denied due to a role-based access control (RBAC) authorization failure". 
  
2. Si el objeto de usuario ha iniciado sesión, cierre sesión y, a continuación, vuelva a iniciar sesión para registrar la nueva asignación de grupo.
    
    > [!NOTE]
    > La cuenta de usuario no puede ser el administrador local de ningún servidor que ejecute Skype Empresarial Server. 
  
3. Use la cuenta administrativa para iniciar sesión en el equipo donde Skype Empresarial Server panel de control está instalado.
    
4. Inicie Skype Empresarial Server Panel de control y, a continuación, proporcione credenciales, si se le solicita. Skype Empresarial Server El Panel de control muestra información de implementación.
    
5. En la barra de navegación izquierda, haga clic en Topología y, a continuación, confirme que el estado del servicio muestra un equipo con una flecha verde y que una marca de verificación verde para el estado de replicación está junto Skype Empresarial Server cada rol que se ha implementado y puesto en línea. 
    
6. En la barra de navegación izquierda, haga clic en **Usuarios** y haga clic en **Habilitar usuarios**. 
    
7. En la **página Nuevo Skype Empresarial Server usuario,** haga clic en **Agregar**.
    
8. Para definir parámetros de búsqueda de los objetos que quiera encontrar, en la página **Seleccionar de Active Directory** seleccione **Buscar** y, si lo desea, haga clic en **Agregar filtro**. También puede seleccionar **Búsqueda LDAP** y especificar una expresión de LDAP para filtrar o limitar los objetos que se devolverán. Una vez que haya decidido las opciones de búsqueda, haga clic en **Buscar**.
    
9. En el panel Resultados de búsqueda, seleccione los usuarios que desea agregar y, a continuación, haga clic en **Aceptar**.
    
10. En la **página Nuevo Skype Empresarial Server usuario,** los usuarios seleccionados se encuentran en la **pantalla** Usuarios. En la **lista Asignar usuarios a un grupo** de servidores, seleccione el servidor donde deben residir los usuarios.
    
    A continuación se muestra una lista de opciones que puede usar para configurar los objetos.
    
    - **Generar uri de SIP del usuario**
    
    - **Telefonía**
    
    - **URI de línea**
    
    - **Directiva de conferencia**
    
    - **Directiva de versión de clientes**
    
    - **Directiva de PIN**
    
    - **Directiva de acceso externo**
    
    - **Directiva de archivado**
    
    - **Directiva de ubicación**
    
    - **Directiva de cliente**
    
    Para probar la funcionalidad básica, seleccione la opción que prefiera para la opción Generar **URI de SIP** del usuario (las otras opciones de la configuración usan la configuración predeterminada) y, a continuación, haga clic en **Habilitar**, como se muestra en la figura.
    
     ![Habilitar usuarios en el Panel de control.](../../media/7ee8717d-9a1f-4864-8f45-71071c88878f.png)
  
11. Se muestra una página de resumen que muestra una marca de verificación en la **columna Habilitado** para indicar que los usuarios están configurados. En la columna **Dirección SIP** figura la dirección que se necesita para configurar el inicio de sesión del usuario.
    
     ![Los usuarios agregados a Skype Empresarial Server Panel de control.](../../media/8960548a-8d6d-44c5-bc01-6f9fb11b7588.png)
  
12. Inicie sesión un usuario en un equipo que esté unido al dominio y otro usuario en otro equipo del dominio.
    
13. Instale Skype Empresarial cliente en cada uno de los dos equipos cliente y, a continuación, compruebe que ambos usuarios puedan iniciar sesión en Skype Empresarial Server y puedan enviar mensajes instantáneos entre sí.
    

