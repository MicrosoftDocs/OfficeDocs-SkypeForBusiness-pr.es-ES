---
title: Comprobar la topología en Skype Empresarial Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 7/14/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: a4f4bad1-fc59-47ce-a3ea-b1b893769db6
description: 'Resumen: Conozca cómo comprobar el Skype para la topología de servidores empresariales y servidores Active Directory funcionan como se esperaba. Descargue una prueba gratuita de Skype para Business Server 2015 desde el centro de Evaluation de Microsoft en: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server.'
ms.openlocfilehash: 983ecf8b78a12898d18f04f7ec5c26c5271cf79a
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="verify-the-topology-in-skype-for-business-server-2015"></a>Comprobar la topología en Skype Empresarial Server 2015
 
**Resumen:** Obtenga información sobre cómo comprobar el Skype para la topología de servidores empresariales y servidores Active Directory funcionan como se esperaba. Descargue una prueba gratuita de Skype para Business Server 2015 desde el [Centro de evaluación de Microsoft](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).
  
Una vez que la topología publicada y el Skype para componentes del sistema de Business Server instalado en cada uno de los servidores de la topología, está listo para comprobar que la topología funciona como se esperaba. Esto incluye la comprobación de que la configuración ha propagado a todos los servidores de Active Directory para que sepa de todo el dominio que Skype para empresas está disponible en el dominio. Puede realizar los pasos 1 a 5 en cualquier orden. Sin embargo, debe realizar los pasos 6, 7 y 8 en orden y después los pasos del 1 al 5, tal como se indica en el diagrama. Verificar la topología es el paso 8 de 8.
  
![Diagrama de información general.](../../media/c8698b53-1282-4978-a9a6-ca3f7a778f60.png)
  
## <a name="test-the-front-end-pool-deployment"></a>Probar la implementación del grupo de servidores front-end

El paso final es probar el grupo de servidores Front-End y confirmar que Skype para clientes de empresa puede comunicarse entre sí. 
  
### <a name="add-users-and-verify-client-connectivity"></a>Agregar usuarios y comprobar la conectividad del cliente

1. Utilice usuarios y equipos de Active Directory para agregar el objeto de usuario de Active Directory de la función Administrador para el Skype para la implementación de Business Server (en el que está instalado Skype para el Panel de Control de servidor de negocios) al grupo **CSAdministrator** .
    
    > [!IMPORTANT]
    > Si no agrega los usuarios y grupos al grupo CsAdministors, recibirá un error cuando abre Skype para Panel de Control de servidor de negocios que lee, "no autorizado: acceso denegado debido a un error de autorización de acceso basado en roles (RBAC) de control ." 
  
2. Si actualmente el objeto de usuario ha iniciado sesión, cierre sesión y, luego, vuelva a iniciarla para registrar la nueva asignación de grupo.
    
    > [!NOTE]
    > La cuenta de usuario no puede ser el administrador local de cualquier servidor que ejecute Skype para Business Server. 
  
3. Utilice la cuenta administrativa para iniciar sesión en el equipo donde está instalado Skype para el Panel de Control de servidor empresarial.
    
4. Iniciar Skype para Panel de Control de servidor empresarial y, a continuación, proporcione credenciales, si se le pide. Skype para Business Server Control Panel muestra información sobre la implementación.
    
5. En la barra de navegación de la izquierda, haga clic en **topología**y, a continuación, confirme que el estado del servicio muestra un equipo con una flecha verde y que una marca de verificación verde para el estado de la replicación está al lado de cada Skype para el rol de servidor de negocios que se ha implementado y puesto en línea. 
    
6. En la barra de navegación izquierda, haga clic en **Usuarios** y, luego, haga clic en **Habilitar usuarios**. 
    
7. En la página **Nuevo Skype para usuarios del servidor de empresa** , haga clic en **Agregar**.
    
8. Para definir parámetros de búsqueda de los objetos que quiera encontrar, en la página **Seleccionar de Active Directory**, seleccione **Buscar** y, si lo desea, haga clic en **Agregar filtro**. También puede seleccionar **Búsqueda LDAP** y especificar una expresión de LDAP para filtrar o limitar los objetos que se devolverán. Una vez establecidas las opciones de búsqueda, haga clic en **Buscar**.
    
9. En el panel de resultados de la búsqueda, seleccione los usuarios que desea agregar y, luego, haga clic en **Aceptar**.
    
10. En la página **Nuevo Skype para usuarios del servidor de empresa** , los usuarios seleccionados están en la presentación de **los usuarios** . En la lista **Asignar usuarios a un grupo**, seleccione el servidor en el que se necesitan hospedar los usuarios.
    
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
    
    Para probar la funcionalidad básica, seleccione la opción deseada para el valor de **URI de SIP del usuario generar** (las demás opciones de la configuración predeterminada del uso) y, a continuación, haga clic en **Habilitar**, como se muestra en la figura.
    
     ![Habilita a los usuarios del Panel de control.](../../media/7ee8717d-9a1f-4864-8f45-71071c88878f.png)
  
11. Se muestra una página de resumen con una marca de verificación en la columna **Habilitado** para indicar que los usuarios están configurados. En la columna **Dirección SIP** figura la dirección que se necesita para configurar el inicio de sesión del usuario.
    
     ![Usuarios añadidos al Panel de control del servidor de Skype Empresarial.](../../media/8960548a-8d6d-44c5-bc01-6f9fb11b7588.png)
  
12. Es preciso que un usuario inicie sesión en un equipo integrado en el dominio y que otro usuario lo haga en otro equipo del dominio.
    
13. Instalar Skype para Business client en cada uno de los dos equipos cliente y, a continuación, compruebe que ambos usuarios pueden iniciar sesión en Skype para Business Server y pueden enviar mensajes instantáneos entre sí.
    

