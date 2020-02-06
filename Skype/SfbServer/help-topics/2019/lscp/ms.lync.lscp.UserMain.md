---
title: Panel de control-búsqueda de usuarios actualizada
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.UserMain
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 50feb75f-92a1-4916-b92e-c039e1290c52
ROBOTS: NOINDEX, NOFOLLOW
description: Puede usar los resultados de una consulta de búsqueda para configurar los usuarios de Skype empresarial Server. Puede buscar usuarios según el nombre para mostrar, el nombre, los apellidos, el nombre de cuenta del Administrador de cuentas de seguridad (SAM), la dirección SIP o el identificador uniforme de recursos (URI) de línea. También Puede buscar usuarios con el panel de control de Lync Server o el complemento de usuarios y equipos de Active Directory.
ms.openlocfilehash: 5322d98e17d93243ad379cad886bea872b215451
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41795591"
---
# <a name="control-panel---updated-user-search"></a>Panel de control - actualización: Búsqueda de usuarios

Puede usar los resultados de una consulta de búsqueda para configurar los usuarios de Skype empresarial Server. Puede buscar usuarios según el nombre para mostrar, el nombre, los apellidos, el nombre de cuenta del Administrador de cuentas de seguridad (SAM), la dirección SIP o el identificador uniforme de recursos (URI) de línea. También Puede buscar usuarios con el panel de control de Lync Server o el complemento de usuarios y equipos de Active Directory.

## <a name="tasks-you-can-perform"></a>Tareas que puede realizar

Puede llevar a cabo las tareas siguientes en la página **Búsqueda de usuarios** del panel de control:

- [Buscar usuarios](https://technet.microsoft.com/library/3b9f6f55-d7a9-46ae-8e10-f221ba0d3bb5.aspx)

- [Habilitar o deshabilitar usuarios](https://technet.microsoft.com/library/12497d00-f665-4a97-be68-854c5a8be4fc.aspx)

- [Mover usuario](ms.lync.lscp.UserMove.md)

- [Mover todos los usuarios](ms.lync.lscp.UserMoveAll.md)

- [Assign Policies to Users](https://technet.microsoft.com/library/a4ed0120-d9e5-4eb2-acfd-8de2cb503652.aspx)

- [Habilitar usuarios para telefonía IP empresarial en Skype empresarial Server](../../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md)

- [Configure Federation, Remote User Access, and Public IM Connectivity for Users](https://technet.microsoft.com/library/736fcaad-9f95-4896-b767-e199d86a00a4.aspx)

- [Configure Telephony for Users](https://technet.microsoft.com/library/4546432e-c839-4517-a2c5-bc0d4d8c6a03.aspx)



## <a name="ui-reference"></a>Referencia de interfaz de usuario

En las siguientes listas se describen los menús, comandos, campos y propiedades de la página **Búsqueda de usuarios**.

### <a name="user-search"></a>Búsqueda de usuarios

- **Búsqueda** Busque usuarios por la primera parte del nombre para mostrar, el nombre, el apellido, el nombre de cuenta SAM, la dirección SIP o el URI de línea de la cuenta de usuario.

- **Búsqueda LDAP** Busque usuarios escribiendo una expresión LDAP.

- **Cuadro Buscar usuarios** Escriba los datos de usuario o la expresión LDAP que desea búsqueda.

- **Buscar** Haga clic para mostrar los usuarios que coinciden con los valores de búsqueda introducidos en el cuadro **Buscar usuarios** y.

- **Abrir consulta** Haga clic para abrir una consulta de búsqueda guardada.

- **Guardar consulta** Haga clic en para guardar una consulta de búsqueda.

- **+ Agregar filtro** Haga clic para agregar criterios de búsqueda adicionales.

- **Campos de filtro de búsqueda** Seleccione el campo en el que desea filtrar los resultados de la búsqueda, seleccione un operador para la consulta y, a continuación, escriba la cadena en la que desea realizar la búsqueda.

- **Número máximo de usuarios que desea mostrar** Escriba el número de resultados de búsqueda que desea mostrar o use las flechas arriba y abajo para especificar el número.

Escriba más texto descriptivo, según sea conveniente.

### <a name="search-results-menus"></a>Menús de resultados de la búsqueda

- **Habilitar usuarios** Haga clic para abrir el cuadro de diálogo [usuarios: nuevo Lync Server](ms.lync.lscp.UserNew.md) , donde puede Agregar un nuevo usuario a Skype empresarial Server.

    Para agregar un nuevo contacto, haga clic en la flecha abajo y, luego, seleccione **Habilitar contactos** para abrir el cuadro de diálogo [Users: New Contact Objects](ms.lync.lscp.UserNewContact.md).

- **Editar** Haga clic en **Editar** y, a continuación, haga clic en **Mostrar detalles** para mostrar los detalles del usuario seleccionado, o bien haga clic en **seleccionar todos los resultados** de la búsqueda para seleccionar todos los usuarios que se muestran en la tabla resultados.

- **Acción** Haga clic en **acción**y, a continuación, seleccione la acción que desea realizar para los usuarios seleccionados en los resultados de la búsqueda. Están disponibles las siguientes acciones:

  - **Volver a habilitar para Lync Server** Habilita la cuenta de usuario seleccionada después de que se haya deshabilitado temporalmente.

  - **Deshabilitar temporalmente para Lync Server** Deshabilita la cuenta de usuario en Skype empresarial Server hasta que se vuelva a habilitar, sin quitar la cuenta de usuario.

  - **Asignar directivas** Abre el cuadro de diálogo [usuarios: asignar directivas](ms.lync.lscp.UserAssignPolicy.md) , donde puede configurar las directivas asignadas al usuario.

  - **Ver estado del PIN** Abre el cuadro de diálogo [usuarios: estado de vista PIN](ms.lync.lscp.UserViewPin.md) , que muestra los datos del PIN del usuario seleccionado.

  - **Establecer PIN** Abre el cuadro de diálogo [establecer PIN](ms.lync.lscp.UserSetPin.md) , donde puede establecer el PIN para el usuario seleccionado.

  - **Bloquear PIN** Bloquea el PIN para el usuario.

  - **Desbloquear pin** Quita el bloqueo del PIN del usuario.

  - **Quitar de Lync Server** Quita la cuenta de usuario de Skype empresarial Server. El usuario no se elimina de Active Directory.

  - **Quitar certificado de usuario** Quita todos los certificados otorgados al usuario.

  - **Mover los usuarios seleccionados al grupo** Abre el cuadro de diálogo [mover usuario](ms.lync.lscp.UserMove.md) , donde puede seleccionar un grupo al que mover el usuario seleccionado.

  - **Mover todos los usuarios al grupo** Abre el cuadro de diálogo [mover usuario](ms.lync.lscp.UserMove.md) , donde puede seleccionar un grupo para mover a todos los usuarios seleccionados.


