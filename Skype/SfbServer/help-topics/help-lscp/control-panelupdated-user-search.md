---
title: 'Panel de control: búsqueda de usuario actualizada'
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 5/21/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.UserMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 50feb75f-92a1-4916-b92e-c039e1290c52
description: Puede usar los resultados de una consulta de búsqueda para configurar los usuarios de Skype Empresarial Server. Puede buscar usuarios según el nombre para mostrar, el nombre, los apellidos, el número de cuenta del Administrador de cuentas de seguridad (SAM), la dirección SIP o el identificador uniforme de recursos (URI) de línea. También puede buscar usuarios mediante el Panel de control de Lync Server o el complemento Usuarios y equipos de Active Directory.
ms.openlocfilehash: 117f1c6a5a697cb1cf9e8e1f5c6cbf8363c517bf
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119939"
---
# <a name="control-panel---updated-user-search"></a>Panel de control actualizado: Búsqueda de usuarios

Puede usar los resultados de una consulta de búsqueda para configurar los usuarios de Skype Empresarial Server. Puede buscar usuarios según el nombre para mostrar, el nombre, los apellidos, el número de cuenta del Administrador de cuentas de seguridad (SAM), la dirección SIP o el identificador uniforme de recursos (URI) de línea. También puede buscar usuarios mediante el Panel de control de Lync Server o el complemento Usuarios y equipos de Active Directory.

## <a name="tasks-you-can-perform"></a>Tareas que puede realizar

Puede realizar las siguientes tareas en la **página** Panel de control de búsqueda del usuario:

- [Buscar usuarios de Lync Server 2010](/previous-versions/office/lync-server-2013/lync-server-2013-search-for-lync-server-users)

- [Habilitar o deshabilitar usuarios para Lync Server 2010](/previous-versions/office/lync-server-2013/lync-server-2013-disable-or-re-enable-user-account-for-lync-server)

- [Mover usuario](move-user.md)

- [Mover todos los usuarios](move-all-users.md)

- [Asignar directivas a usuarios](/previous-versions/office/lync-server-2013/lync-server-2013-assigning-per-user-policies)

- [Habilitar usuarios para Telefonía IP empresarial en Skype Empresarial Server 2015](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md)

- [Configurar la federación, el acceso remoto de usuarios y la conectividad de mensajería instantánea pública para los usuarios](/previous-versions/office/lync-server-2013/lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user)

- [Configurar telefonía para usuarios](/previous-versions/office/lync-server-2013/lync-server-2013-configure-telephony-for-a-user)

Para obtener información detallada sobre los diferentes procedimientos que puede realizar mediante el Panel de control de Skype Empresarial Server, vea [Manage Skype for Business Server 2015](../../manage/manage.md).

## <a name="ui-reference"></a>Referencia de la UI

Las listas siguientes describen los menús, comandos, campos y propiedades de la página de **Búsqueda de usuarios**.

### <a name="user-search"></a>Búsqueda de usuarios

- **Búsqueda** Busque usuarios por la primera parte del nombre para mostrar, el nombre, el apellido, el nombre de cuenta SAM, la dirección SIP o el URI de línea de la cuenta de usuario.

- **Búsqueda LDAP** Busque usuarios escribiendo una expresión LDAP.

- **Cuadro Buscar usuarios** Escriba los datos de usuario o la expresión LDAP que desea buscar.

- **Buscar** Haga clic para mostrar los usuarios que coinciden con los valores de búsqueda especificados en el cuadro **Buscar usuarios** y.

- **Consulta abierta** Haga clic para abrir una consulta de búsqueda guardada.

- **Guardar consulta** Haga clic para guardar una consulta de búsqueda.

- **+ Agregar filtro** Haga clic para agregar criterios de búsqueda adicionales.

- **Campos de filtro de búsqueda** Seleccione el campo en el que desea filtrar los resultados de la búsqueda, seleccione un operador para la consulta y, a continuación, escriba la cadena en la que desea buscar.

- **Máximo de usuarios para mostrar** Escriba el número de resultados de búsqueda que desea mostrar o use las flechas arriba y abajo para especificar el número.

Agregar texto descriptivo adicional, según sea conveniente.

### <a name="search-results-menus"></a>Menús de búsqueda de resultados

- **Habilitar usuarios** Haga clic para abrir el [cuadro de diálogo Usuarios: Nuevo](users-new-lync-server-user.md) usuario de Lync Server, donde puede agregar un nuevo usuario a Skype Empresarial Server.

    Para agregar un nuevo contacto, haga clic en la flecha abajo y luego seleccione **Activar contactos** para abrir el cuadro de diálogo de [Users: New Contact Objects](users-new-contact-objects.md).

- **Editar** Haga **clic en** Editar y, a continuación, en Mostrar detalles para mostrar los detalles del usuario seleccionado, o haga clic en **Seleccionar** todos los resultados de búsqueda para seleccionar todos los usuarios que se muestran en la tabla de resultados. 

- **Acción** Haga **clic en** Acción y, a continuación, seleccione la acción que desea realizar para los usuarios seleccionados en los resultados de búsqueda. Están disponibles las siguientes acciones:

  - **Volver a habilitar para Lync Server** Habilita la cuenta de usuario seleccionada después de que se haya deshabilitado temporalmente.

  - **Deshabilitar temporalmente para Lync Server** Deshabilita la cuenta de usuario en Skype Empresarial Server hasta que vuelva a habilitarla, sin quitar la cuenta de usuario.

  - **Asignar directivas** Abre el [cuadro de diálogo Usuarios: Asignar directivas,](users-assign-policies.md) donde puede configurar las directivas asignadas al usuario.

  - **Ver estado del PIN** Abre el [cuadro de diálogo Usuarios: Ver](users-view-pin-status.md) estado del PIN, que muestra los datos de PIN del usuario seleccionado.

  - **Establecer PIN** Abre el cuadro de diálogo Establecer [PIN,](set-pin.md) donde puede establecer el PIN para el usuario seleccionado.

  - **BLOQUEAR PIN** Bloquea el PIN del usuario.

  - **Desbloquear PIN** Quita el bloqueo del PIN del usuario.

  - **Quitar de Lync Server** Quita la cuenta de usuario de Skype Empresarial Server. El usuario no se elimina de Active Directory.

  - **Quitar certificado de usuario** Quita todos los certificados concedidos al usuario.

  - **Mover usuarios seleccionados al grupo** Abre el [cuadro de diálogo](move-user.md) Mover usuario, donde puede seleccionar un grupo al que mover el usuario seleccionado.

  - **Mover todos los usuarios al grupo** Abre el [cuadro de diálogo](move-user.md) Mover usuario, donde puede seleccionar un grupo al que mover todos los usuarios seleccionados.