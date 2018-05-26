---
title: Panel de control - búsqueda de usuario actualizada
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 5/21/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.UserMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 50feb75f-92a1-4916-b92e-c039e1290c52
description: Puede usar los resultados de una consulta de búsqueda para configurar usuarios de Skype para Business Server. Puede buscar usuarios según el nombre para mostrar, el nombre, los apellidos, el nombre de cuenta del Administrador de cuentas de seguridad (SAM), la dirección SIP o el identificador uniforme de recursos (URI) de línea. También Puede buscar usuarios con el panel de control de Lync Server o el complemento de usuarios y equipos de Active Directory.
ms.openlocfilehash: 188c60467f5579a56cd4b5fa85a616f2e4639663
ms.sourcegitcommit: 9d816453083c26fd24f8a1cdc0f53f3d218c43b3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/25/2018
---
# <a name="control-panel---updated-user-search"></a>Panel de control - actualización: Búsqueda de usuarios
 
Puede usar los resultados de una consulta de búsqueda para configurar usuarios de Skype para Business Server. Puede buscar usuarios según el nombre para mostrar, el nombre, los apellidos, el nombre de cuenta del Administrador de cuentas de seguridad (SAM), la dirección SIP o el identificador uniforme de recursos (URI) de línea. También Puede buscar usuarios con el panel de control de Lync Server o el complemento de usuarios y equipos de Active Directory.
  
## <a name="tasks-you-can-perform"></a>Tareas que puede realizar

Puede llevar a cabo las tareas siguientes en la página **Búsqueda de usuarios** del panel de control:
  
- [Búsqueda para los usuarios de Lync Server 2010](http://technet.microsoft.com/library/3b9f6f55-d7a9-46ae-8e10-f221ba0d3bb5.aspx)
    
- [Habilitar o deshabilitar usuarios para Lync Server 2010](http://technet.microsoft.com/library/12497d00-f665-4a97-be68-854c5a8be4fc.aspx)
    
- [Mover el usuario](ms.lync.lscp.UserMove.md)
    
- [Mover todos los usuarios](ms.lync.lscp.UserMoveAll.md)
    
- [Asignar directivas a usuarios](http://technet.microsoft.com/library/a4ed0120-d9e5-4eb2-acfd-8de2cb503652.aspx)
    
- [Habilitar a usuarios para Enterprise Voice en Skype para Business Server 2015](../../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md)
    
- [Configurar la federación, el acceso de usuarios remotos y la conectividad de mensajería instantánea pública para los usuarios](http://technet.microsoft.com/library/736fcaad-9f95-4896-b767-e199d86a00a4.aspx)
    
- [Configurar la telefonía para los usuarios](http://technet.microsoft.com/library/4546432e-c839-4517-a2c5-bc0d4d8c6a03.aspx)
    
Para obtener información detallada sobre los distintos procedimientos que puede realizar mediante el uso de la Skype para el Panel de Control de servidor empresarial, vea [Administrar Skype para Business Server 2015](../../../manage/manage.md).
  
## <a name="ui-reference"></a>Referencia de interfaz de usuario

En las siguientes listas se describen los menús, comandos, campos y propiedades de la página **Búsqueda de usuarios**.
  
### <a name="user-search"></a>Búsqueda de usuarios

- **Búsqueda** Buscar usuarios por la primera parte del nombre para mostrar, nombre, apellidos, nombre de cuenta SAM, dirección SIP o URI de la cuenta de usuario de línea.
    
- **Búsqueda LDAP** Búsqueda de usuarios escribiendo una expresión de LDAP.
    
- **Cuadro de búsqueda a los usuarios** Escriba los datos de usuario o expresión de LDAP que quiera buscar.
    
- **Buscar** Haga clic en para mostrar los usuarios que coinciden con los valores de búsqueda que escribió en el cuadro y la **búsqueda de usuarios** .
    
- **Abrir consulta** Haga clic para abrir una consulta de búsqueda guardada.
    
- **Guardar consulta** Haga clic aquí para guardar una consulta de búsqueda.
    
- **+ Agregar filtro** Haga clic aquí para agregar criterios de búsqueda adicionales.
    
- **Campos de filtro de búsqueda** Seleccione el campo en el que desea filtrar los resultados de búsqueda, seleccione un operador para la consulta y, a continuación, escriba la cadena que desea buscar en.
    
- **Número máximo de usuarios para mostrar** Escriba el número de resultados de búsqueda que desea mostrar, o use las flechas y abajo para especificar el número.
    
Escriba más texto descriptivo, según sea conveniente.
  
### <a name="search-results-menus"></a>Menús de resultados de la búsqueda

- **Permitir a los usuarios** Haga clic para abrir el [a los usuarios: nuevo usuario de Lync Server](ms.lync.lscp.UserNew.md) cuadro de diálogo, donde puede agregar un nuevo usuario a Skype para Business Server.
    
    Para agregar un nuevo contacto, haga clic en la flecha hacia abajo y, a continuación, seleccione **Habilitar contactos** para abrir el [a los usuarios: nuevos objetos de contacto](ms.lync.lscp.UserNewContact.md) cuadro de diálogo.
    
- **Editar** Haga clic en **Editar** y, a continuación, haga clic en **Mostrar detalles** para mostrar los detalles del usuario seleccionado, o haga clic en **Seleccionar todos los resultados de búsqueda** para seleccionar todos los usuarios que se muestran en la tabla de resultados.
    
- **Acción** Haga clic en **acción**y, a continuación, seleccione la acción que desea realizar para los usuarios seleccionados en los resultados de búsqueda. Están disponibles las siguientes acciones:
    
  - **Volver a habilitar para Lync Server** Permite que la cuenta de usuario seleccionada después de que se ha deshabilitado temporalmente.
    
  - **Deshabilitar temporalmente para Lync Server** Deshabilita la cuenta de usuario en Skype para Business Server hasta que vuelva a activarlo, sin quitar la cuenta de usuario.
    
  - **Asignar directivas** Se abre la [a los usuarios: asignar directivas](ms.lync.lscp.UserAssignPolicy.md) cuadro de diálogo, donde puede configurar las directivas asignadas al usuario.
    
  - **Ver estado de PIN** Se abre la [a los usuarios: ver el estado de PIN](ms.lync.lscp.UserViewPin.md) cuadro de diálogo que muestra los datos de PIN del usuario seleccionado.
    
  - **Establecer PIN** Se abre el cuadro de diálogo [Establecer PIN](ms.lync.lscp.UserSetPin.md) , donde puede configurar el PIN del usuario seleccionado.
    
  - **Bloqueo de PIN** Bloquea el PIN para el usuario.
    
  - **Desbloquear el PIN** Quita el bloqueo en el PIN del usuario.
    
  - **Quitar de Lync Server** Quita la cuenta de usuario de Skype para Business Server. El usuario no se elimina de Active Directory.
    
  - **Quitar certificado de usuario** Quita todos los certificados concedidos al usuario.
    
  - **Mover los usuarios seleccionados al grupo de servidores** Se abre el cuadro de diálogo de [Move User](ms.lync.lscp.UserMove.md) , donde puede seleccionar un grupo de servidores al que mover el usuario seleccionado.
    
  - **Mover todos los usuarios al grupo de servidores** Se abre el cuadro de diálogo de [Move User](ms.lync.lscp.UserMove.md) , donde puede seleccionar para mover todos los usuarios seleccionados a un grupo de servidores.
    

